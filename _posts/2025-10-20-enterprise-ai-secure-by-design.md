---
layout: post
title: "Why Enterprise AI Must Be Secure by Design"
category: "Building Terno AI"
tags: [enterprise-ai, security, data-privacy, architecture, terno-ai]
excerpt: >
  Many AI applications are impressive in demonstrations but become dangerous when
  connected to real enterprise data. Security cannot be an afterthought. Here is
  how I am thinking about building AI that enterprises can genuinely trust.
---

Here is a scenario that I think about often.

A company deploys an AI assistant connected to its internal data. Employees start
asking it questions. The system is useful and popular. Then, one day, someone asks
a question that the system was never designed to handle — and it answers anyway,
drawing on data that the questioner was never supposed to access.

No malicious intent. No external attacker. Just an AI doing what it was designed to do —
helping the user — in a situation where helping meant revealing something it should not.

This is not a hypothetical risk. It is a category of failure that any organisation
connecting AI to its data must take seriously. And I think the industry has not yet
fully reckoned with it.

## The Demo vs. Production Gap

AI applications for enterprise data analytics face a specific and underappreciated
challenge: the gap between what works in a demonstration and what is safe in production.

In a demonstration, you show the system answering questions correctly on a carefully
chosen dataset. The data is clean. The questions are well-posed. The access rules are
simple. Everything works as expected.

In production, the data is messy. The questions are unexpected. The users have varying
levels of access rights. There are sensitive columns and confidential rows. The system
operates continuously and handles requests from many users with different roles.

Many AI applications that look excellent in demos fail in one or more of these
dimensions when deployed for real enterprise use.

## What Genuine Enterprise Security Requires

When I talk about secure enterprise AI, I mean something more specific than just
encrypting data in transit or requiring authentication to use the system.

I mean the following:

**Data should stay in your environment.** The most sensitive enterprise data should
not need to leave the company's security perimeter to receive AI analysis. A system
that requires all data to flow to an external API creates both privacy risk and
compliance risk. Terno AI is designed to support deployment within the customer's
own private cloud or on-premises environment.

**Access controls must be deterministic, not AI-dependent.** Here is a subtle but
important point. If your system relies on an AI model to decide whether a user is
allowed to see a particular piece of data, you are trusting a probabilistic system
with a binary security decision. AI models can be prompted, confused, or led astray.
Access to sensitive data must be enforced through deterministic rules — not through
another model's judgment.

**Code execution must be sandboxed.** When AI systems can execute code, there is
potential for that code to interact with systems beyond its intended scope. A
well-designed analytical AI should execute code in a strict sandbox — with defined
resource limits, no ability to make network requests, no file system access beyond
what is explicitly permitted, and isolated from other users' computation.

**Audit logs must be maintained.** In enterprise contexts, it is not sufficient for
a system to be secure — it must also be auditable. You need to be able to answer:
who asked what, when, what analysis was run, and what was returned. This is both
a compliance requirement and a practical necessity for investigating anything unexpected.

**Security must cover the data, not just the interface.** A system can require login
and still leak data through its outputs. If an AI will answer any natural language
question by summarising data, a sophisticated user can effectively reconstruct
sensitive information through a series of carefully posed queries. Real security
requires thinking about what information can be inferred from outputs, not just
what data is directly returned.

## The Semantic Layer and Security

There is a connection between data security and the semantic layer that I have come
to find important.

A well-designed semantic layer does not just improve accuracy. It also provides a
natural place to enforce data governance rules.

When the system has an explicit, maintained model of what each piece of data means —
what tables exist, what columns contain, what data is sensitive, what access a
particular user role should have — security rules can be expressed and enforced at
the level of meaning rather than just at the level of raw tables and columns.

A user who should not see salary data should be prevented from accessing any analysis
that would reveal it — even indirectly, even through an aggregation that seems
innocuous, even through a question that does not mention "salary" but could
reconstruct the information.

This kind of protection is much harder to implement when security is bolted on to
a system as an afterthought. It requires being designed in from the beginning.

## The Trust Problem Is the Hard Problem

I believe the central challenge of enterprise AI is not capability. Current AI systems
can perform impressive analytical work.

The central challenge is trust.

For an enterprise to genuinely rely on an AI system for analytical work that drives
real decisions, they need to trust that the system will be correct when it matters,
that it will not leak data it should not reveal, that its behaviour is predictable
and auditable, and that it will fail safely and visibly rather than silently and dangerously.

Building AI systems that deserve this trust requires making different choices at every
layer of the design — from how data is stored and accessed, to how code is generated
and executed, to how outputs are validated before they are returned.

This is harder than building impressive demos. But it is the only kind of enterprise
AI that is genuinely worth building.

---

*This essay is part of my ongoing writing about what I am learning while building
Terno AI. For more on the technical approach, see my essay on
[why AI should generate code rather than guess answers](/essays).*
