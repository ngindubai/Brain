---
title: Brain ingestion - tracker
area: dashboard
tags: [project, ingestion]
status: active
stage: Plan set, awaiting source files per batch
next_action: Ingest Batch 1 (SEO portfolio)
updated: 2026-06-22
---

# Brain ingestion

Ingest the research HTML documents into the brain at full fidelity. Done in batches.

## Method (per document, no compromise on detail or linking)

1. Read the full source: an uploaded or pasted file, or Drive for the recurring reports.
2. Save the original verbatim to `.raw/<area>/<filename>` as the immutable record.
3. Write a distilled note in the right area or project: frontmatter, the substantive detail kept (findings, numbers, recommendations, decisions), and `[[wikilinks]]` to the area index, related notes, the `.raw` source, and the relevant repo.
4. Update the area `_index.md` to link the new note.
5. Cross-link related documents to each other.
6. Log in the daily note.

## Source reality

Drive holds the recurring SEO report outputs (portfolio, mortgage, money, insure compare). Those I ingest directly. The one-off research documents are not in Drive, so for those upload the HTML files, or paste them, when you say ingest the batch.

## Batches

### Batch 1 - SEO portfolio
- [ ] Latest portfolio SEO report (Drive, 2026-06-21) - snapshot only, not every daily copy
- [ ] Portfolio action plan / GSC triage manual (upload)
- [ ] GEO/AEO audit and implementation playbook (upload)
- [ ] Programmatic SEO diagnostic, root causes per site (upload)
Destination: [[areas/seo-portfolio/_index]] and [[projects/seo-indexing-fix/plan]]

### Batch 2 - Comparison network
- [ ] Latest MortgageCompare SEO report (Drive)
- [ ] UAE Compare Network weekly SEO report (Drive, 18 June)
- [ ] money and insure compare SEO reports (Drive)
- [ ] Comparison seed packs and cluster maps (upload)
- [ ] MortgageCompare go-to-market plan (upload)
- [ ] DLD transaction analysis (upload)
Destination: [[areas/comparison-network/_index]]

### Batch 3 - Products
- [ ] George brochure, skins study, product docs (upload)
- [ ] NGIN command build guide (upload)
- [ ] KlientFlo proposal Rev 4.0, SOW, invoice (upload)
Destination: [[areas/products/_index]] and projects

### Batch 4 - Ventures
- [ ] Property expansion research, 114 opportunities (upload)
- [ ] AI build ideas, 20 at GBP 10k+ (upload)
- [ ] GPU compute business model (upload)
- [ ] US service business opportunities (upload)
- [ ] KDP self-publishing (upload)
- [ ] UK energy claims analysis (upload)
Destination: [[areas/ventures/_index]]

### Batch 5 - Trading
- [ ] Trader Capture Kit, watch protocol, 87-question debrief, fuse prompt (upload)
Destination: [[areas/trading/_index]]

### Batch 6 - NORTHLANDS
- [ ] NORTHLANDS City Bible master (upload)
- [ ] FiveM free scripts catalogue (upload)
Destination: [[areas/products/_index]] and [[reference/house-style|reference]]

## Open questions

- Recurring SEO reports: ingest only the latest snapshot per site as the note, originals to `.raw`? Default yes, to avoid duplicate bloat.
- Anything in the batches I have wrong or missed? Add it before we start.
