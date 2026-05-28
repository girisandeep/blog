---
layout: post
title: "Why I Am Building an AI Data Scientist"
category: "Building Terno AI"
tags: [terno-ai, enterprise-ai, data-science, analytics, product]
excerpt: >
  Every enterprise has data. Very few have the people, time and tools to ask real questions
  of it. I am building Terno AI because I believe the right solution is not more dashboards —
  it is an AI that can actually perform analysis.
featured: true
---

I want to tell you about a problem I have seen repeatedly.

A business leader wants to understand something about their company. Maybe it is why
churn increased last quarter. Maybe it is which customer segment is driving most of
the growth. Maybe it is whether the promotional campaign actually worked, after
controlling for seasonality.

These are not unusual questions. They are exactly the kind of question that good
businesses ask constantly.

Now watch what happens next.

The leader opens their BI dashboard. They find some charts. The charts show overall
trends but not the specific slice they need. They submit a request to the data team.
The data team is busy. Three days later, a report comes back. But the question has
slightly changed — and the report does not quite answer the new version.

This cycle plays out thousands of times a day in organisations around the world.

## The Wrong Tool for the Job

The standard response to this problem has been dashboards. Build more dashboards.
Add more pre-built reports. Create more self-service analytics tools.

I think this is the wrong tool for the problem.

Dashboards are good at showing you what you already know you want to see. They are
built around anticipated questions. But the most valuable analytical work is almost
always about unanticipated questions — the question that occurs to you in the middle
of a meeting, the follow-up that emerges from an answer, the investigation that was
triggered by something unexpected.

For that kind of work, a dashboard is useless.

## The AI Promise — and the AI Problem

The obvious modern answer is: use AI. Ask your data a question in plain English.

And to be fair, there are now many tools that let you do something like this. You type
a question, the AI generates SQL or a summary, and an answer appears.

But there is a problem with this approach that I became increasingly uncomfortable with
the more I thought about it.

When a language model reads your question and produces an answer, it is doing text
generation. It is producing text that sounds like the right answer to your question,
based on patterns it learned during training. It has learned, in some sense, what
analytical answers look like.

But there is a fundamental difference between text that resembles an answer and an
answer that is actually correct.

A language model can write "revenue grew 23% in Q3" with exactly as much confidence
whether the actual number is 23% or 7% or -4%. It cannot distinguish between a
statistically sound conclusion and a plausible-sounding fabrication, because it is
not doing statistics. It is doing writing.

For most applications, this is an acceptable limitation. But for business decisions —
for the kind of analysis that drives headcount decisions, investment choices, product
roadmaps — it is not acceptable.

## A Different Approach

The approach I am taking with Terno AI starts from a different premise.

Rather than asking a language model to produce an answer, I am asking it to produce
*code that computes* the answer. The code is then executed in a secure, sandboxed
environment against the actual data. The result is computed, not composed.

This changes the reliability property completely. The answer comes from running the
analysis, not from generating text. You can inspect the code. You can verify the logic.
You can reproduce the result. And if the code is wrong, it will often fail visibly
rather than silently — which is itself useful information.

This is what I mean when I say Terno AI is an AI data scientist rather than an
AI answer-generator. It is designed to actually perform the analysis.

## The Semantic Layer Problem

There is a second, less obvious challenge that I have become increasingly focused on.

Real enterprise databases are messy in ways that make naive AI applications fail.

Table names were chosen by engineers, not by business users. Column names are often
abbreviations or legacy codes. Business concepts are not documented anywhere in the
schema. The relationship between what a user means by "active customer" and what the
database actually contains requires knowledge that is not in the data itself.

I have come to believe that an AI data scientist that ignores this problem will produce
unreliable results even if the underlying analysis engine is perfect. The analytical
code might be syntactically correct but semantically wrong — computing the right
operation on the wrong thing.

Terno AI addresses this through what I call a semantic layer: a maintained, structured
understanding of what the data actually means. What tables represent. How columns map
to business concepts. What business formulas mean. Which terms users commonly use and
what they refer to.

This is unglamorous work. But I have become convinced it is the difference between
a demo that looks impressive and a product that actually works reliably.

## Why Now

Two things have come together to make this tractable now.

The first is the quality of current language models. The ability to generate analytically
correct code from a natural language description of a task has improved dramatically in
the last few years. It is not perfect — but it is good enough to be genuinely useful,
and it is improving rapidly.

The second is the broader enterprise appetite for AI that actually works. There is a
growing frustration, in my view, with AI applications that are impressive in
demonstrations but unreliable in production. Enterprises are looking for AI they can
trust for real work — and they are willing to pay for it.

## The Larger Question

I am building Terno AI partly because I think it is commercially valuable. But I am
also building it because I think it addresses a real problem in how organisations make
decisions.

Most organisations have data. Few of them can ask real questions of it. The people
who can ask — skilled data analysts and data scientists — are expensive, scarce and
slow compared to the rate at which analytical questions arise.

An AI data scientist that can be trusted to perform real analysis — securely, correctly,
reproducibly — is not just a convenience. It is a capability that changes the nature
of how organisations can think about their work.

That seems worth building.

---

*To learn more about how Terno AI approaches enterprise analytics, visit the
[Terno AI page](/terno-ai). For the technical thinking behind secure, reliable
AI analytics, read my next essay on why AI must generate code rather than guessing answers.*
