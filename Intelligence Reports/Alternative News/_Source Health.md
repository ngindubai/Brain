---
title: Alternative News - Source Health
tags: [intelligence, alternative-news, source-health]
updated: 2026-07-17
---

# Alternative News — Source Health

Tracks reachability of sources for the [[Intelligence Feed Sources|Alternative News]] daily brief. Recheck monthly; anything BLOCKED or DEAD twice running moves to the routine's Retired list.

## Core register (T1/T2), tested 17 July 2026

| Source | Entry point tried | Result | Notes |
|---|---|---|---|
| The Intercept | https://theintercept.com/feeds/ | OK | Feed fetched cleanly, full today-dated list with bylines and timestamps. |
| ProPublica | https://www.propublica.org/ | PARTIAL | Homepage doesn't surface reliable per-article dates; had to confirm today's story via targeted search instead. Use search fallback for date confirmation going forward. |
| Declassified UK | https://www.declassifieduk.org/feed/ | BLOCKED | 403 Forbidden on /feed/. Homepage not directly fetch-tested this run; confirmed via search fallback that nothing published 17 July (most recent then was 14 July). Retry homepage direct fetch next run. |
| Drop Site News | individual /p/ article URLs | BLOCKED | Two /p/ article fetches both returned 403 this run, despite the routine note that these usually fetch in full. Relied on search snippets instead. Today's content was daily war-tracker roundup format only (out of scope per routine rules), so no story lost to the block today — but the block itself is worth re-testing next run. |
| The Dissenter | https://thedissenter.org/rss/ | OK | Feed fetched cleanly. Nothing published today; most recent was 15 July. |
| Responsible Statecraft | https://responsiblestatecraft.org/ | OK | Homepage fetched cleanly, dated articles, four today. |
| openDemocracy | https://www.opendemocracy.net/ | OK | Homepage fetched cleanly, dated articles, three today. |
| Byline Times | https://bylinetimes.com/columns/special-investigation/ | OK | Page fetched cleanly. Nothing published today; most recent was 9 July. |

## Pending-verification sources, first tested 17 July 2026

| Source | Entry point tried | Result | Recommended tier | Notes |
|---|---|---|---|---|
| The Bureau of Investigative Journalism | https://www.thebureauinvestigates.com/ | BLOCKED | — | 403 Forbidden on homepage. Retest next run before promoting. |
| The Ferret | https://theferret.scot/ | OK | T3 | No paywall hit — full headlines with dates visible, contrary to the routine's "expect paywall" note. Scotland-focused, narrow remit; use selectively. |
| Source Material | https://www.source-material.org/ | OK | T2 | Strong cross-border corporate-accountability investigations, dated headlines back to October 2025 (low daily cadence — check every run but don't expect fresh content often). |
| Type Investigations | https://typeinvestigations.org/ | OK | T2 | Solid documents-based investigations; low daily cadence (most recent at test time was 26 May). |
| The Markup | https://themarkup.org/ | OK | T2 | Tech/data accountability, some overlap with the Tech category — use only when the story is corporate/state accountability rather than pure product coverage. |
| OCCRP | https://www.occrp.org/en | OK | T1 | Very strong, multiple dated stories same-day, cross-border corruption specialism. Promote to T1 alongside The Intercept and ProPublica. |
| Lighthouse Reports | https://www.lighthousereports.com/ | OK | T2 | Strong investigations plus methodology write-ups; the methodology posts are process pieces, not stories — don't count them as investigations for breadth purposes. |
| Follow the Money | https://www.ftm.eu/ | PAYWALL | T3 | Most substantive pieces gated behind a 30-day-trial membership wall; only newsletter-style headlines and select pieces are free. Use only when a specific story is confirmed free. |
| Correctiv | https://correctiv.org/en/ | OK | T2 | Solid European accountability journalism, low-ish cadence. |
| Disclose | https://disclose.ngo/en/ | OK | T2 | France-focused, state secrecy/environmental crime specialism. |
| Investigate Europe | https://www.investigate-europe.eu/ | OK | T2 | Strong EU-wide investigations (surveillance tech, gambling, tax), good UK/Europe breadth source. |
| Bellingcat | https://www.bellingcat.com/ | OK | T1 | Open-source investigation gold standard. Publishes irregularly — check every run, don't expect daily output. |
| Michael West Media | https://michaelwest.com.au/ | OK | T2 | Strong, high-cadence corporate/lobby accountability from Australia. Use selectively to avoid over-indexing non-UK/EU/US content against the routine's breadth rules. |
| Craig Murray | https://www.craigmurray.org.uk/ | OK (reachability only) | Do not promote | Loads fine but content is personal-blog opinion/commentary, not documents-based investigation. Cite only if he breaks original documentary evidence himself; otherwise out of scope. |

**Recheck due:** 17 August 2026.
