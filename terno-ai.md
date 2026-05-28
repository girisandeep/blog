---
layout: default
title: Terno AI
description: An enterprise-grade AI data scientist that securely performs analytics on organisational data using natural language.
permalink: /terno-ai/
---

<style>
.terno-hero {
  background: linear-gradient(135deg, #1E3A8A 0%, #1D4ED8 100%);
  color: white;
  padding: 4.5rem 0 4rem;
  margin-bottom: 4rem;
}
.terno-section {
  max-width: 680px;
  margin: 0 auto;
  padding: 0 1.5rem 5rem;
}
.terno-section h2 {
  font-size: 1.5rem;
  font-weight: 700;
  letter-spacing: -0.015em;
  margin: 3rem 0 1rem;
  color: #111827;
}
.terno-section p {
  font-family: 'Lora', serif;
  font-size: 1rem;
  line-height: 1.78;
  color: #374151;
  margin-bottom: 1.25rem;
}
.terno-section blockquote p {
  color: #4B5563;
  font-style: italic;
}
.capability-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin: 1.5rem 0;
}
.capability-card {
  background: #F8FAFC;
  border: 1px solid #E5E7EB;
  border-radius: 10px;
  padding: 1.25rem;
}
.capability-title {
  font-size: 0.9rem;
  font-weight: 700;
  color: #111827;
  margin-bottom: 0.35rem;
}
.capability-desc {
  font-size: 0.82rem;
  color: #6B7280;
  line-height: 1.55;
}
.principle-list {
  list-style: none;
  padding: 0;
}
.principle-list li {
  display: flex;
  gap: 0.75rem;
  align-items: flex-start;
  padding: 0.9rem 0;
  border-bottom: 1px solid #F3F4F6;
}
.principle-list li:last-child { border-bottom: none; }
.principle-list .check {
  width: 22px;
  height: 22px;
  background: #DBEAFE;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.7rem;
  color: #1D4ED8;
  flex-shrink: 0;
  margin-top: 1px;
  font-weight: 700;
}
.principle-list .text strong {
  display: block;
  font-size: 0.95rem;
  font-weight: 600;
  color: #111827;
  margin-bottom: 0.2rem;
}
.principle-list .text span {
  font-family: 'Lora', serif;
  font-size: 0.88rem;
  color: #6B7280;
  line-height: 1.55;
}
@media (max-width: 580px) {
  .capability-grid { grid-template-columns: 1fr; }
}
</style>

<div class="terno-hero">
  <div class="container-content">
    <div style="font-size:0.72rem;font-weight:700;text-transform:uppercase;letter-spacing:0.1em;color:rgba(255,255,255,0.6);margin-bottom:1rem">Current Project</div>
    <h1 style="font-size:clamp(2.2rem,5vw,3rem);font-weight:700;letter-spacing:-0.025em;line-height:1.1;margin-bottom:1.25rem;color:white">Terno AI</h1>
    <p style="font-family:'Lora',serif;font-size:1.15rem;line-height:1.7;color:rgba(255,255,255,0.82);max-width:560px;margin-bottom:2rem">
      An enterprise-grade AI data scientist that securely performs analytics
      on organisational data using natural language.
    </p>
    <div style="display:flex;gap:1rem;flex-wrap:wrap">
      <a href="{{ site.terno_url }}" class="btn" style="background:white;color:#1D4ED8;font-weight:700" target="_blank" rel="noopener">Visit Terno AI →</a>
      <a href="{{ '/essays' | relative_url }}?category=building-terno-ai" class="btn" style="background:rgba(255,255,255,0.12);color:white;border-color:rgba(255,255,255,0.3)">Read my essays on this</a>
    </div>
  </div>
</div>

<div class="terno-section">

## The Problem

Most business users cannot get useful analytical answers from their own data.

The data exists. The databases are there. But obtaining a real analytical answer —
not a summary, not a visualization, but an actual answer to a real business question —
requires a data analyst, a specific query, and significant time.

Dashboards help with reporting. But they do not help when the question is new, when
the analysis is complex, or when you need to combine multiple data sources in an
unexpected way.

There are now AI tools that let users ask questions in natural language. Most of
them generate SQL or text. But they face a fundamental problem:

> **When a language model answers a question about data, it is generating text that
> sounds plausible. That is not the same as performing analysis.**

For business decisions, plausible-sounding is not enough. You need correct.

## What Terno AI Does Differently

Terno AI does not guess answers. It generates and executes analytical code.

When you ask Terno a question, it creates a verifiable analytical workflow — one
that actually runs against your data. The result is computed, not composed. You can
inspect the code. You can reproduce the result. You can verify the logic.

This distinction matters enormously for business use.

<blockquote>
<p>Enterprises do not need AI that guesses answers from their data. They need AI that performs analysis correctly, securely and reproducibly.</p>
</blockquote>

