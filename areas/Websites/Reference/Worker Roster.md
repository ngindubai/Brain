---
title: Worker Roster
tags: [websites, workers, pipeline, reference]
updated: 2026-07-22
---

# Worker Roster

The canonical worker set. Every page or article on every site passes through one of these two pipelines. Soul files live in each site repo (`workforce/` on programmatic sites, `insights-engine/workers/` on content sites); this note is the portfolio map of the roles so a new site knows what to port.

## Programmatic pipeline (the 7 stage model)

Origin: pet-transport. Cleanest current port: pest-control-usa (`workforce/`, roster in AGENTS.md). Every location or entity page passes all seven in sequence. Load only the workers a block needs.

| # | Worker | Does |
|---|---|---|
| 1 | The Geographer (or domain equivalent, e.g. regulations researcher) | Builds the per entity intelligence record: species and seasonality, regulations, climate, local factors, costs. Facts enter the record with sources before any copy exists |
| 2 | The Wordsmith | Unique warm expert copy from the record. Body copy may only use facts already in the record's own fields |
| 3 | The Interrogator | Entity specific FAQs; at least 2 per page naming the location or entity and a specific fact |
| 4 | The Chameleon | Humanisation and template footprint breaking: the [[Style Law]] pattern list, burstiness, statistical targets (trigram repetition under 0.05), and a generate then critique then revise pass |
| 5 | The Optimizer | Titles, metas, schema (LocalBusiness / Service / FAQPage or the route schema), internal links guarded against broken slugs |
| 6 | The Auditor | The QA gate: uniqueness, word floors, banned vocab, schema validity, factual accuracy, English variant |
| 7 | The Builder | Writes data and page files, builds the static export, commits atomically with the docs update, deploy fires |

Support workers (orchestration, not per page): The Architect (structure), The Scout (research), The Spider (data assembly), The Librarian (data hygiene), The Connector (internal linking), The Analyst (performance), The Watchdog (monitoring).

## Content pipeline (the 4 worker engine)

Origin: orwell-replica and Warmhomes `insights-engine/workers/`. One article per run, each worker's output is the next worker's input. A worker that cannot meet its pass criteria stops the article and the run takes the next queue row; never ship weak.

| # | Worker | Does | Hard rule |
|---|---|---|---|
| 1 | Research agent | The brief before any writing: the information gain fact, 5 to 10 claims each verified against a named dated source and written into claims.json, competitor angle notes, the FAQ questions real people ask | No brief, no article |
| 2 | Writing agent | Drafts from the brief and the plan row: H1, In brief box, direct answer paragraph in the first 150 words, H2 outline, FAQs, cluster routed CTA | Uses only claims from the brief, wrapped in claim markers |
| 3 | Humanising agent | Rewrites against the [[Style Law]]: banned words and frames out, burstiness in, template footprint broken, opens on this page's own number or scenario, closes on a concrete point never a summary | Output reads as written by a person with opinions |
| 4 | SEO agent | Final assembly: head tags, canonical, cluster meta, three JSON-LD blocks, visible breadcrumb, internal links, and every registration (intent map, sitemap, llms.txt, hub feeds) in the same commit | Never any rating schema; FAQ names match H3s verbatim |

## Porting rule for a new site

Copy the soul files from the newest reference repo of the matching archetype, then adapt only: the domain vocabulary of worker 1, the audience and tone brief of worker 2, the English variant, and the author model. The pass criteria and the pipeline order do not change.
