---
layout: post
title: "Domain-Focused PCA on Text Embeddings Improves Semantic Retrieval"
category: "Building Terno AI"
tags: [research, embeddings, pca, semantic-retrieval, nlp, enterprise-ai]
excerpt: >
  We published a paper showing that applying PCA to domain-specific text embeddings —
  fitted only on the target corpus — improves retrieval accuracy by 5.2%, increases
  the similarity gap 2.5×, and compresses storage 48× with no fine-tuning required.
---

One of the core problems in building a reliable AI system for enterprise data is
retrieval: given a user's question, can you find the right context quickly and
accurately?

Modern retrieval systems depend heavily on text embeddings — dense vector
representations produced by models like OpenAI's `text-embedding-3-small`. These
embeddings are trained on enormous general-purpose corpora. They work remarkably
well as a starting point. But "general purpose" is not the same as "domain optimal."
A model trained on the entire internet does not distribute its representational
capacity the way a medical, legal or financial corpus would want it to.

The question I wanted to answer: can we improve retrieval accuracy in a specific
domain without fine-tuning the embedding model — which is expensive, slow, and
requires labelled data?

The answer turned out to be yes, with a surprisingly simple technique.

## The Idea

[Principal Component Analysis](https://en.wikipedia.org/wiki/Principal_component_analysis)
(PCA) is one of the oldest ideas in machine learning. It finds the directions of
maximum variance in a set of vectors and projects everything onto those directions.
Applied to text embeddings from a domain-specific corpus, it does something useful:
it rotates the embedding space so that the axes align with the directions that
actually matter for *this* domain, rather than the directions that mattered across
the general training data.

The intuition is straightforward. A general embedding model uses many dimensions
to represent distinctions that are important across all domains. In a medical corpus,
most of those dimensions are irrelevant noise. PCA finds the dimensions that carry
real signal for the documents you actually have, and discards the rest.

Crucially: we fit the PCA transform *only on the document corpus*, not on queries.
This turns out to matter.

## What We Tested

We ran experiments on a medical domain corpus covering 20 clinical topics, using
OpenAI's `text-embedding-3-small` as the base embedding model. We tested five
hypotheses about when and why domain-focused PCA helps:

1. Does PCA on a domain corpus improve MAP over the raw baseline?
2. Is 32 dimensions the sweet spot, or does more always help?
3. Does fitting PCA on corpus-only data outperform fitting on corpus + queries?
4. Do random projections produce the same gains? (Spoiler: they do not.)
5. Does the improvement hold as corpus diversity increases?

## The Results

The best configuration — **PCA-32, fitted on the document corpus only** —
achieved a Mean Average Precision (MAP) of **0.9203** against a baseline of
**0.8750**. That is a **+5.2% improvement** in retrieval accuracy.

Two other numbers from the results matter practically:

- **2.5× increase in similarity gap** — the distance between a correct match and
  the nearest incorrect one grows substantially. This makes retrieval more robust
  in real systems where you are using a threshold to decide what to include.

- **48× reduction in storage** — going from 1536-dimensional to 32-dimensional
  vectors. For large enterprise corpora, this is not a minor convenience.
  It is the difference between retrieval that fits in memory and retrieval that
  requires expensive infrastructure.

The random projection control was important. When we projected embeddings onto
32 random directions instead of 32 PCA-derived directions, accuracy did not
improve. The gain comes specifically from aligning dimensions with the domain —
not just from reducing dimensionality. That rules out the possibility that we
were simply compressing away noise randomly.

The corpus-only fitting result was also notable. Adding query vectors to the
PCA fitting data slightly reduced performance compared to fitting on documents
alone. The retrieval task is fundamentally about the document space; letting
query variation influence the principal components adds irrelevant structure.

Finally, as corpus diversity increased across our 20-topic dataset, performance
*improved* rather than degrading. This is encouraging for practical deployment:
the technique scales with the breadth of the domain corpus rather than
becoming less useful.

## Why This Matters for Enterprise AI

At Terno AI, we think a lot about how to make retrieval accurate and efficient
for enterprise data. The problem is not just finding relevant content — it is
finding it reliably enough to trust the downstream reasoning.

Enterprise corpora are not the internet. They are specific: a legal firm's
contracts, a hospital's clinical notes, a manufacturer's technical documentation.
The variance structure in these corpora is nothing like the variance structure
of a general embedding model's training data.

Domain-focused PCA offers a lightweight path to alignment without fine-tuning:
- No labelled data required
- No model training
- Runs in seconds on a modern laptop
- Composable with any embedding model
- Interpretable — you can inspect the principal components

It fits naturally into a semantic layer architecture where you want retrieval to
be accurate *and* fast *and* auditable.

## The Paper and Code

The full paper is published on Zenodo:

**[Domain-Focused PCA on Text Embeddings Improves Semantic Retrieval: A Medical Domain Study](https://zenodo.org/records/20320367)**
DOI: 10.5281/zenodo.20320367

The code — including the full experiment, figure generation, and a cached
embedding pipeline that avoids repeated API calls — is on GitHub:

**[github.com/cloudxlab/pca_embeddings](https://github.com/cloudxlab/pca_embeddings)**

To run it yourself:

```bash
git clone https://github.com/cloudxlab/pca_embeddings
pip install openai scikit-learn numpy pandas matplotlib seaborn
export OPENAI_API_KEY=your-key
python3 pca_experiment_v2.py
```

Embeddings are cached locally after the first run, so subsequent experiments
cost nothing in API calls.

## What Is Next

This study used a medical corpus as a controlled testbed. The obvious questions
for follow-up are: does the gain hold in legal, financial, and technical domains?
What is the relationship between corpus size and optimal PCA dimensionality?
Can the principal components themselves be used to understand what a corpus is
"about" — as a form of automatic semantic layer construction?

These are the questions we are working on. If you are building retrieval systems
for enterprise domains, I would be interested to hear what you find.

---

*The paper is open access under Creative Commons Attribution 4.0. The code is
MIT licensed. Both are free to use and build on.*
