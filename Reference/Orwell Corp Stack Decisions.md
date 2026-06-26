---
title: Orwell Corp stack decisions
tags: [reference, decision-record, orwell-corp, agent-org, hermes, hosting]
updated: 2026-06-24
related:
  - "[[Agent Org]]"
  - "[[Products]]"
  - "[[Comparison Network]]"
  - "[[Ventures]]"
  - "[[Hermes Agent Personal AI OS]]"
  - "[[Agent Skills Ecosystem]]"
  - "[[Hermes Compare Reporting]]"
  - "[[Marketing Department]]"
source: Architecture sessions, 23 June 2026
---

# Orwell Corp Stack Decisions

Durable record of the settled architecture for the Orwell-Corp repo (`ngindubai/Orwell-Corp`), the realised version of the [[Agent Org]] engine. Supersedes earlier "Render" and "Node/BullMQ" assumptions in the trackers. This is the meta-record; the executable plan lives in the repo as the build-next plan and the dossier.

## The two Hermes things (settled)

- **Hermes the model** is Nous Research's open-weight LLM family (Hermes 3, Hermes 4). A brain you host.
- **Hermes Agent** is Nous Research's model-agnostic agent runtime: `~/.hermes/config.yaml`, skills, memory, cron, delegation, MCP. This is what is installed, and it runs any model.
- The "self-learning" is the runtime writing and refining its own skills plus persistent memory, not a model retraining itself. See [[Hermes Agent Personal AI OS]].

## The topology (decided 23 June)

| Part | Runs on | Job |
|---|---|---|
| Warehouse | Neon Postgres and pgvector (already cloud) | Data, recommendations, memory, history |
| Routine model | Hermes 4 70B via vLLM on a RunPod GPU | The cheap, repetitive thinking |
| Runtime and dashboard | Hostinger KVM VPS (always on) | Hermes Agent runs the company; the Command Centre is served from the same box |
| Deep thinking | Claude API, Firswoods key, Sonnet 4.6 default, Opus 4.8 hardest | Called by Hermes only for judgement |

Corrections to older notes: the warehouse is **Neon, not Render**; hosting is **Hostinger plus RunPod, not Render**; the dashboard stays (it was not dropped). Hostinger has no GPU, so the model sits on a GPU host now and moves to a dedicated machine later.

## Model routing for token economy

Main and orchestrator steps on Claude; leaf and routine subagents on the Hermes 4 70B; only summaries return to the parent; caching on the briefs. "Hermes runs the routine, Claude does the thinking."

## Cost (June 2026 estimate, confirm at source)

Hostinger VPS $7 to $20; RunPod serverless GPU for a daily run $25 to $100; Claude thinking $20 to $120; Neon free to about $19. Typical total about $60 to $250. A 405B model is roughly ten times the GPU line and is not chosen.

## The build-next plan (headline)

- [ ] B16 reduce to the three compare businesses, prune the rest
- [ ] S1 skills layer: retire the static clones, install a pinned audited manifest, curator opt-in (see [[Agent Skills Ecosystem]])
- [ ] B17 stand up the Hermes 4 70B endpoint on RunPod
- [ ] B18 Hostinger VPS, Hermes Agent, two models, verification gate
- [ ] B19 dashboard on the VPS, reports off local disk into the warehouse
- [ ] S2 hardening and go-live gate: web app testing, monitoring, VPS hardening
- [ ] B20 cut over, clean the PC
- [ ] B21 remove SEMrush, Search Console supplies keywords
- [ ] B22 build and verify the real GSC and GA4 connectors
- [ ] B23 warehouse history, week-on-week and month-on-month, timeframe filter
- [ ] B24 remove all mock, table by table
- [ ] B25 deeper weekly report (links, programmatic, GEO, schema, deltas)
- [ ] B26 Processes tab: run now, scheduler, worker souls, core files
- [ ] B27 export connectors for the intelligence dashboard
- [ ] Phase 2 (separate rules) the daily blog builder

## Honest dependencies (do not reorder)

- "Test GSC and GA4" means building them first; both real providers currently stop with a "not yet wired" error.
- Removing SEMrush removes the only keyword source; Search Console takes over, with no true volume or difficulty until SEMrush returns.
- "Remove all mock" cannot precede real connectors, or the system has no data.
- Reports must move off local disk; a cloud box wipes it on redeploy.
- Phase 2 publishing runs under its own rules, kept apart from the recommendation-only core.

## Open loops

- Hermes 4 70B vs 405B (70B chosen).
- Google credentials for the three compare sites (Search Console share, GA4 property IDs).
- Dashboard host: Hostinger VPS (planned) or Vercel.
