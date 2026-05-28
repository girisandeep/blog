---
layout: post
title: "Building an Open-Source Autonomous Agent SDK"
category: "Agentic Systems"
tags: [agents, ai, open-source, sdk, autonomous-systems, tools]
excerpt: >
  Agentic AI systems are becoming genuinely capable. But the infrastructure for
  building reliable, auditable, multi-tool agents remains immature. Here is how I
  am thinking about what a useful open-source agent SDK should look like.
---

We are at an interesting moment in the development of AI.

The underlying models — the large language models that reason, write code, and
follow complex instructions — have reached a capability level where they can be
genuinely useful for tasks that require multiple steps, tool use, and judgment.

But the infrastructure for building agentic systems — systems that can plan, take
actions, use tools, remember context, and operate autonomously toward a goal —
remains surprisingly immature.

Existing frameworks make certain things easy. But they often sacrifice transparency
for convenience, or make it hard to audit what the agent actually did and why.

I have been thinking about what a well-designed open-source agent SDK would look like.
Here are my current thoughts.

## What Makes a Good Agent

Before thinking about the SDK, it helps to be clear about what a good agent actually is.

An agent is a system that can:
1. Receive a goal or task in natural language
2. Decompose that task into steps
3. Execute those steps using available tools
4. Observe the results of each step
5. Adjust its plan based on what it observes
6. Complete the task or report why it cannot

This sounds simple. But building a system that does this reliably — that does not
hallucinate tool calls, that handles errors gracefully, that does not lose track of
the original goal, that can be safely stopped or interrupted — is genuinely hard.

The hardest parts are:

**Planning under uncertainty.** The agent must decide what to do next without full
information about whether its previous steps worked as intended, and without certainty
about what future steps will be needed.

**Tool reliability.** Tools fail, return unexpected outputs, or produce results that
require interpretation. The agent must handle this gracefully.

**Context management.** Long tasks require the agent to maintain coherent state over
many steps. Current language models have context windows that become a bottleneck in
long tasks.

**Safety and auditability.** For any serious use case, you need to be able to inspect
what the agent did, why it made the decisions it made, and where things went wrong.

## What Current Frameworks Get Wrong

Most current agent frameworks optimise for getting demos working quickly. This is
understandable — demos attract attention and demonstrate capability. But it creates
problems when you try to use these frameworks for production work.

**Opacity.** Many frameworks make it easy to run an agent but hard to understand what
it is doing internally. You get an output, but you cannot easily reconstruct the
reasoning chain that produced it.

**Tight coupling.** Frameworks often tightly couple the agent logic to a specific
model provider or a specific tool interface. This makes it hard to swap components,
run tests with mock tools, or migrate between providers as models improve.

**Weak error handling.** When a tool fails or returns unexpected output, many frameworks
either crash or retry indefinitely. Production agents need explicit, configurable
error handling at every step.

**No audit trail.** For enterprise or safety-critical applications, you need a complete
record of what the agent did — every tool call, every observation, every decision.
Most frameworks treat this as an afterthought.

## What a Good SDK Should Provide

Based on these observations, here is what I think a good open-source agent SDK should
prioritise:

**Explicit, inspectable state.** Every step of the agent's reasoning and action should
be represented as an explicit, serialisable data structure. You should be able to pause
an agent, inspect its complete state, and either resume it or understand what it did.

**Composable tools with typed interfaces.** Tools should be defined with explicit input
and output types, validation logic, and error handling. The agent should be able to
discover available tools and understand their capabilities from their definitions.

**Modular planning.** The planning component should be separated from the execution
component. This makes it possible to test planning logic without running tools, and to
swap planning strategies without changing execution code.

**First-class memory.** Long-running agents need to store and retrieve information across
steps. This should be a first-class concept — not an afterthought implemented by
appending to a prompt.

**Permission model.** Different tools should have different permission levels. A tool that
reads a file is different from a tool that writes one, which is different from a tool
that makes a network request. The agent should require explicit authorisation for
operations above a certain permission level.

**Complete audit logging.** Every action taken by the agent — including its internal
reasoning, tool calls, observations and decisions — should be logged in a structured
format that can be queried and analysed.

## The Memory Problem

One of the most underappreciated challenges in building agentic systems is memory.

Language models do not have persistent memory. Everything they know about the current
task must be present in their context window at the time of each call. For short tasks,
this works fine. For long tasks, it becomes a serious bottleneck.

A good agent SDK should provide abstractions for different types of memory:

**Working memory** — the current state of the task, including the goal, the steps
completed so far, and the current plan.

**Episodic memory** — records of past interactions that may be relevant to the current
task. The agent should be able to retrieve relevant past episodes when they are helpful.

**Semantic memory** — general knowledge about the domain, the user's preferences, and
the tools available.

**Procedural memory** — learned patterns for how to accomplish common subtasks.

These do not need to be implemented as separate systems. But they need to be thought
about as distinct concepts, because the criteria for what to store, when to retrieve,
and how to keep them current are different for each.

## Interface Diversity

I am also interested in agents that can interact through multiple interfaces: not just
a chat window, but a command line, a browser, an API, or a messaging application.

A well-designed agent should be able to adapt its behaviour to the interface it is
operating through. The way you express a complex analytical task through a terminal
command is different from the way you express it through a conversational interface.
An agent that is tightly coupled to one interaction model will be limited in how it
can be deployed.

## What I Am Working Toward

I do not have a complete answer yet. But I find the design space of reliable,
transparent, composable agent systems genuinely interesting — and I think there is
real value to be created by building infrastructure that makes it easier to build
agents that work well in production, not just in demos.

If you are building in this space, I would be glad to compare notes.

---

*This essay is part of my writing on Agentic Systems. The ideas here connect to
the design work I am doing at Terno AI around secure, auditable AI workflows.*
