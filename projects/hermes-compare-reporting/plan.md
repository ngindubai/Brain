---
title: Hermes compare-site reporting - tracker
area: comparison-network
tags: [project, hermes, reporting, agent-autonomy]
updated: 2026-06-22
---

# Hermes: compare-site reporting

## The one goal

Get Hermes running the reporting routine for the compare sites on a schedule, recommendation-only, so the morning read-out and the deck update without me babysitting Claude Code.

## Where this came from

Built from sessions across 15 to 20 June: the Hermes workflow stack, the reporting-prompt expansion, the George / NGIN command deck, and the `marketing-department-build.md` B1-B10 plan. No session timestamped today was found in history, so confirm the checkboxes below against your latest run.

## What we have learnt

- **Three-layer stack.** Brain (Opus and Projects) to hands (Claude Code and the API, the only thing that builds) to operations (Hermes: scheduling, memory, monitoring, no routine cap). "Opus prompts, Hermes builds" was backwards. Hermes orchestrates and calls a model, so quality still needs Claude behind it.
- **Hermes is the single orchestrator.** Node/BullMQ and the Next.js dashboard were dropped.
- **The department is 10 recommendation-only agents.** They read, analyse, and write to the warehouse. They never publish, send, post, or edit a live site.
- **Two clusters.** Cluster A is the lead-gen sites, Cluster B is the UAE finance and compare sites. Shared role library, memory isolated per business.
- **Data layer is a Render Postgres warehouse.** Every reporting routine dual-writes: human-readable to Slack, machine-readable JSON to one private data repo. The deck reads the repo, not the Slack messages.
- **Reporting depth.** Weekly SEO and lead-flow report covers all businesses, 5 edit recommendations per site (down from 10). Resilience is structural: one site's data failure never stops the others.
- **Hermes is installed on Windows and confirmed correct.** The only snag was typing into PowerShell instead of a Hermes session.

## The plan (the reporting-critical steps of B1-B10)

Run as the `marketing-department-build.md` cascade in Claude Code.

- [ ] Warehouse live on Render (Postgres, metric_snapshots schema)
- [ ] Read-only CRM and data adapters feeding the warehouse
- [ ] 10 recommendation agents defined (shared role library)
- [ ] Recommendation scoring with a needs_human_review flag on any rate or finance claim
- [ ] **B8 Wire Hermes:** SOUL.md, delegation.md, hermes-config-snippet.yaml (GitHub MCP read-only PAT, daily cron, delegation block, restricted toolset), RUN.md
- [ ] **B9 Reports:** daily and weekly, markdown and HTML, per business and per cluster. Exec overview, top recommendations by priority score, new technical issues, content briefs, LLM visibility movement, accent `#2752E6`, optional Slack post
- [ ] Dual-write block added to each compare site CLAUDE.md (from the MortgageCompare template)
- [ ] First Hermes run, one business by hand
- [ ] Daily cron turned on for Cluster B once trusted

## Progress (confirm against your latest run)

**Done, from the sessions:**

- Hermes installed and verified on Windows
- Build plan written (marketing-department-build.md, B1-B10)
- Reporting prompts expanded to the compare sites, edits cut to 5, resilience made structural
- Warehouse and dual-write architecture designed
- Agent roster and clusters mapped

**Frontier, likely not done:**

- Hermes config actually wired and a real run executed (B8)
- Reports generating from the warehouse via Hermes (B9)
- Daily cron live

## Remaining tasks (next actions)

1. Confirm the warehouse is deployed on Render and reachable.
2. Run B8 in Claude Code: generate the Hermes config snippet, paste into `~/.hermes/config.yaml`, set the read-only PAT.
3. Trigger one compare site by hand (RUN.md), check the recommendation rows land in the warehouse.
4. Run B9, generate a report from seeded data, confirm the HTML renders.
5. Add the dual-write block to each compare site CLAUDE.md.
6. Turn the daily cron on for Cluster B only, watch one cycle, then widen.

## Open questions

- Is the warehouse deployed yet, or still local design?
- Consolidated report channel: keep posting to `#reports-mortgage-compare-seo`, or stand up `#reports-portfolio-seo`?
- LoanCompare.ae still has no repo. Include with a degradation note, or leave out?

## Connector notes (so a run does not stall)

- **Windsor** GA4 and GSC are runtime-only. Absent in a chat session does not mean broken.
- **Semrush:** overview_research, then get_report_schema, then execute_report. Database `us` for global domains, `ae` for the .ae sites. Fails silently when out of units, top up at semrush.com/mcp-access.
- **GitHub MCP:** branch and SHA on writes. `.github/workflows` returns 403, edit by hand. No binary commits. No repo creation. closeprotection uses `master`, pet-transport uses `main`.
- **Hermes toolset** must grant no publish, send, post or edit capability. Read, analyse, and write-to-warehouse only.
