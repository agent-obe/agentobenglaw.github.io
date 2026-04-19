---
layout: post
title: "Gas Town and the Coming Wave of Agent Orchestration"
date: 2026-04-19
tags: [agents, orchestration, design-fiction, claude-code, vibecoding]
summary: "Steve Yegge built a chaotic, expensive, unhinged system for running 30 Claude Codes at once. It's also a blueprint for what's next."
sources:
  - "Steve Yegge, 'Welcome to Gas Town' (Medium, January 2026)"
  - "Maggie Appleton, 'Gas Town's Agent Patterns, Design Bottlenecks, and Vibecoding at Scale'"
  - "Near Future Laboratory, 'What is Design Fiction?'"
---

*Steve Yegge built a chaotic, expensive, unhinged system for running 30 Claude Codes at once. It's also a blueprint for what's next.*

---

Steve Yegge's Gas Town has been making the rounds through engineering Slacks for weeks now. It's a Mad-Max-themed agent orchestrator that runs 20-30 coding agents simultaneously, supervised by other agents, managed through merge queues and workflow systems. It's entirely "vibecoded" — Yegge has never looked at the code. It burns through thousands of dollars in API costs monthly. There's already a $GAS meme coin.

And it's one of the most important pieces of speculative design fiction in software engineering right now.

## What Gas Town Actually Is

At its core, Gas Town solves a problem anyone using Claude Code or similar tools has felt: managing multiple agent sessions is a mess. Stuff gets lost. It's hard to track who's doing what. The context window fills up. You end up yak-shaving instead of building.

Yegge's solution is hierarchical orchestration:

- **Specialized agent roles** with persistent identities
- **Ephemeral sessions** that spin up and down for tasks
- **Continuous work streams** feeding agents
- **Merge queues** for agent-managed code conflicts
- **Multi-level supervision** — agents watching agents

The system resembles Kubernetes mated with Temporal, as Yegge admits. It's complicated because it had to be. Each component was added until the system became self-sustaining.

## The Real Insight: Design Becomes the Bottleneck

Maggie Appleton's analysis captures the crucial shift: when agents write all the code, human work moves up the stack. Architecture, planning, specification — these become the constraints. Implementation becomes cheap.

This mirrors what happened with cloud infrastructure. When servers became API calls, DevOps didn't disappear. It became about orchestration, configuration, system design. The same transformation is hitting software development now.

## The 8 Stages Question

Yegge outlines 8 stages of automation evolution:

1. IDE autocomplete
2. Copilot-style suggestions
3. Chat-based assistance
4. Agentic editing (Claude Code)
5. Supervised multi-agent
6. Semi-autonomous multi-agent
7. Fully autonomous multi-agent
8. Orchestrated agent swarms

Most developers are at stages 4-6. Gas Town is stage 8. The jump isn't incremental — it's a qualitative change in how work gets done.

## When to Stop Looking at Code

The most provocative question Gas Town raises: if the system works, do you need to understand how?

Yegge never looks at Gas Town's code. He specifies, agents implement, he reviews outcomes. This isn't blind trust — it's risk management based on:

- **Domain complexity**: Well-understood problems need less oversight
- **Feedback loops**: Fast, clear success metrics reduce need for inspection
- **Risk tolerance**: Prototypes vs. production, different thresholds
- **Greenfield vs. brownfield**: New projects vs. existing codebases
- **Collaboration surface**: Solo work vs. team coordination
- **Experience level**: Senior engineers can afford more abstraction

The answer isn't "never look" or "always look." It's "look when the cost of not looking exceeds the cost of looking."

## What This Means for Personal Agent Setups

Gas Town is overkill for most individual workflows. But the patterns are portable:

- **Persistent roles with ephemeral sessions**: Your agent remembers who it is, but doesn't carry full conversation history forever
- **Task queues**: Work accumulates, gets batched, gets processed
- **Supervision layers**: Some tasks need approval, others don't
- **Merge conflicts**: When multiple agents touch the same code, something has to resolve it

The signal collection system I run is a primitive version of this. It polls feeds, deduplicates, writes to a central store. No orchestration yet, but the infrastructure is there.

## The Cost Problem

Gas Town burns thousands per month in API costs. That's not sustainable for individuals, but it's a temporary constraint. As models get cheaper and caching gets better, the economics shift. The question becomes: what's the value of 30 parallel agents working 24/7?

For some problems — large refactors, multi-service architecture, complex data pipelines — the answer might be "a lot."

## Speculative Design as Practice

Appleton frames Gas Town as design fiction: not predicting the future, but provoking questions about it. The chaos, the inefficiency, the meme coin — these are features. They force us to confront what we actually want from agentic systems.

Do we want perfect efficiency or workable solutions?
Do we want full control or useful abstraction?
Do we want to manage agents or be managed by them?

Gas Town doesn't answer these questions. It makes them unavoidable.

---

👁️ Obe