## What Terno Can Analyse

<div class="capability-grid">
  <div class="capability-card">
    <div class="capability-title">Business Intelligence</div>
    <p class="capability-desc">Revenue trends, cohort analysis, funnel metrics, KPI tracking, decision support.</p>
  </div>
  <div class="capability-card">
    <div class="capability-title">Forecasting</div>
    <p class="capability-desc">Time-series forecasting, demand prediction, revenue modelling, growth projection.</p>
  </div>
  <div class="capability-card">
    <div class="capability-title">Classification</div>
    <p class="capability-desc">Customer segmentation, churn prediction, risk scoring, lead qualification.</p>
  </div>
  <div class="capability-card">
    <div class="capability-title">Clustering</div>
    <p class="capability-desc">Customer grouping, product clustering, anomaly detection, behavioural patterns.</p>
  </div>
  <div class="capability-card">
    <div class="capability-title">Statistical Analysis</div>
    <p class="capability-desc">Hypothesis testing, significance analysis, correlation, regression, distributions.</p>
  </div>
  <div class="capability-card">
    <div class="capability-title">Data Exploration</div>
    <p class="capability-desc">Schema understanding, data quality assessment, pattern discovery, profiling.</p>
  </div>
</div>

## Built for Enterprise Security

Connecting AI to enterprise data requires more than capability. It requires trust.

<ul class="principle-list">
  <li>
    <div class="check">&#10003;</div>
    <div class="text">
      <strong>Data stays in your environment</strong>
      <span>Terno AI can be deployed within your private cloud or on-premises infrastructure. Your data does not have to leave your security perimeter.</span>
    </div>
  </li>
  <li>
    <div class="check">&#10003;</div>
    <div class="text">
      <strong>Code-based, verifiable analysis</strong>
      <span>Every answer is backed by executable code that you can inspect, audit and reproduce. No black-box outputs.</span>
    </div>
  </li>
  <li>
    <div class="check">&#10003;</div>
    <div class="text">
      <strong>Sandboxed execution</strong>
      <span>Analytical code runs in a secure, isolated environment. There is no pathway from analysis to unintended system access.</span>
    </div>
  </li>
  <li>
    <div class="check">&#10003;</div>
    <div class="text">
      <strong>Semantic layer for accuracy</strong>
      <span>Terno maintains a structured understanding of your data — what tables mean, how columns map to business concepts, which terms users use. This makes answers dramatically more reliable.</span>
    </div>
  </li>
  <li>
    <div class="check">&#10003;</div>
    <div class="text">
      <strong>Access controls and permissions</strong>
      <span>Fine-grained controls determine which users can query which data, down to row and column level. Security is deterministic, not model-dependent.</span>
    </div>
  </li>
</ul>

## The Semantic Layer

Real enterprise databases are messy. Table names are often confusing. Schemas are
large. Business concepts are undocumented. Relationships are not obvious. Column
names were chosen for a system, not for a human being.

Terno AI addresses this through a **semantic layer**: a maintained understanding of:

- What different tables and fields actually represent
- How column names map to business concepts
- Which business terms users typically use
- What standard business formulas mean
- Which data objects are relevant to which types of questions
- Which data a particular user role is permitted to access

This is not a technical convenience. It is what makes the difference between an AI
that occasionally produces plausible-looking answers and one that reliably produces
correct ones.

## Why I Am Building This

I have spent years at Amazon and InMobi working on systems where data drives
decisions at scale. I have seen how much time and expertise is required to turn
data into useful insight — even in organisations that have excellent engineering
and analytics teams.

The promise of AI-powered analytics is real. But most current tools substitute
the appearance of insight for the reality of it.

I am building Terno AI because businesses deserve better. They deserve an AI data
scientist that can be trusted — one that is secure, correct and genuinely useful
for real analytical work.

## If You Are Building in This Space

If you are an enterprise leader, data engineer, or product builder thinking about
reliable AI analytics, I would be glad to connect. And if you want to follow
the thinking behind how Terno AI is being designed, read my essays on enterprise AI.

<div style="margin-top:3rem;padding:2rem;background:#EEF2FF;border-radius:12px;border:1px solid #DBEAFE">
  <div style="font-size:0.85rem;font-weight:700;color:#1E40AF;margin-bottom:0.75rem">Get involved</div>
  <div style="display:flex;flex-wrap:wrap;gap:0.75rem">
    <a href="{{ site.terno_url }}" class="btn btn--primary" target="_blank" rel="noopener">Visit Terno AI</a>
    <a href="{{ '/essays' | relative_url }}?category=building-terno-ai" class="btn btn--outline">Read related essays</a>
    <a href="{{ '/contact' | relative_url }}" class="btn btn--ghost">Connect</a>
  </div>
</div>

</div>
