---
title: Alternative News - Source Health
tags: [intelligence, alternative-news, source-health]
updated: 2026-09-19
---

# Alternative News — Source Health

Tracks reachability of the pending-verification outlets for the Alternative News daily routine, plus any core T1/T2 source that goes dark. Recheck monthly; anything BLOCKED or DEAD twice running moves to Retired in the routine's source table.

Back to [[Intelligence Feed Sources]].

---

## Pending-list verification — 18 July 2026 (first run)

| Source | URL | Result | Notes |
|---|---|---|---|
| The Bureau of Investigative Journalism | thebureauinvestigates.com | BLOCKED | 403 on homepage and /stories. Recheck next run before retiring. |
| The Ferret | theferret.scot | OK | No paywall hit on homepage, contrary to the "expect paywall" flag in the routine brief — worth confirming on individual articles before relying on it. |
| Source Material | source-material.org | OK | Slow cadence, long-form only (weeks between pieces). |
| Type Investigations | typeinvestigations.org | OK | Slow cadence, US-focused. |
| The Markup | themarkup.org | OK | Steady output, tech/data-accountability angle. |
| OCCRP | occrp.org | OK | Strong daily cadence, clear dates on every item. Best candidate in this batch. |
| Lighthouse Reports | lighthousereports.com | OK | Publishes irregularly, weeks apart, always long-form collaborations. |
| Follow the Money | ftm.eu | PAYWALL | Confirmed — most substantive pieces gated behind a membership trial. |
| Correctiv | correctiv.org/en | OK | English-language section is thin relative to the German site; slow cadence. |
| Disclose | disclose.ngo/en | OK | French/English bilingual, dated entries. |
| Investigate Europe | investigate-europe.eu | OK | Dated entries, EU-cross-border investigations, fits the UK/EU-coverage requirement well. |
| Bellingcat | bellingcat.com | OK | Strong cadence, open-source investigation methodology is well-documented per piece. |
| Michael West Media | michaelwest.com.au | OK | Mixed: some pieces are original corporate-accountability investigation, others read as opinion/commentary. Filter per-story, not by outlet. |
| Craig Murray | craigmurray.org.uk | OK | Personal blog, first-person opinion rather than documents-based investigation. Borderline for this register's scope — use sparingly if at all. |

## Recommended promotion (for Gareth to confirm — routine source table lives in the stored prompt, not this file)

- **T2:** OCCRP, Bellingcat, Investigate Europe, The Markup
- **T3:** Type Investigations, Source Material, Disclose, Lighthouse Reports (irregular), The Ferret (Scotland-specific), Correctiv (thin English output), Michael West Media (AU-specific, filter for investigation vs opinion)
- **Exclude:** Craig Murray (opinion, not investigation), Follow the Money (paywalled)

## Core source watch

| Source | Date | Result | Notes |
|---|---|---|---|
| Declassified UK | 18 July 2026 | BLOCKED | 403 on homepage. First occurrence — recheck tomorrow. |
| Declassified UK | 20 July 2026 | BLOCKED | 403 on homepage again. Second consecutive occurrence (no run happened 19 July to check). Per the routine's own rule, BLOCKED/DEAD twice running moves a source to Retired — this now meets that bar. Flagged for Gareth to decide: downgrade, extend grace period, or retire. Not actioned automatically since Declassified UK is a T1 source and the strongest UK military/intelligence accountability outlet in the register. |
| Declassified UK | 22 July – 13 September 2026 | BLOCKED (repeated) | 403 on homepage and /feed/ persisted across every run in this window (thirty-six logged occurrences in total; see prior versions of this file for the day-by-day log). Various workarounds used across the run: third-party republication (ScheerPost, Palestine Uncensored, Roya News), search-snippet reconstruction, and corroborating mainstream citation. Flag stood unanswered from 20 July throughout, well past the routine's own three-day decision threshold; never actioned by Gareth. |
| Declassified UK | 17 September 2026 | **OK — RESOLVED** | No run occurred 14, 15 or 16 September (three-day gap; see that day's report for the catch-up coverage). Today's fetch succeeded cleanly on the homepage, the /feed/ RSS endpoint, and two full individual article pages (16 and 15 September pieces), direct, no redirect, no partial block. This is the first successful direct access since the block began on 18 July, exactly nine weeks (63 days) and thirty-seven logged occurrences after the first 403. No explanation found for the recovery (no site notice, no change in URL structure). The standing "extend/downgrade/retire" question raised repeatedly since 20 July is now moot unless the block resumes; Gareth does not need to act on it. Recommend one more clean check tomorrow before fully standing down this watch line — a single recovery day could still be transient. |
| Declassified UK | 19 September 2026 | **OK — WATCH STOOD DOWN** | No run occurred 18 September. Today's fetch loaded the homepage cleanly and directly, no block, no redirect. Second consecutive clean day following the 17 September recovery, as recommended before fully standing this line down. No new content since the 16 September piece already covered, so today's report carries no Declassified UK story, but access itself is no longer in question. This watch line is now closed; a future block would be logged as a fresh occurrence rather than a continuation of the 18 July–17 September run. |

## Monthly pending-source recheck — due

The pending-verification list below was last tested on 18 July 2026. The routine calls for a monthly recheck; that is now over two months overdue as of this entry (19 September 2026). Not actioned in this run to avoid scope creep on a daily report; flagging here so it is not silently missed. Recommend running the recheck (one fetch per pending source, log OK/BLOCKED/DEAD/PAYWALL) next time there is headroom, or folding it into the next monthly review.
