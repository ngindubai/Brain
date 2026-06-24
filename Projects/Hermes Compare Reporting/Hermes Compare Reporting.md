---
title: Hermes Compare Reporting
area: Comparison Network
tags: [project, hermes, reporting, agent-autonomy]
status: active
stage: Wire Hermes (B8) and reports (B9) for Cluster B
next_action: Confirm warehouse deployed, run B8
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-24
---

# Hermes Compare Reporting

Parent: [[Marketing Department]]. Area: [[Comparison Network]].

## The one goal

Get Hermes running the reporting routine for the compare sites on a schedule, recommendation-only, so the morning read-out and the deck update without me babysitting Claude Code.

## What we have learnt

- **Three-layer stack.** Brain to hands (Claude Code and the API, the only thing that builds) to operations (Hermes: scheduling, memory, no routine cap). Hermes orchestrates and calls a model, so quality still needs Claude behind it.
- **Hermes is the single orchestrator.** Node/BullMQ and the Next.js dashboard were dropped.
- **10 recommendation-only agents.** They read, analyse, and write to the warehouse. They never publish, send, post, or edit a live site.
- **Two clusters.** Cluster A lead-gen sites, Cluster B the UAE finance and compare sites. Shared role library, memory isolated per business.
- **Render Postgres warehouse.** Every reporting routine dual-writes: human-readable to Slack, machine-readable JSON to a private data repo. The deck reads the repo.
- **Reporting depth.** Weekly SEO and lead-flow report, 5 edits per site, resilience structural so one site's failure never stops the others.
- **Hermes installed on Windows and confirmed correct.** The only snag was typing into PowerShell instead of a Hermes session.

## The plan (reporting-critical steps of B1-B10)

- [ ] Warehouse live on Render (Postgres, metric_snapshots schema)
- [ ] Read-only CRM and data adapters feeding the warehouse
- [ ] 10 recommendation agents defined (shared role library)
- [ ] Recommendation scoring with a needs_human_review flag on any rate or finance claim
- [ ] **B8 Wire Hermes:** SOUL.md, delegation.md, hermes-config-snippet.yaml (read-only PAT, daily cron, restricted toolset), RUN.md
- [ ] **B9 Reports:** daily and weekly, markdown and HTML, per business and per cluster, accent `#2752E6`, optional Slack post
- [ ] Dual-write block added to each compare site CLAUDE.md
- [ ] First Hermes run, one business by hand
- [ ] Daily cron on for Cluster B once trusted

## Progress

**Done:** Hermes installed and verified; build plan written; reporting prompts expanded to the compare sites (5 edits, resilience structural); warehouse and dual-write architecture designed; roster and clusters mapped.

**Frontier:** Hermes config wired and a real run executed (B8); reports generating via Hermes (B9); daily cron live.

## Next actions

1. Confirm the warehouse is deployed on Render and reachable.
2. Run B8: generate the Hermes config, paste into `~/.hermes/config.yaml`, set the read-only PAT.
3. Trigger one compare site by hand, check rows land in the warehouse.
4. Run B9, render a report from seeded data.
5. Add the dual-write block to each compare site CLAUDE.md.
6. Cron on for Cluster B only, watch one cycle, then widen.

## Open questions

- Warehouse deployed yet, or still local design?
- Report channel: keep #reports-mortgage-compare-seo or stand up #reports-portfolio-seo?
- LoanCompare.ae in or out (no repo yet)?

## Connector notes

- **Windsor** GA4 and GSC are runtime-only. Absent in a chat does not mean broken.
- **Semrush:** overview_research, then get_report_schema, then execute_report. Database `us` for global, `ae` for the .ae sites. Fails silently when out of units.
- **GitHub MCP:** branch and SHA on writes. `.github/workflows` 403, edit by hand. No binary commits. closeprotection uses `master`, pet-transport `main`.
- **Hermes toolset** grants no publish, send, post or edit. Read, analyse, write-to-warehouse only.
