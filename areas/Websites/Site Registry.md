---
title: Site Registry
tags: [websites, registry, portfolio]
updated: 2026-07-22
---

# Site Registry

Every lead generation site, its archetype and its machinery. Update this row the day a site launches or changes stack. This is the index a fresh chat reads to find the right reference repo to copy.

## Live sites

| Site | Domain | Repo | Archetype | Stack | Deploy | Publishing engine |
|---|---|---|---|---|---|---|
| PetTransportGlobal | pettransportglobal.com | `ngindubai/pet-transport` | Programmatic (routes) + blog | Hugo 0.160 + Python generators | Push to `main` fires `build-to-live.yml`, `live` branch served by Hostinger | Cascading build plan, chunks of 25, templates A to E, AUTONOMOUS-BUILD-ROUTINE.md |
| PestRemovalUSA | pestremovalusa.com | `ngindubai/pest-control-usa` | Programmatic (state, city, town) | Next.js 16 static export + TypeScript data files | Push to `main`, Actions publishes `out/` to `live` branch, Hostinger serves | 7 stage pipeline, 14 workers, `docs/build-routine.md`, `npm run check:batch` |
| RepatriationFuneral | (funeral repatriation) | `ngindubai/funeral-repatriation` | Programmatic | Python generated HTML | Hostinger | Pet transport method port. Indexing repair in progress, see [[SEO Portfolio]] |
| CloseProtectionHire | (close protection) | `ngindubai/closeprotectionhure-com` | Programmatic | Static HTML + Python | Hostinger | Pet transport method port |
| BusRentalGlobal | (bus hire) | `ngindubai/global-bus-hire` | Programmatic | Static HTML + Python generators | Hostinger | Pet transport method port, park or resume decision open |
| MortgageCompare | mortgagecompare.ae | `ngindubai/mortgagecompare-ae` | Content | Static HTML/CSS/JS, knowledge hub | Push to `main`, `deploy.yml` FTP syncs to Hostinger | 249 row content plan (plan-rows q1 to q4), 23 clusters, five gate scripts, `docs/build-routine.md` |
| InsureCompare | insurecompare.ae | `ngindubai/insurecompare-ae` | Content | Static HTML, mortgagecompare design family | Hostinger | Content plan seed pack, Semrush AE pull |
| MoneyCompare | moneycompare.ae | `ngindubai/moneycompare-ae` | Content | Static HTML, design family | Hostinger git integration | ~1,260 row plan, 5 articles per working day, corridor pages first |
| Warm Homes Loan Scheme | warmhomeschemeloan.co.uk | `ngindubai/Warmhomes` | Content | `src/` templates + `node build.js`, hub articles are final HTML | Hostinger pulls branch `claude/website-plan-qa-ddv99s` (NOT main) | Insights engine: 4 workers + 7 gates, ~369 row 12 month queue, 1 article per day |
| Orwell Lab | orwelllab.com | `ngindubai/orwell-replica` | Content (agency site + insights) | Framer export + insights engine | Render deploys `main` | Insights engine: 4 workers + 7 gates, 358 row plan, 1 article per day |

## Tool stack shared across sites

| Layer | Tool |
|---|---|
| Keyword and competitor data | Semrush MCP (`phrase_these` batches, db per market) and the in house keyword platform built on the Semrush data source. Google Keyword Planner for CPC validation |
| Search performance | GSC and GA4, piped through Windsor.ai |
| Site health | Per repo audit scripts (`site_health_monitor.py`, gate scripts), Semrush site audit |
| Alerts and review | Slack build channels (one per site, e.g. #build-pet-transport) |
| Build execution | Claude Code (Max 20x) + Claude Routines, batched to fit the 15 routine per day cap |
| Hosting | Hostinger (FTP or git), Render for orwelllab |

When the in house keyword platform gets its own repo entry, record it here with its query interface so research flows can call it by name.

## Conventions that differ per site (check before working)

- **Deploy branch is not always `main`.** Warmhomes deploys from `claude/website-plan-qa-ddv99s`. Check the repo CLAUDE.md branch rule first, every time.
- **English variant follows the market.** US sites are US English absolutely (pest-control-usa bans British spellings by list). UK and UAE sites are British English. Never mix.
- **Author model differs.** Pet transport and pest control use four named personas each. Warmhomes uses only the Organization editorial desk. Orwell Lab uses Gareth or the research desk. Mortgagecompare rotates a named pool. Never use Gareth's name on the programmatic sites.
