---
title: Agent org
area: agent-org
tags: [area, agents, humanless, hermes]
updated: 2026-06-22
---

# Agent org

The humanless-company engine: how Orwell's businesses get staffed by AI agents in every department role. This is the area behind the north star, 80% agent-staffed at a tenth of human cost.

## The model in one view

- **Three-layer stack.** Brain (Opus and Projects) to hands (Claude Code and the API, the only builder) to operations (Hermes, always-on scheduling and memory, no routine cap). See [[areas/agent-org/three-layer-stack]].
- **Souls.** Each business runs a roster of named agents, "souls", across departments. pet-transport has 14 live across 6 departments, with 7 more to build. See [[areas/agent-org/workforce-souls]].
- **Shared role library, isolated memory.** Role definitions shared across a cluster, invocations per task, memory always isolated per business. Cluster A is the five lead-gen sites, Cluster B the UAE finance sites.
- **Data layer.** A production Postgres warehouse off the laptop. See [[areas/agent-org/warehouse-architecture]].
- **First department to ship: marketing.** Ten recommendation-only agents. See [[projects/marketing-department/plan]], and the Cluster B reporting slice [[projects/hermes-compare-reporting/plan]].

## Repos

- `ngindubai/orwell-marketing` (new, read/write for the agents)
- `ngindubai/pet-transport` (the souls reference implementation, read-only to agents)

## Source documents

- Hermes workflow and the three-layer stack: chat 1b691260 (15 June)
- Warehouse, souls and marketing department: chat 8ed658bc (20 June)

## Open loops

- Build the 7 missing souls (6 Sales plus The Indexer).
- Stand up the warehouse on managed Postgres (Neon).
