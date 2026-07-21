---
title: Fix And Enhance Flow
tags: [websites, fixing, enhancement, audit, flow]
updated: 2026-07-22
---

# Fix And Enhance Flow

Turns [[Monitoring Flow]] findings into shipped fixes, and periodic audits into upgrade programmes. The core principle from the live repos: **every fix becomes a forward rule**, written into the site's CLAUDE.md born correct constants so the problem cannot recur on new pages. A fix that does not update the rules is half done.

## Triage

- [ ] P1 (indexing collapse, manual action, deploy broken, wrong facts on a YMYL page, fabricated content found): fix in the current session, ahead of all build work.
- [ ] P2 (gate failures, broken links live, schema errors, lead tracking broken, cannibalisation): fix this week, may share a session with build work.
- [ ] P3 (corpus debt: banned vocab backlog, word count remediation, template refresh): a named, tracked remediation project with its own log. Never lets it block fresh correctly built batches; the `--changed` scoped gates exist exactly so new work is judged on its own merits.

## The audit pass model (for enhancement programmes)

When a site needs a full upgrade rather than a point fix, run it as a numbered multi pass audit (the mortgagecompare v4 pattern: five passes, each with its own findings and shipped fixes). Per pass:

- [ ] 1. Scope one dimension per pass (technical/indexing, on page/schema, content quality and cannibalisation, internal linking and architecture, conversion and design).
- [ ] 2. Gather evidence with tools, not opinion: crawls, GSC exports, gate scripts, live browser checks across all templates.
- [ ] 3. Record everything in a dated build plan file in the repo: `docs/build-plans/<NAME>-YYYY-MM-DD.md`, decisions, shipped, pending. Check the latest file there before starting so effort is not duplicated.
- [ ] 4. Ship fixes in gated batches with the docs update and live link review, same as build work.
- [ ] 5. Append every applied fix and every outstanding trap to `docs/seo-upgrade-log.md`. The build routine reads this file; a new page must not reintroduce anything marked Applied.
- [ ] 6. Promote the fix to a born correct rule in CLAUDE.md.

## Standing fix rules learned from the portfolio (apply everywhere)

- Canonicals self reference; never point one page's canonical at another as a fix.
- Never resolve cannibalisation by publishing a third page: pick the owner, 301 the loser, move it to the intent map superseded list, and purge internal links to it (links must point at final URLs, never through a redirect hop).
- Sitemaps never contain a redirecting or superseded URL. Large sitemaps split by section.
- Schema fixes: valid JSON-LD, no double escaping, no TODO placeholder strings, never any rating or review schema.
- Fabricated anything (a rate, a rating, a testimonial, a company history) is a P1: purge sitewide the day it is found, then ban it in the rules. This has happened (the 3.25% rate, the pest control About page) and the purge plus rule pattern is what stopped it recurring.
- Freshness fixes are real edits with real dateModified bumps, never a date bump without a change.
- Deploy failures on Hostinger FTP are usually transient control socket timeouts: re trigger, never rewrite the workflow (see the mortgagecompare CLAUDE.md standard fix).
- Wrong or stale counts: run the verify script with --write, never hand edit.

## Fix session prompt (paste into a fresh chat with the finding)

```
You are running a fix session for <SITE>, repo ngindubai/<REPO>. Read the repo CLAUDE.md in full first; it is the single source of truth and its rules bind you (deploy branch, English variant, banned vocabulary, born correct constants). Read docs/seo-upgrade-log.md and the newest file in docs/build-plans/ so you do not repeat or undo prior work. The finding: <PASTE THE FINDING WITH EVIDENCE FROM THE HEALTH REPORT>.

Work this order: 1) Reproduce and size the problem with evidence (queries, crawls, script output), never assume the report is exactly right. 2) Identify the root cause and check ERRORS.md and MEMORY.md for prior attempts. 3) Ship the smallest correct fix in a gated batch: run the repo's gate scripts scoped to the change, bundle the docs update (BUILD-PLAN.md, build_state.json via the verify script, MEMORY.md) in the same commit, push to the production branch. 4) Post every changed live URL, one per line. 5) Append the fix to docs/seo-upgrade-log.md and, if the same problem could recur on future pages, add or amend the born correct rule in CLAUDE.md in the same commit. 6) If the fix reveals a wider corpus debt, do not attempt to fix the whole corpus now: size it, file it as a named remediation project in BUILD-PLAN.md, and state what the --changed scoped gate now prevents.

Never touch .github/workflows via the connector (403; provide file content for manual paste). Never edit the live branch. Never delete anything without stating what and why first.
```
