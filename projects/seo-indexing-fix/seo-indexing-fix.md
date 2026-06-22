---
title: SEO indexing fix - tracker
area: seo-portfolio
tags: [project, seo, indexing, gsc]
status: active
stage: Per-site GSC indexing repair
next_action: RepatriationFuneral canonical and duplication repair, then PetTransport 404s
updated: 2026-06-22
---

# SEO indexing fix

Area: [[areas/seo-portfolio/seo-portfolio]].

## The one goal

Get the programmatic portfolio cleanly indexed in Google so the pages can rank and sell leads.

## What we have learnt

- Worst site: RepatriationFuneral, roughly 2,193 not-indexed (718 alternate-canonical, 574 discovered, 433 Google-chose-different-canonical, 367 crawled-not-indexed). Repair before any new content.
- PetTransport leaks: 114 hard 404s and roughly 1,069 not-indexed despite being highest traffic.
- MortgageCompare cleanest (30 not-indexed). Its failed-canonical is a content-similarity issue across near-identical calculator pages, not technical.
- PestRemovalUSA has no hard 404s. It is a sitemap-coverage and internal-linking fix.
- CloseProtection robots.txt was bare and was fixed to the Repat/Pet pattern with sitemap and AI-bot directives.
- BusRentalGlobal canonical script rewritten to clean directory URLs; needs a local re-run and push.
- Branch care: closeprotection uses master, pet-transport uses main. Read deployed Hugo output with ref live.

## Progress

Done:
- Action plan / tickable manual built. BusRental canonical script fixed. CloseProtection robots.txt fixed. Live Windsor GA4 and GSC data confirmed flowing.

Frontier:
- RepatriationFuneral canonical and duplication repair. PetTransport 404 cleanup. GSC console submissions.

## Next actions

1. RepatriationFuneral: fix canonicals, de-duplicate, resubmit.
2. PetTransport: clear the 114 hard 404s.
3. Bus: run the canonical script locally and push.
4. MortgageCompare: differentiate the five calculator pages with bank-specific content.

## Open questions

- Park or resume BusRentalGlobal after index cleanup?
