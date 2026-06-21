---
title: SEO portfolio
area: seo-portfolio
tags: [area, seo, lead-gen]
updated: 2026-06-22
---

# SEO portfolio

Programmatic SEO lead-generation sites. Each ranks for long-tail service queries and sells the leads.

## Sites and repos

| Site | Repo | Notes |
|---|---|---|
| PetTransportGlobal | `ngindubai/pet-transport` | Reference site and template. Highest traffic. Page-one within weeks of launch. |
| RepatriationFuneral | `ngindubai/funeral-repatriation` | Worst indexing in the portfolio, roughly 2,193 not-indexed pages. Canonical and duplication repair first. |
| CloseProtectionHire | `ngindubai/closeprotectionhure-com` | Bot and spam traffic masking near-zero real audience. |
| BusRentalGlobal | `ngindubai/global-bus-hire` | Park-or-resume decision after index cleanup. |
| PestRemovalUSA | `ngindubai/pest-control-usa` | Sitemap coverage and internal linking fix. No hard 404s. |

## Standing context

- Builds run via Claude Code Routines on Anthropic's cloud, batched up to 4 blocks per run to fit the 15-routine/day cap.
- GA4 and GSC data piped through Windsor.ai. Semrush for keyword and competitor work.
- `.github/workflows/` paths return 403 on the connector and must be edited manually.

## Open loops

- Finish the GSC indexing fix, site by site.
