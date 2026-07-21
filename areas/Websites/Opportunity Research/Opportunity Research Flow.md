---
title: Opportunity Research Flow
tags: [websites, research, opportunities, keywords, cpc, flow]
updated: 2026-07-22
---

# Opportunity Research Flow

Finds the next site worth building, using keyword volume, KD and CPC data from the in house keyword platform (Semrush data source) plus lead marketplace pricing. Output is a scored opportunity report filed in `Research/`, promoted to a build only when it clears the scorecard. The kill discipline matters as much as the find: most candidates should die here cheaply.

## Step 1. Candidate sourcing

- [ ] Lead marketplaces first: Referr, pay per call networks (Callbox pattern), and any listing that states a per lead price. A posted buy price is proof someone pays for the lead; note the price, the geography restriction and the qualifying requirements.
- [ ] CPC mining: pull high CPC commercial intent clusters from the in house platform. CPC is the proxy for lead value where no marketplace price exists.
- [ ] Portfolio adjacency: niches sharing data shape with an existing archetype transfer fastest (another entity matrix ports the pest control machinery; another regulated consumer scheme ports the Warmhomes engine).
- [ ] The weekly Niche intelligence brief: any CONTENT CLUSTER TRIGGER yes line is a candidate for expansion research.

## Step 2. Demand pull

- [ ] Semrush `phrase_these` batches (up to 20 seeds per call, correct market database, columns keyword, volume, cpc, competitive_density, keyword_difficulty, intent), expanded with `phrase_fullsearch` (top 40 by volume) and `phrase_related` on the strongest seeds. Run `get_report_schema` before any unfamiliar report. Four calls, roughly 165 rows, is enough for a full first taxonomy.
- [ ] Exclude adjacent demand traps before totalling anything (the look alike term that belongs to a different product).
- [ ] Total the cluster volume, note the KD distribution and the CPC spread. Record whether volumes are tool verified or logic estimated.
- [ ] Geo restricted plays: check the restricted region's cluster volume specifically. Semrush geo CPC is weak below country level; validate with Google Keyword Planner before trusting a local paid play.

## Step 3. Competition verification

- [ ] Never trust KD alone. Live search the top 10 for the head term and 5 long tail samples: who ranks, are they SEO professionals in their own right (a generation trap: design and web niches are full of incumbents who do SEO for a living), how strong are their pages really.
- [ ] Semrush organic research on the top 2 to 3 domains: pages, keywords, traffic concentration, what tool or calculator anchors them.
- [ ] Name the winnable gap or kill the candidate.

## Step 4. Economics

- [ ] Lead value: marketplace posted price, or CPC x a conservative multiple, or a known commission (the mortgagecompare model prices a lead at AED 7,000 from commission x close rate).
- [ ] Ceiling: cluster volume x realistic CTR x conversion. A £200 per lead niche with 1,000 monthly cluster searches works in principle but has a low ceiling; say so plainly.
- [ ] Cost side: pages needed to compete, build effort in blocks or plan rows, any data acquisition burden, any YMYL or regulatory load.

## Step 5. Scorecard (all six or it dies)

| # | Test | Pass |
|---|---|---|
| 1 | Proven lead demand | A buyer exists at a stated or defensible price |
| 2 | Reachable volume | Cluster volume supports the ceiling needed at the lead price |
| 3 | Winnable SERP | Verified by live search, not KD alone; a named gap exists |
| 4 | Archetype fit | Maps cleanly onto programmatic or content machinery we already run |
| 5 | Information gain source | We can actually obtain data competitors do not have |
| 6 | Economics | Ceiling x lead value clears the build and run cost with margin |

- [ ] Verdict: BUILD (goes to [[New Site Kickoff Prompt]]), PARK (file with the trigger that would revive it), or KILL (file the reason so it is not re researched).

## Output

One note per candidate in `Research/` using the Idea Template: the pull data, the SERP verification, the economics, the scorecard, the verdict. Add the row to the Research Topics table. A BUILD verdict graduates to `Projects/` per the vault idea lifecycle, then runs the kickoff prompt.

## Opportunity research prompt (paste into a fresh chat)

```
Run an opportunity research pass for a potential new lead generation site. Candidate: <NICHE, MARKET, and the source of the idea, e.g. a Referr listing at £X per lead with its restrictions, or a CPC cluster from the keyword platform>. Method and scorecard: ngindubai/Brain areas/Websites/Opportunity Research/Opportunity Research Flow.md; read it first, plus areas/Websites/Websites.md for the two archetypes.

Execute: 1) Demand pull via the Semrush MCP (phrase_these batches, correct market database, columns keyword, volume, cpc, competitive_density, keyword_difficulty, intent; get_report_schema first; if out of API units say so and stop rather than guessing). Exclude adjacent demand traps before totalling. 2) Competition verification by live search on the head term and 5 long tail samples plus Semrush organic research on the top domains; name the winnable gap or the reason there is none. 3) Economics: lead value with its source, volume ceiling, build cost in blocks or plan rows. 4) Score all six scorecard tests and give a one word verdict: BUILD, PARK or KILL, with the single strongest reason. 5) File the research note in ngindubai/Brain Research/ per the vault conventions (frontmatter, wikilinks, British English, no em dashes, banned word list) and add the Topics table row. Never present an estimated volume as tool verified; label every number's source.
```
