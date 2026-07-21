---
title: Repo Scaffold
tags: [websites, scaffold, repo, reference]
updated: 2026-07-22
---

# Repo Scaffold

The files every site repo carries. A new build copies this shape from the newest reference repo of its archetype ([[Site Registry]] names them). If a file here is missing from a repo, that is a finding.

## Both archetypes

| File | Purpose |
|---|---|
| `CLAUDE.md` | Single source of truth, read in full every session. Carries: the 4 load bearing rules (ask don't assume, simplest first, don't touch unrelated code, flag uncertainty), the em dash ban, banned vocabulary, English variant, author model, deploy model and branch rule, born correct constants, session protocols, current status block |
| `BUILD-PLAN.md` | Session log plus what to build next, in order |
| `build_state.json` | Machine readable progress and the next unit pointer; only ever written by the verify script |
| `MEMORY.md` | Decision log plus the Current State block |
| `ERRORS.md` | Failed approach log, read before retrying anything |
| Routine prompt file | The self contained unattended build prompt (`AUTONOMOUS-BUILD-ROUTINE.md`, `docs/build-routine.md` or `insights-engine/ROUTINE-PROMPT.md` + paste ready `PROMPT.txt`) |
| `docs/seo-upgrade-log.md` | Every applied fix and outstanding trap; new pages must not reintroduce anything marked Applied |
| `docs/build-plans/` | Dated audit build plans, one per audit cycle |
| `sitemap.xml`, `robots.txt`, `llms.txt` | Registered surfaces, updated in the same commit as any page change |
| Gate scripts | `scripts/` (Python run-gates set) or npm check:* scripts; see [[Quality Gates]] |
| `.github/workflows/` deploy workflow | Auto deploy on push to the production branch. Cannot be written via the MCP connector (403): provide the full file for manual paste, enable or disable in the Actions tab |

## Programmatic additions

| File | Purpose |
|---|---|
| `workforce/` | The soul files: content workers (wordsmith, interrogator, chameleon), leadership (auditor), plus the support roster. Paths matter: souls sit under subfolders, load only what a block needs |
| `data/` | The per entity intelligence records with sources, the keyword universe, competitor analysis |
| Templates A to E | Five structurally distinct page templates plus the router; variant stored per page record, slug hash assigned |
| Generators | Batch page generators reading the data files; bulk generation without the gate is banned, generators serve gated blocks |
| `verify_build_state.py` (or equivalent) | Counts from disk, reconciles build_state.json, SessionStart hook checks drift |
| `TEMPLATE-DIVERSIFICATION-GUIDE` | The anti penalty engine rules |

## Content additions

| File | Purpose |
|---|---|
| `insights-engine/ENGINE.md` | The master rules file, read first every content session |
| `insights-engine/publishing-plan.json` + `schedule-YYYY-MM.json` | The ordered article queue; or the `content-plan/` dashboard + plan-rows files |
| `insights-engine/workers/` | The four agent specs |
| `insights-engine/data/claims.json` | Every statistic with source, url and checked date |
| `insights-engine/data/intent-map.json` | One owner page per intent plus the superseded slug list |
| `insights-engine/data/style-law.json` | The banned lists the style gate reads |
| `insights-engine/templates/article.html` | The master article skeleton (first build only; thereafter the newest live article is the reference) |
| Hub pages | The knowledge hub index and topic or feed pages, regenerated or prepended in the same commit as every article |

## Platform traps (learned, do not relearn)

- `.github/workflows/*.yml` returns 403 via the git MCP connector on every repo. Manual paste only.
- The deploy branch is per site law: Warmhomes deploys `claude/website-plan-qa-ddv99s`, not main. Check CLAUDE.md before any push.
- Hostinger FTP deploys intermittently fail with control socket timeouts. The commit is safe; re trigger the workflow, never rewrite it, never touch the FTP secret, never delete the sync state file.
- The `live` branches are orphan build output. Never edit them, never commit build output to main.
- Binary files do not commit via the MCP connector; use local git in Claude Code.
- Semrush MCP fails silently when out of API units: `execute_report` returns nothing partial. Top up at semrush.com/mcp-access, and always `get_report_schema` before an unfamiliar report.
- On stale SHA push failures: re read, re apply, push again. Never force.
