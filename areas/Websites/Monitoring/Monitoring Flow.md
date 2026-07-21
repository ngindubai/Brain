---
title: Monitoring Flow
tags: [websites, monitoring, flow]
updated: 2026-07-22
---

# Monitoring Flow

Health and performance checks across every site in [[Site Registry]]. Monitoring produces findings; [[Fix And Enhance Flow]] turns findings into shipped work. Monitoring never fixes anything itself; it reports.

## Data sources

| Source | What it gives | Access |
|---|---|---|
| GSC | Indexed vs not indexed, impressions, clicks, queries, page level CTR, manual actions | Windsor.ai connector, or URL Inspection by hand for single pages (the bulk indexing report can lag by weeks; trust URL Inspection over it) |
| GA4 | Sessions, key events (generate_lead, calculator_complete, whatsapp_click, view_article), lead value, cluster level reporting via the cluster meta tag, AI assistant referral channel | Windsor.ai connector, GA4 Explore for the weekly explorations |
| Semrush / in house keyword platform | Position tracking, site audit, backlinks, referring domains, Sensor volatility, competitor movement | Semrush MCP; the in house platform runs on the same data source and is the default once stable |
| Repo scripts | Gate status, count drift (verify_build_state), broken links, similarity, banned vocab backlog | Run in Claude Code per repo |
| Live site | HTTP status of sampled pages, sitemap validity, schema validation, Core Web Vitals via PSI | site_health_monitor.py (pet-transport) as the pattern |
| Slack | Routine halt posts (BUILD HALTED, PAUSED, COMMIT FAILED) | The build channels are themselves a monitoring feed: a silent channel that should be posting is a red flag |

## Cadence

### Daily (automatic, zero effort)
- The build routines post their own status and live links per run. A missing post is a finding.
- The SEO daily intelligence brief flags confirmed Google updates and Sensor spikes and names the most exposed sites (see the Brain CLAUDE.md Intelligence Reports section).

### Weekly (one run per site, batched)
- [ ] GSC: indexed count vs total pages, week on week. Impressions and clicks trend. New queries worth owning.
- [ ] GA4: sessions, lead events and lead value by site. Anything down more than 20% week on week is a finding.
- [ ] Routine health: every scheduled routine ran and committed. Chunk pointer advancing. Gates green.
- [ ] Sample 10 live URLs per site for 200 status and correct canonical.

### Monthly (deep pass, one site per day across the month)
- [ ] Full position tracking pull: target keywords vs rank, movement vs last month, competitor overlap.
- [ ] Site audit run (Semrush site audit or the in house equivalent): errors, warnings, crawl issues.
- [ ] Backlinks and referring domains vs the site's gate target (mortgagecompare pattern: baseline and target recorded, re pulled monthly).
- [ ] Content decay check on content sites: pages with falling clicks that earn a refresh (real edit, real dateModified bump).
- [ ] Count reconciliation: verify script against disk, docs vs reality.
- [ ] Monthly planning pass on content sites (keyword re verification) per the engine rules.

## Thresholds that trigger a finding

- Indexed share falling two weeks running, or below 60% of submitted pages after 8 weeks live.
- Any manual action or security issue in GSC: drop everything.
- Lead events down more than 20% week on week without a traffic drop to explain it.
- Sensor spike plus a portfolio ranking move in the same week: freeze template changes until it settles.
- Any gate failing on main, any count drift, any routine silent for 48 hours.
- Bot or spam traffic masking real numbers (the closeprotection failure mode): segment it out before reading trends.

## Output format

One dated health report per run: `reports/health-YYYY-MM-DD.html` in the site repo (or the portfolio roll up filed in this folder), each finding with severity (P1 fix now, P2 this week, P3 backlog), evidence, and a one line proposed action. Post the summary to the site's Slack channel. Every P1 and P2 finding becomes a ticket in [[Fix And Enhance Flow]].

## Weekly monitoring prompt (paste into a routine or a fresh chat)

```
Run the weekly monitoring pass for the Orwell website portfolio. The site list, repos and stacks are in ngindubai/Brain areas/Websites/Site Registry.md; the checks, thresholds and output format are in areas/Websites/Monitoring/Monitoring Flow.md. For each site: pull GSC and GA4 numbers via the available connectors (Windsor.ai preferred, note any source you cannot reach), check the last 7 days of routine commits in the repo, sample 10 live URLs for status and canonical, and compare against last week's report if one exists in the repo reports/ directory. Produce one dated portfolio health report with per site sections, findings graded P1/P2/P3 with evidence, and a proposed action per finding. Commit the report and post the P1/P2 summary. Do not fix anything in this pass; report only. Never invent a number you did not pull; mark gaps as NOT CHECKED with the reason.
```
