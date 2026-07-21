---
title: Build A Content Site
tags: [websites, build, content, flow]
updated: 2026-07-22
---

# Build A Content Site

For demand that is a body of questions, comparisons and decisions around one subject. Ranks by publishing one quality gated article per day (up to 5 on aggressive sites) into a cluster mapped knowledge hub. Reference implementations: `ngindubai/Warmhomes` and `ngindubai/orwell-replica` carry the newest engine (`insights-engine/`, 4 workers + 7 gates); `ngindubai/mortgagecompare-ae` is the biggest corpus and the origin of the content plan format.

Entry point for a brand new topic: run [[New Site Kickoff Prompt]] first.

## Phase 0. Keyword universe and cluster map

- [ ] Pull the keyword universe: Semrush broad match export plus `phrase_these` batches in the market database, or the in house keyword platform. Include volume, KD, CPC, intent. On an existing domain add GSC queries.
- [ ] Watch for adjacent demand traps: a brand adjacent term can dwarf the real target (the Warm Home Discount at 90k monthly searches next to the Warm Homes Loan Scheme). Identify and exclude before planning.
- [ ] Deduplicate keeping the highest volume row per keyword. Filter to the intents that convert (commercial, transactional, plus the informational spine).
- [ ] Cluster the universe: 8 to 25 named clusters, each with an ID, a name, an intent label and an article count. The cluster IDs become the page meta tag (`mc-cluster`, `ol-cluster`, `whs-cluster` pattern).
- [ ] Output: cluster map + keyword universe committed to `content-plan/` or `insights-engine/`.

## Phase 1. Competitor and gap research

- [ ] Semrush organic research on the top ranking domains: their top pages, their keyword coverage, their calculators and tools (calculators are a moat: yallacompare's car loan calculator is its second biggest page).
- [ ] Note which clusters competitors own and which are open. Open clusters with real volume are the launch batch.
- [ ] Write the per cluster information gain thesis.

## Phase 2. The content plan (the ordered queue)

- [ ] Generate the plan: one row per article with slug, title, cluster, publish_date, slot, primary keyword (with volume and KD where verified), secondary and LLM layer keywords, H2 outline, direct answer block, schema required, internal and external links, author, word count target.
- [ ] Scale: 249 rows over 12 months at 1 per day (mortgagecompare), ~369 rows (Warmhomes), ~1,260 rows at 5 per working day (moneycompare). Pick the cadence the niche supports.
- [ ] Rows are an ordered queue by (publish_date, slot). Past dates are queue position, not deadlines. Each run builds exactly the earliest unbuilt row. Published state is file existence, never a flag edited by hand.
- [ ] Keyword gate: a row is only eligible if its primary keyword is non null. Never invent a keyword to unblock a row.
- [ ] Output: `publishing-plan.json` + monthly `schedule-YYYY-MM.json` files (or the plan-rows-q1 to q4 JS format), plus a human readable dashboard HTML.

## Phase 3. Site scaffold

- [ ] Static HTML with a master template: every new page is generated from the newest live article, never a bespoke skeleton. Design tokens in one CSS file. Site constants (rates, scheme figures) in one data file with marker wrapped values (`<!--r:KEY-->` / `<!--c:KEY-->`) applied by script, never hard coded per page.
- [ ] Stand up the engine directory from the Warmhomes/orwell-replica pattern: `insights-engine/ENGINE.md` (master rules), `workers/` (research, writing, humanising, seo agent specs), `data/` (claims.json, intent-map.json, style-law.json), `templates/article.html`, `ROUTINE-PROMPT.md`, and `scripts/run-gates.py` with the seven gates.
- [ ] Wire deploy (Hostinger FTP or git pull, Render for orwelllab class sites). Record the production branch in CLAUDE.md; it is not always `main`.
- [ ] Register in [[Site Registry]], stand up the Slack channel, wire GA4 with the event helper and cluster meta tag.

## Phase 4. Born correct constants (every page at generation time)

- [ ] Canonical self reference. Never noindex an article.
- [ ] Cluster meta tag with exactly one valid cluster ID.
- [ ] Visible breadcrumb at the top (Home > Hub > label) as real links, plus BreadcrumbList JSON-LD.
- [ ] Key facts / In brief box after the H1: 3 bullets sourced only from the article's own content, plus one cluster routed CTA.
- [ ] Direct answer paragraph in the first 150 words, quotable by an assistant.
- [ ] Article + FAQPage + BreadcrumbList JSON-LD, FAQ names matching body H3s verbatim. Never any rating or review schema.
- [ ] Every statistic exists in claims.json with source, source_url and checked_date, wrapped in page as a claim marker. Claims older than 6 months block the commit until re verified.
- [ ] Intent map registration, sitemap entry, llms.txt line and hub feed card (prepended, newest first) in the same commit.
- [ ] 4+ internal links to cluster siblings plus one up to the pillar or hub, all relative, all final URLs, never a superseded slug.
- [ ] No stale month year stamps in titles or metas. Real dates only, bumped only on real edits.

## Phase 5. The daily routine

- [ ] The routine prompt lives at `insights-engine/ROUTINE-PROMPT.md` with a paste ready copy in `PROMPT.txt`. One article per run, one commit per run, straight to the production branch, ending with the live URL.
- [ ] Pipeline per article: research agent (brief with the information gain fact, 5 to 10 sourced claims, competitor angle, real FAQ questions; no brief, no article), writing agent (structure contract from the plan row), humanising agent ([[Style Law]] in full), seo agent (head, schema, registrations). A worker that cannot meet its pass criteria stops the article and takes the next queue row rather than shipping weak.
- [ ] All seven gates pass or nothing pushes. No baseline edits to force a commit through.
- [ ] Monthly planning pass on the first run of the month: one Semrush batch call verifying the coming month's keywords, swap losers, re verify moving scheme facts, record the pull in the plan meta. Quarterly future layer review: promote anything whose volume tripled.

## Done means

Launch batch live, daily routine publishing unattended, gates green, hub and feeds updating themselves, monitoring reporting weekly, lead events firing in GA4 with value attached.
