---
title: Websites
area: Websites
tags: [area, websites, lead-gen, seo, factory]
updated: 2026-07-22
---

# Websites

The website factory. This area holds the repeatable method for building, monitoring, fixing and finding lead generation websites. Every flow here is written so a fresh Claude chat can execute it end to end with no other context.

Source of the method: the live portfolio repos, scanned 2026-07-22. The rules below are extracted from what already works on pet-transport, pest-control-usa, mortgagecompare-ae, Warmhomes and orwell-replica, not invented from scratch.

## The two archetypes

Every site in the portfolio is one of two builds. Decide the archetype before anything else.

| Archetype | Ranks with | Examples | Build flow |
|---|---|---|---|
| **Programmatic** | Thousands of long tail entity pages (country to country routes, city pages) built from data files through rotating templates | pet-transport, funeral-repatriation, closeprotectionhure-com, global-bus-hire, pest-control-usa | [[Build A Programmatic Site]] |
| **Content** | Daily quality gated articles into a knowledge hub, organised by keyword clusters with one owner page per intent | mortgagecompare-ae, insurecompare-ae, moneycompare-ae, Warmhomes, orwell-replica | [[Build A Content Site]] |

Decision test: if the demand splits naturally into a big matrix of entity pairs or locations (X to Y, service in City), it is programmatic. If the demand is a body of questions and comparisons around one subject, it is content. Some sites end up hybrid (pet-transport runs both routes and a blog); start with the dominant mode.

## The flows

| Flow | What it does | Note |
|---|---|---|
| Build a new site | Topic in, live earning site out | [[New Site Kickoff Prompt]] then [[Build A Programmatic Site]] or [[Build A Content Site]] |
| Monitor the portfolio | Health and performance checks on every live site | [[Monitoring Flow]] |
| Fix and enhance | Turn monitoring findings into shipped fixes and forward rules | [[Fix And Enhance Flow]] |
| Find the next site | Keyword, CPC and lead value research into a go or no go | [[Opportunity Research Flow]] |

## Reference (shared law)

| Note | Holds |
|---|---|
| [[Site Registry]] | Every site: domain, repo, archetype, stack, deploy, routine, status |
| [[Worker Roster]] | The canonical worker set for both pipelines |
| [[Quality Gates]] | The gates that hold before any commit, plus the docs discipline |
| [[Style Law]] | Banned words, burstiness, information gain, personas, YMYL guard |
| [[Repo Scaffold]] | The files every site repo must carry, and the known platform traps |

## Operating principles (apply everywhere)

- **Quality gated batches, never bulk generation.** A block is 25 pages or 1 article. Every block runs its full pipeline. Mass generation scripts without the gate are banned on every site.
- **Born correct beats fixed later.** Every past fix becomes a forward rule in the site's CLAUDE.md so new pages are generated already compliant. The fix flow feeds the build flow.
- **Docs move with content.** Every content commit also updates BUILD-PLAN.md, build_state.json and MEMORY.md in the same commit, with counts reconciled from disk by script, never by hand.
- **Review after deploy.** Deploys are automatic on push. The safety gate is the live link review: every new or changed URL posted, one line per page, after every batch.
- **One owner page per intent.** The intent map is the anti cannibalisation registry. No second page for a query that already has an owner.
- **Nothing invented.** Every statistic sourced and dated. No fabricated ratings, testimonials, credentials or anecdotes, ever.

## Related areas

[[SEO Portfolio]] holds live status of the programmatic sites. [[Comparison Network]] holds the UAE content sites. This area holds the method; those hold the state.
