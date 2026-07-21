---
title: Build A Programmatic Site
tags: [websites, build, programmatic, flow]
updated: 2026-07-22
---

# Build A Programmatic Site

For demand that splits into a large matrix of entity pages: X to Y routes, service in City, product for Breed. Reference implementations: `ngindubai/pet-transport` (Hugo + Python, the origin of the method) and `ngindubai/pest-control-usa` (Next.js port, the cleanest current expression). Copy the newest reference, do not reinvent.

Entry point for a brand new topic: run [[New Site Kickoff Prompt]] first. It executes Phases 0 to 2 below and hands over a build plan.

## Phase 0. Keyword and demand research

- [ ] Define the entity matrix: what are the two axes (origin x destination, service x location)? Estimate total cell count.
- [ ] Pull keyword data: Semrush `phrase_these` batches (up to 20 terms per call, semicolon separated, columns keyword, volume, cpc, competitive_density, keyword_difficulty, intent) in the market database, or the in house keyword platform. Seed with the head term plus 10 to 20 entity samples.
- [ ] Score every cell into tiers: Tier 1 (high volume or high value corridors), Tier 2, Tier 3. Volume estimates may be logic based (population, expat flows, demand proxies) where tools have no data; mark them as estimates and validate against GSC once live.
- [ ] Capture CPC per cluster. CPC is the lead value proxy: it decides whether the site is worth building at all (see [[Opportunity Research Flow]] thresholds).
- [ ] Output: a scored keyword universe file committed to the repo `data/` directory, and a tier table in the build plan.

## Phase 1. Competitor research

- [ ] Identify the top 5 to 10 ranking competitors for the head term and 5 sample long tail cells (live web search, then Semrush organic research on each domain).
- [ ] Record per competitor: page count, page structure, schema use, what data their pages carry, what they are missing. The gaps become the information gain plan.
- [ ] Write the information gain thesis: the specific data every page of ours will carry that competitor pages do not (named regulations with codes, real costs in the correct currency, seasonality, named authorities, concrete process steps).
- [ ] Output: `data/competitors/competitor_analysis.html` in the repo.

## Phase 2. Architecture and scaffold

- [ ] Pick the stack. Default: Next.js 16 static export + TypeScript data files (the pest-control-usa pattern) for new builds; Hugo + Python remains valid. Locked once chosen.
- [ ] Page hierarchy: hub pages (origins, states), entity pages (routes, cities), supporting silos (airlines, breeds, services, blog). Cities before towns, Tier 1 before Tier 2.
- [ ] Scaffold the repo with every file in [[Repo Scaffold]]: CLAUDE.md (adapted from the reference site), BUILD-PLAN.md, build_state.json, MEMORY.md, ERRORS.md, workforce/ souls, scripts/ gates, data/ files.
- [ ] Build the 5 templates, A to E, structurally distinct: different section order, hero composition, FAQ placement and format, sidebar presence, schema type emphasis, one shared brand. Never a 6th template, never collapse two. Template assigned per page by slug hash, stored in the page's data record, share of corpus held between 15% and 25% per template.
- [ ] Wire deploy: GitHub Actions builds and publishes to a `live` branch (or FTP syncs), Hostinger serves it. Push to the production branch is the only trigger. Never edit `live` directly. Remember `.github/workflows/` returns 403 on the MCP connector; workflow files are pasted by hand.
- [ ] Register the site in [[Site Registry]] and stand up the Slack build channel.

## Phase 3. Data before copy

- [ ] Build the source data files the generators read: per entity records (regulations, species, climate, costs, seasonality, local factors) with named, dated sources. On pest-control-usa this is The Geographer's location record; on pet-transport it is `data/countries_pet_regulations.json` and `data/airline_pet_policies.json`.
- [ ] Rule from pest-control-usa worth keeping: body copy may only use facts already present in that record's own fields. New claims enter the data file first, with a source, then the page.

## Phase 4. The build rhythm

- [ ] A block is 25 pages. One interactive "go" builds one block. The unattended routine builds 2 blocks per run, target 100 pages per day across 2 runs, floor 1 block when quality demands it, never more than 2.
- [ ] Every block runs the full pipeline in [[Worker Roster]] (Geographer through Builder on the 7 stage model) and clears every gate in [[Quality Gates]], scoped to the batch so old corpus debt never blocks new correct work.
- [ ] Word floors per tier (pest-control-usa values, adjust per site): Tier 1 >= 800 words unique body, Tier 2 >= 500, Tier 3 >= 350. Duplication ceiling 15% shared body copy between any two pages. At least 2 FAQs per page naming the location and a location specific fact.
- [ ] One atomic commit per block or batch: content + BUILD-PLAN.md row + build_state.json (reconciled by the verify script, never hand edited) + MEMORY.md. Then the live link review post, one URL per line.

## Phase 5. The autonomous routine

- [ ] Write the routine prompt as a self contained file in the repo (`AUTONOMOUS-BUILD-ROUTINE.md` or `docs/build-routine.md`) and paste it into Claude Routines. It must contain, in order: branch guard (halt if not on the production branch), budget tripwire (halt on usage limit, post to Slack), read state (build_state.json points at the next chunk, tier and template), skip check by commit log not by date, build 2 blocks through the full gate, reconcile counts from disk, atomic commit with retry twice then alarm, verify the remote SHA matches, then the Slack post with every live link on its own line.
- [ ] Every halt condition posts a named status to the site's Slack channel: BUILD HALTED, PAUSED, SKIPPED, COMMIT FAILED, DEPLOY RISK. Silence is never an acceptable failure mode.
- [ ] Schedule within the 15 routine per day cap across the whole portfolio (see [[SEO Portfolio]] standing context).

## Phase 6. Switch on operations

- [ ] Submit sitemaps (split large sitemaps by section), verify GSC, wire GA4, connect Windsor.ai.
- [ ] Add the site to [[Monitoring Flow]] cadence and thresholds.
- [ ] Add the lead capture and tracking loop (form or WhatsApp to tracker sheet, the pet-transport enquiry tracker webhook is the reference pattern).
- [ ] File the first monthly review date in the site tracker.

## Done means

Tier 1 pages live and indexed, routine building unattended at 2 blocks per run, gates green, monitoring reporting weekly, leads landing in a tracker.
