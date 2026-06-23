---
title: Marketing department build - tracker
area: agent-org
tags: [project, agents, marketing, hermes]
status: active
stage: Realised in Orwell-Corp through B15 on mock data; next phase is the build-next plan from B16
next_action: Run B16 (reduce to three) and S1 (skills layer); see [[reference/orwell-corp-stack-decisions]]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-23
---

# Marketing department build

The first humanless department: recommendation-only marketing agents across Cluster A and Cluster B. Parent of [[projects/hermes-compare-reporting/hermes-compare-reporting]], the Cluster B reporting slice. Sits under [[areas/agent-org/agent-org]].

## Update 2026-06-23: realised in Orwell-Corp, next phase set

The department is realised in the `ngindubai/Orwell-Corp` repo, built through B15 on mock data: the Command Centre dashboard, the Neon warehouse, the connectors, the reports, and seventeen agents (more than the original ten). The Next.js dashboard, dropped in the early plan, was re-added and is part of the repo. The settled stack and the next-phase plan are in [[reference/orwell-corp-stack-decisions]], and the skills layer that sharpens the agents is in [[research/agent-skills-ecosystem]].

## The one goal

A marketing department of agents that reads the sites, analyses, and writes recommendations to the warehouse and to reports, on a schedule, via Hermes, never touching anything live.

## What was decided

- Keep the recommendation-only agents, the recommendation schema, the Neon Postgres and pgvector warehouse, and the connector set.
- Hermes is the single orchestrator. The dashboard was re-added as the Command Centre.
- Recommendation-only is enforced by withholding the publish and send tools from the Hermes toolset, not by instruction alone. Even a confused agent cannot touch anything live.
- Token model: read-only on the site repos, read/write only on the Orwell-Corp repo. Agents read the sites, never write to them.
- Mock data by design for the build; real connectors and the removal of mock come in the next phase (B21 to B24).

## Hermes fit (verified)

- Installs natively on Windows; moving to a Hostinger VPS in the next phase so it runs always-on.
- Agent identity file is literally `SOUL.md`, so the souls pattern maps straight on. See [[areas/agent-org/workforce-souls]].
- Has a cron tool for the daily runs. Takes GitHub through an MCP entry with a token.
- Routine work routes to the Hermes 4 70B model, deep thinking to Claude. See [[reference/orwell-corp-stack-decisions]].

## Next actions

1. Run B16 (reduce to three) and S1 (skills layer).
2. Stand up the cloud (B17 to B19), harden and gate go-live (S2), cut the PC over (B20).
3. Make the data real (B21 to B24), then the deeper report, Processes tab and exports (B25 to B27).
4. Keep the Cluster B reporting slice in step: [[projects/hermes-compare-reporting/hermes-compare-reporting]].

Source: chat 8ed658bc and the 23 June stack-settle session.
