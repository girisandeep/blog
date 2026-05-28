---
layout: post
title: "Why LLMs Should Generate Code Instead of Guessing Answers From Data"
category: "Building Terno AI"
tags: [llm, data-analytics, code-generation, reliability, enterprise-ai]
excerpt: >
  When an AI is asked a question about data, it faces a choice: generate text that
  sounds like the answer, or generate code that computes the answer. These are not
  the same. Here is why the distinction matters enormously for enterprise use.
---

Let me describe two ways an AI can respond to the question:
*"What was our best-performing product category last quarter?"*

**Approach One:** The AI reads the question, accesses some information about your
business, and generates a response: *"Based on available information, your Electronics
category showed the strongest performance last quarter, with revenue growth of approximately
18% compared to the prior period."*

**Approach Two:** The AI generates the following code, executes it, and returns the result:

```python
import pandas as pd

df = query_database("""
    SELECT
        category,
        SUM(revenue) as total_revenue,
        SUM(revenue) - LAG(SUM(revenue)) OVER (PARTITION BY category ORDER BY quarter) as qoq_growth
    FROM sales
    WHERE quarter = '2025-Q3'
    GROUP BY category
    ORDER BY total_revenue DESC
    LIMIT 5
""")

best_category = df.iloc[0]
print(f"Best category: {best_category['category']}")
print(f"Revenue: {best_category['total_revenue']:,.0f}")
print(f"QoQ growth: {best_category['qoq_growth']:,.0f} ({best_category['qoq_growth']/df.iloc[0]['total_revenue']*100:.1f}%)")
```

The difference between these two approaches is not stylistic. It is fundamental.

## What Approach One Is Actually Doing

Approach One uses a language model's text generation capability to produce something
that resembles an answer. The model has learned, from training data, what analytical
answers look like. It knows that such answers typically contain category names,
percentages, comparisons to prior periods, and confident-sounding phrasing.

But here is what the model cannot do: it cannot know whether its output is correct.

The number "18%" was generated because it sounds plausible in this context. The word
"Electronics" was selected because it sounds like a plausible best-performing category.
The model has no mechanism to verify these claims against actual data.

This is what we mean when we say that language models hallucinate. It is not a bug
that can be fixed with a better prompt. It is a property of the underlying approach.
Text generation produces text that is *plausible given its training*, not text that is
*verified against the actual state of the world*.

For answering general knowledge questions, this limitation is manageable.
For answering questions about your specific business data, it is not.

## What Approach Two Is Actually Doing

Approach Two uses a language model's code generation capability to produce an
analytical program. The program is then executed against the actual data.

This changes the reliability property completely.

The answer now comes from running the analysis. The number returned is the actual
number in the database. The category returned is the category that actually has the
highest revenue. These facts are computed, not generated.

The language model can still make errors — it might write syntactically incorrect
code, or make incorrect assumptions about the database schema. But these errors are
of a completely different character:

1. **They are often visible.** Code that is wrong frequently fails to run, rather
   than running and producing a plausible-looking wrong answer.

2. **They are auditable.** You can inspect the code and see exactly what analysis
   was performed. A data analyst can review the SQL and confirm that it answers
   the intended question.

3. **They are reproducible.** Running the same code against the same data will
   always produce the same result. The answer is not different every time you ask.

4. **They are correctable.** If the code is wrong, you can fix it. If a text
   generation output is wrong, you have no mechanism for correction other than
   asking again and hoping the next generation is better.

## Why This Matters for Enterprise Use

Imagine a product manager making a headcount decision based on analysis of customer
acquisition data. Or a finance leader using AI-generated analysis to inform an
investment decision. Or a supply chain team using AI to forecast inventory needs.

In these contexts, the difference between an answer that is computed and an answer
that is generated is not academic. It is the difference between reliable intelligence
and sophisticated-sounding noise.

The enterprises that will benefit most from AI analytics are not those with the
highest tolerance for occasional errors. They are those who can apply AI to decisions
that matter — which requires a level of reliability that text generation cannot provide.

## The Code Quality Challenge

I want to be honest about the limitations of the code generation approach as well.

Generating correct analytical code is harder than generating correct text. Language
models can produce code that is syntactically valid but semantically wrong — querying
the right table but computing the wrong metric, applying the right function but to
the wrong column, producing results that look plausible but measure the wrong thing.

Addressing this requires several things working together:

**A rich semantic layer.** The model needs to know what the data actually means —
not just the schema, but the business context. What does "revenue" mean in your
system? Is it net or gross? Does it include refunds? Are there edge cases in how
certain categories are classified?

**Schema validation.** The generated code should be checked against the actual
schema before execution to catch references to non-existent tables or columns.

**Output validation.** Where possible, the results should be checked for plausibility —
are these numbers in the expected range? Do the totals add up correctly?

**Iterative refinement.** When code fails or produces unexpected output, the system
should be able to diagnose the problem and generate a corrected version.

None of these are fully solved. But they are solvable in a way that the fundamental
reliability problem of text generation is not.

## The Right Tool for the Right Problem

I am not arguing that text generation is useless for analytical work. There are
contexts where it is exactly right: summarising results, explaining analysis in
plain language, generating hypotheses to investigate, answering questions about
general methodology.

But for the core task of answering specific factual questions about enterprise data,
code generation and execution is the right approach. Not because it is more
impressive, but because it is more honest about what AI can and cannot reliably do.

The goal is not an AI that always sounds confident. The goal is an AI that is
genuinely trustworthy — that fails visibly when it fails, that produces verifiable
results when it succeeds, and that gives the humans who use it real information
rather than the appearance of it.

That is the kind of AI that enterprises actually need.

---

*This is part of my ongoing writing on building Terno AI. Previous essays in this
series cover [why I am building an AI data scientist](/essays) and
[enterprise AI security](/essays).*
