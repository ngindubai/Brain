---
title: Agent Org
area: Agent Org
tags: [area, agents, humanless, hermes]
updated: 2026-06-24
---

# Agent Org

The humanless-company engine: how Orwell's businesses get staffed by AI agents in every department role. This is the area behind the north star, 80% agent-staffed at a tenth of human cost.

## The model in one view

- **Three-layer stack.** Brain (Opus and Projects) to hands (Claude Code and the API, the only builder) to operations (Hermes, always-on scheduling and memory, no routine cap). See [[Three Layer Stack]].
- **The schema is the company.** Design the data contract first; structure lives in the data model. See [[Humanless Company Design]].
- **Behaviour is constrained by design.** Blackboard coordination, recommendation-only by tool-withholding, watchdog QC. See [[Agent Behaviour Design]].
- **Souls.** Each business runs a roster of named agents across departments. pet-transport has 14 live across 6 departments, with 7 more to build. See [[Workforce Souls]].
- **Shared role library, isolated memory.** Role definitions shared across a cluster, invocations per task, memory always isolated per business. Cluster A is the five lead-gen sites, Cluster B the UAE finance sites.
- **Data layer.** A production Postgres warehouse off the laptop, six layers. See [[Warehouse Architecture]].
- **First department to ship: marketing.** Ten recommendation-only agents. See [[Marketing Department]], and the Cluster B reporting slice [[Hermes Compare Reporting]].

## Design docs

- [[Humanless Company Design]] - The Humanless Company (19 June)
- [[Agent Behaviour Design]] - The Glass Office (companion)
- [[Three Layer Stack]] - Claude and Hermes (15 June)
- [[Warehouse Architecture]] - the data layer
- [[Workforce Souls]] - the roster

## Repos

- `ngindubai/orwell-marketing` (new, read/write for the agents)
- `ngindubai/pet-transport` (the souls reference implementation, read-only to agents)

## Source conversations

- Hermes workflow and the three-layer stack: chat 1b691260 (15 June)
- Humanless company, Glass Office, warehouse, souls, marketing department: chat 8ed658bc (19 to 20 June)

## Open loops

- Build the 7 missing souls (6 Sales plus The Indexer).
- Stand up the warehouse on managed Postgres (Neon), six layers.
- Build the QC watchdog and circuit-breaker layer.
