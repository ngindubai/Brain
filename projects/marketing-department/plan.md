---
title: Marketing department build - tracker
area: agent-org
tags: [project, agents, marketing, hermes]
status: active
stage: Plan and review docs produced; build runs B1-B10 in Claude Code on mock data
next_action: Do the five manual tasks, then run B1 in Claude Code and advance with "build next"
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-22
---

# Marketing department build

The first humanless department: ten recommendation-only marketing agents across Cluster A and Cluster B. Parent of [[projects/hermes-compare-reporting/plan]], the Cluster B reporting slice. Sits under [[areas/agent-org/_index]].

## The one goal

A marketing department of agents that reads the sites, analyses, and writes recommendations to the warehouse and to reports, on a schedule, via Hermes, never touching anything live.

## What was decided

- Keep the ten recommendation-only agents, the recommendation schema, the Postgres and pgvector warehouse, and the connector set (from the reconciled ChatGPT plan).
- Drop the Node/BullMQ orchestrator and the Next.js dashboard. Hermes is the single orchestrator. Output goes to the warehouse and reports first; a dashboard is a later phase.
- Recommendation-only is enforced by withholding the publish and send tools from the Hermes toolset, not by instruction alone. Even a confused agent cannot touch anything live.
- Token model: read-only on the nine site repos, read/write only on the new `orwell-marketing` repo. Agents read the sites, never write to them.
- Mock data by design. The whole loop can be proved without Search Console, GA4 or Semrush credentials. Wire those in later.

## Hermes fit (verified)

- Installs natively on Windows with one PowerShell line, no WSL.
- Agent identity file is literally `SOUL.md`, so the souls pattern maps straight on. See [[areas/agent-org/workforce-souls]].
- Has a cron tool for the daily runs.
- Takes GitHub through an MCP entry with a token.

## The plan

`marketing-department-build.md` is the executable cascade: drop it into Claude Code in an empty folder, say "build next" to advance one step at a time through B1 to B10. Each step commits and stops on its own. `marketing-department-build-plan.html` is the review copy.

## The five manual tasks (the only ones Claude Code cannot do)

1. The Firswoods API key
2. The Neon connection string
3. The GitHub token
4. Installing Hermes
5. Confirming Claude Code is present

Everything else, including turning on pgvector and creating the repo, is Claude Code's job.

## Cautions

- Hermes runs on a metered API key, no subscription pool. Set a spend limit in the Firswoods console before the first run, start with one business.
- Start on mock data, one business, then widen.

## Next actions

1. Do the five manual tasks.
2. Run B1 in Claude Code, advance with "build next".
3. Prove the loop on mock data for one business.
4. Wire the Cluster B reporting slice: [[projects/hermes-compare-reporting/plan]].

Source: chat 8ed658bc. The full original HTML review doc lives in that conversation.
