---
title: Humanless company design
area: agent-org
tags: [agents, humanless, design, architecture]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-22
---

# Humanless company design

From "The Humanless Company" build plan, 19 June. The design behind running a whole company with no humans in the seats. Companion to [[areas/agent-org/agent-behaviour-design]] ("The Glass Office").

## The core idea: the schema is the company

Design the data contract first. Not the agents, not the visualiser, not the orchestration. The schema is the company's nervous system; everything else is muscle attached to it. Get it right and you can swap models, swap orchestrators, and add departments without rewriting the business.

Why the data model carries the company:

- **Continuity and learning** live in stored state.
- **Coordination substrate.** Agents hand work to each other by writing to shared state, not by chatting.
- **Audit trail.** With no humans in the seats, the record of who did what is the only accountability.
- **The org design itself.** The schema encodes who exists, what they may touch, and how work moves. Structure lives in the data model, not in prose.

## The warehouse: six layers, only one of them storage

1. System of record
2. Knowledge and SOPs
3. Memory
4. Work state
5. Event and audit log
6. Artefact store

Build it first, before any agent. See [[areas/agent-org/warehouse-architecture]].

## Where it runs, and the split that keeps the company alive

Orchestration is replaceable compute. The warehouse is the company.

- **On his hardware: Hermes.** Cron, dispatch, self-learning skills, the event watcher.
- **In managed cloud: the warehouse.** Replicated, backed-up Postgres, never on the mini PC. A humanless company whose entire memory sits on one unbacked machine is one power supply away from not existing.

## Billing

Run Hermes against the Claude API, not the subscription. The API is built for headless, always-on work, carries no interactive caps, and supports prompt caching and Batch where the real savings sit. The June 2026 billing change moved automated agent usage onto API credits anyway. Model mix: Sonnet 4.6 for most work, Opus 4.8 for hard reasoning, Haiku 4.5 for cheap high-volume steps, caching on the fixed scaffolding.

## Inter-department comms: blackboard, not chat

Departments read and write shared state with a status field. Nobody messages anyone. This is the lesson the agent-society experiments paid for (AI Village, Emergence World): left to talk freely, agents drift, form odd dynamics, and get stuck. Structured channels are auditable, replayable, and resilient to a crashed agent.

## The work pipeline

The seven-step workflow renders as a pipeline where every step is a read from or write to a specific warehouse layer, including the rejection and retry loop and the memory write-back that makes the company learn. Shape worth noticing: steps 1 to 4 are cheap reads, step 5 is the only place cost happens, 6 and 7 are checks and writes.

## The framing: a factory, not a company

Build the operating system as the asset. Each business is a configuration of it: clone the template, swap the domain tables and SOPs. He runs a portfolio, so the OS is what compounds.

Source: chat 8ed658bc. The full original HTML lives in that conversation.
