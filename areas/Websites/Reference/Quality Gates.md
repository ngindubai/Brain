---
title: Quality Gates
tags: [websites, gates, qa, reference]
updated: 2026-07-22
---

# Quality Gates

What must pass before any commit, on any site. All gates pass or nothing pushes. No baseline edits to force a commit through. Gates are scoped to the batch (`--changed` mode) so corpus debt never blocks new correct work; whole corpus reports stay informational and feed the remediation backlog.

## Content sites: the seven gates

Run `python3 scripts/run-gates.py` from the repo root (orwell-replica and Warmhomes implementation; mortgagecompare runs the equivalent five scripts individually).

| # | Gate | Fails if |
|---|---|---|
| 1 | Internal links | Any internal link, sitemap entry or llms.txt link does not resolve to a repo file; breadcrumb missing; article missing from a feed |
| 2 | Images | An image ref does not resolve, or a non decorative image lacks alt text |
| 3 | Dates | Schema dates are not the real build date; a stale month year stamp sits in a title or meta |
| 4 | Claims | Any statistic is not a claim marker backed by claims.json, or a claim is older than 6 months |
| 5 | Cannibalisation | The keyword already has an owner page; the new page is not registered in the intent map this commit; a superseded slug is linked or sitemapped |
| 6 | Style | Banned words, banned frames, em dashes, or any sentence over 8 words duplicated verbatim across articles; burstiness warning |
| 7 | Schema | JSON-LD does not parse; a required type is missing; FAQ names do not match H3s; any rating or review schema exists |

Mechanical traps that fail gates: unescaped special characters in claims, `&` unescaped in visible text, one mistyped `@type`, a reused closing line.

## Programmatic sites: the batch checks

Run `npm run check:batch` (pest-control-usa) or the Python equivalents (pet-transport `qa_audit.py`, `check_titles.py`, `check_descs.py`, `check_schema.py`) before every commit.

| Check | Gate |
|---|---|
| Word floors | Every new page clears its tier floor (T1 800, T2 500, T3 350 unique body words). Changed scope blocks; whole corpus reports only |
| Banned vocabulary | Zero occurrences in the batch's new content. The single canonical list lives in the site CLAUDE.md and the check script must never drift from it |
| Body similarity | No pair of pages shares more than 15% body copy (shingle overlap vs same silo peers). Flagged pairs get a structural rewrite before the batch is done |
| Template distribution | A to E rotation held between 15% and 25% each; no H2 string identical on more than 30% of pages in a template bucket; no DOM skeleton cluster over 25% of a silo |
| Count reconciliation | `verify_build_state.py --write` (or equivalent) recounts from disk. Hand edited counts are banned; a SessionStart hook checks drift every session |

## The docs discipline (every commit, both archetypes)

- [ ] BUILD-PLAN.md gets a session log row: date, what was built, new counts, what is next.
- [ ] build_state.json updated by the verify script, never by hand.
- [ ] MEMORY.md Current State block updated.
- [ ] All bundled in the same atomic commit as the content. A dangling content commit without its docs update is a failed run.

## The live link review gate (after every deploy)

Deploy is automatic on push, so review happens after publish. After every batch: post the full live URL of every new or changed page, one page per line, one clickable link per line, never grouped or truncated, grouped new vs changed, with the expected deploy time. Template changes name a representative sample plus the homepage. Skipping the link post is a failed run. On Slack, blank lines between bare URLs or `- ` bullets keep them clickable.

## Routine safety rails (unattended runs)

Branch guard (halt if not on the production branch), budget tripwire (halt on any usage or rate limit, post PAUSED, never retry the build), skip check by commit log not date, atomic commit with two retries then a COMMIT FAILED alarm, remote SHA verification after push, and a named Slack post for every halt state. Silence is never a valid outcome.
