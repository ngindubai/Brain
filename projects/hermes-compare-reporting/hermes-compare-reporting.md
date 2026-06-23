---
title: Hermes compare-site reporting - tracker
area: comparison-network
tags: [project, hermes, reporting, agent-autonomy]
status: active
stage: Stack settled (Hostinger + RunPod 70B + Neon); next phase is the Orwell-Corp build-next plan
next_action: Run B16 (reduce to three) and S1 (skills layer); see [[reference/orwell-corp-stack-decisions]]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-23
---

# Hermes: compare-site reporting

Parent: [[projects/marketing-department/marketing-department]]. Area: [[areas/comparison-network/comparison-network]].

## Update 2026-06-23: stack settled, next phase

The architecture is now settled and recorded in [[reference/orwell-corp-stack-decisions]]. Headlines, which correct earlier notes below:

- **Warehouse is Neon, not Render.** Already cloud and always on.
- **Hosting:** Hermes Agent and the Command Centre dashboard on a Hostinger VPS; the Hermes 4 70B model on a RunPod GPU; Claude for the deep thinking (Sonnet default, Opus hardest). Not Render.
- **The dashboard stays.** The Command Centre is part of the realised Orwell-Corp repo, built through B15 on mock data.
- **SEMrush is being removed for now;** Search Console takes over keyword duty (no true volume or difficulty until SEMrush returns).
- **Skills layer added** (S1): maintained, pinned, audited skills incl. ai-seo and schema-markup. See [[research/agent-skills-ecosystem]].
- **Next phase is the build-next plan** B16 to B27 plus S1 and S2. Reduce to three, install skills, move to the cloud, harden, then make the data real and add the new surfaces.

## The one goal

Get Hermes running the reporting routine for the compare sites on a schedule, recommendation-only, so the morning read-out and the deck update without me babysitting Claude Code.

## Where this came from

Built from sessions across 15 to 20 June: the Hermes workflow stack, the reporting-prompt expansion, the George / NGIN command deck, and the `marketing-department-build.md` B1-B10 plan. The Orwell-Corp repo has since been built through B15.

## What we have learnt

- **Three-layer stack.** Brain (Opus and Projects) to hands (Claude Code and the API, the only thing that builds) to operations (Hermes: scheduling, memory, monitoring, no routine cap). Hermes orchestrates and calls a model, so quality still needs Claude behind it.
- **Hermes is the single orchestrator.** Node/BullMQ was dropped. The Next.js dashboard was later re-added and is part of Orwell-Corp.
- **The department is recommendation-only agents.** They read, analyse, and write to the warehouse. They never publish, send, post, or edit a live site.
- **Two clusters.** Cluster A is the lead-gen sites, Cluster B is the UAE finance and compare sites. Shared role library, memory isolated per business.
- **Data layer is a Neon Postgres warehouse** (earlier notes said Render; corrected 23 June). Reporting routines dual-write: human-readable to Slack, machine-readable to the warehouse; the deck reads the warehouse.
- **Reporting depth.** Weekly SEO and lead-flow report covers all businesses, 5 edit recommendations per site. Resilience is structural: one site's data failure never stops the others. The deeper report (B25) adds internal links, programmatic pages, GEO, schema and week-on-week and month-on-month.

## Remaining tasks (next actions)

1. Run B16 (reduce to the three compare sites, prune the rest) and S1 (skills layer).
2. Stand up the Hermes 4 70B endpoint on RunPod (B17), then the Hostinger VPS with Hermes Agent and two models (B18).
3. Move the dashboard to the VPS and reports into the warehouse (B19), then harden and gate go-live (S2).
4. Cut the PC over (B20).
5. Remove SEMrush and wire real GSC and GA4 (B21 to B22), add history and timeframe filtering (B23), remove all mock (B24).
6. Build the deeper report (B25), the Processes tab (B26), and the export connectors (B27).

## Open questions

- Google credentials for the three sites: Search Console share and GA4 property IDs.
- Consolidated report channel: keep `#reports-mortgage-compare-seo`, or stand up `#reports-portfolio-seo`?
- Dashboard host: Hostinger VPS (planned) or Vercel.

## Connector notes (so a run does not stall)

- **GA4 and GSC** real providers are not yet built in the repo (they stop with a "not yet wired" error). B22 builds them.
- **SEMrush** is being removed for now; Search Console supplies keywords in the meantime.
- **GitHub MCP:** branch and SHA on writes. `.github/workflows` returns 403, edit by hand. No binary commits. No repo creation. closeprotection uses `master`, pet-transport uses `main`.
- **Hermes toolset** must grant no publish, send, post or edit capability. Read, analyse, and write-to-warehouse only.
