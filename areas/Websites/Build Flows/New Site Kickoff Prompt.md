---
title: New Site Kickoff Prompt
tags: [websites, build, prompt, kickoff]
updated: 2026-07-22
---

# New Site Kickoff Prompt

The master prompt. Open a fresh Claude chat (or Claude Code session with the git connector), paste everything in the block below, fill the three fields at the top, send. It runs research, decides the archetype, produces the build plan and scaffolds the repo to the point where the daily build rhythm can start.

Keep this prompt in sync with [[Build A Programmatic Site]] and [[Build A Content Site]]; it is the executable summary of both.

```
TOPIC: <the niche, e.g. yacht transport>
MARKET: <primary country or region and language variant, e.g. USA, US English>
LEAD BUYER: <who buys the leads and roughly what a lead is worth, if known>

You are building a new lead generation website for the Orwell portfolio, owner ngindubai. Work through the phases below in order. Do not skip research to start building. Ask at most one clarifying question, then proceed on stated assumptions.

CONTEXT AND METHOD SOURCES
The method is already proven in these repos. Read before building, copy conventions rather than inventing:
- Programmatic archetype reference: ngindubai/pest-control-usa (read CLAUDE.md and AGENTS.md) and ngindubai/pet-transport (read CLAUDE.md and AUTONOMOUS-BUILD-ROUTINE.md).
- Content archetype reference: ngindubai/Warmhomes and ngindubai/orwell-replica (read insights-engine/ENGINE.md, the workers/ specs and ROUTINE-PROMPT.md).
- The framework notes live in ngindubai/Brain under areas/Websites/ (Websites, Build A Programmatic Site, Build A Content Site, Worker Roster, Quality Gates, Style Law, Repo Scaffold, Site Registry). Read them.

PHASE 1: KEYWORD RESEARCH
Pull the keyword universe with the Semrush MCP (get_report_schema first, then execute_report). Use phrase_these batch calls: up to 20 semicolon separated seeds per call, database matching MARKET, columns keyword, volume, cpc, competitive_density, keyword_difficulty, intent. Expand with phrase_fullsearch and phrase_related on the strongest seeds. If Semrush is out of API units, say so and use the in house keyword platform or ask for a manual export. Watch for adjacent demand traps: exclude look alike terms that belong to a different product before planning. Deduplicate keeping the highest volume row per keyword. Deliver: total addressable volume, volume by cluster, CPC by cluster, KD distribution, intent split.

PHASE 2: COMPETITOR RESEARCH
Identify the top 5 to 10 ranking sites for the head term and for 5 sample long tail queries (live web search plus Semrush organic research per domain). Record page counts, structures, schema, tools and calculators, and what their pages are missing. Write the information gain thesis: the specific data every one of our pages will carry that theirs do not.

PHASE 3: ARCHETYPE DECISION
Decide programmatic or content. Programmatic if demand splits into a large entity matrix (X to Y, service in City): count the cells and tier them 1 to 3. Content if demand is a question and comparison body around one subject: build the cluster map (8 to 25 clusters with IDs, intents, article counts). State the decision and the reasoning in one paragraph. Hybrid is allowed but name the dominant mode and build that first.

PHASE 4: THE BUILD PLAN
Produce the plan as a committed file in the new repo:
- Programmatic: tiered entity matrix, page hierarchy, the 5 template (A to E) definitions, data file schema for the per entity records, chunk sequence (blocks of 25, Tier 1 first), word floors per tier, and the information gain rule.
- Content: the full ordered queue of plan rows (slug, title, cluster, publish_date, slot, primary keyword + volume + KD, secondary keywords, H2 outline, direct answer block, schema required, internal links, author, word count target) at the chosen cadence, plus the human readable dashboard.

PHASE 5: SCAFFOLD THE REPO
Create the repo with every file in the Brain Repo Scaffold note: CLAUDE.md adapted from the reference site (correct English variant for MARKET, author model, deploy branch rule, banned vocabulary, the born correct constants), BUILD-PLAN.md, build_state.json, MEMORY.md, ERRORS.md, the worker soul files, the gate scripts, the data files (claims.json, intent-map.json or the entity data files), the master page template(s), sitemap, robots.txt, llms.txt. Wire the deploy workflow (note: .github/workflows files cannot be pushed via the MCP connector, provide the file content for manual paste). Build the homepage, the hub pages and the first quality gated block or launch batch through the full worker pipeline and gates.

PHASE 6: ROUTINES AND OPERATIONS
Write the autonomous routine prompt into the repo (self contained: branch guard, budget tripwire, state read, skip check by commit log, build unit, gates, atomic commit with docs update, push verification, Slack post with every live URL on its own line). Then: register the site in the Brain Site Registry (areas/Websites/Site Registry.md) with a new row, set up the monitoring entry per the Brain Monitoring Flow, and list the manual tasks only Gareth can do (domain, hosting, GSC verification, GA4 property, Slack channel, routine scheduling) as numbered click this type this steps.

RULES THAT BIND THROUGHOUT
British English for UK and UAE markets, US English absolutely for US markets. No em dashes anywhere ever. The full banned vocabulary and banned frame list from the Brain Style Law note. Information gain decided before drafting: no gain, no ship. Never invent a statistic, rate, rating, testimonial or credential. One owner page per intent. Blocks of 25 pages or single articles, every unit through the full gate, never bulk generation. Every content commit bundles the docs update. End every build response with the clickable live URLs, one per line.
```

## After the kickoff

- [ ] Review the archetype decision and the plan before letting the routine run unattended.
- [ ] Do the manual tasks list (domain, GSC, GA4, Slack channel, schedule the routine within the 15 per day cap).
- [ ] Confirm the [[Site Registry]] row and the [[Monitoring Flow]] entry exist.
- [ ] First week: review the live link posts daily. Then drop to the normal monitoring cadence.
