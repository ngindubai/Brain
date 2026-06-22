---
title: Brain ingestion - tracker
area: dashboard
tags: [project, ingestion]
status: active
stage: Plan set, agent-org batch done, awaiting source files for the rest
next_action: Ingest the next batch on request
updated: 2026-06-22
---

# Brain ingestion

Ingest the research HTML documents into the brain at full fidelity. Done in batches.

## Method (per document, no compromise on detail or linking)

1. Read the full source: an uploaded or pasted file, or Drive for the recurring reports.
2. Save the original verbatim to `.raw/<area>/<filename>` as the immutable record.
3. Write a distilled note in the right area or project: frontmatter, the substantive detail kept, and `[[wikilinks]]` to the area, related notes, the `.raw` source, and the relevant repo.
4. Update the area note to link the new note.
5. Cross-link related documents to each other.
6. Log in the daily note.

## Source reality

Drive holds the recurring SEO report outputs (portfolio, mortgage, money, insure compare). Those I ingest directly. The one-off research documents are not in Drive, so for those upload or paste them when you say ingest the batch. Search-based ingestion is the default, with any gap flagged per document.

## Batches

### Batch 1 - SEO portfolio
- [ ] Latest portfolio SEO report (Drive, 2026-06-21), snapshot only
- [ ] Portfolio action plan / GSC triage manual (upload)
- [ ] GEO/AEO audit and implementation playbook (upload)
- [ ] Programmatic SEO diagnostic, root causes per site (upload)
Destination: [[areas/seo-portfolio/seo-portfolio]] and [[projects/seo-indexing-fix/seo-indexing-fix]]

### Batch 2 - Comparison network
- [ ] Latest MortgageCompare SEO report (Drive)
- [ ] UAE Compare Network weekly SEO report (Drive, 18 June)
- [ ] money and insure compare SEO reports (Drive)
- [ ] Comparison seed packs and cluster maps (upload)
- [ ] MortgageCompare go-to-market plan (upload)
- [ ] DLD transaction analysis (upload)
Destination: [[areas/comparison-network/comparison-network]]

### Batch 3 - Products
- [ ] George brochure, skins study, product docs (upload)
- [ ] NGIN command build guide (upload)
- [ ] KlientFlo proposal Rev 4.0, SOW, invoice (upload)
Destination: [[areas/products/products]]

### Batch 4 - Ventures
- [ ] Property expansion research, 114 opportunities (upload)
- [ ] AI build ideas, 20 at GBP 10k+ (upload)
- [ ] GPU compute business model (upload)
- [ ] US service business opportunities (upload)
- [ ] KDP self-publishing (upload)
- [ ] UK energy claims analysis (upload)
Destination: [[areas/ventures/ventures]]

### Batch 5 - Trading
- [ ] Trader Capture Kit (upload)
Destination: [[areas/trading/trading]]

### Batch 6 - NORTHLANDS
- [ ] NORTHLANDS City Bible master (upload)
- [ ] FiveM free scripts catalogue (upload)
Destination: [[areas/products/products]]

## Done

- Hermes and humanless-companies design batch ingested into [[areas/agent-org/agent-org]] (three-layer stack, warehouse, souls, humanless company design, agent behaviour design, marketing department).

## Open questions

- Recurring SEO reports: ingest only the latest snapshot per site as the note, originals to `.raw`? Default yes.
