---
title: Loop Engineering - 14 Step Roadmap
tags: [reading-list, summary, agentic-ai, claude-code, loops, automation, codex]
updated: 2026-06-29
source: https://x.com/0xCodez/status/2064374643729773029
author: "@0xCodez"
related:
  - "[[Reading List]]"
  - "[[Guide - Loop Engineering]]"
  - "[[Agent Org]]"
  - "[[Agentic AI Keyword Forecast]]"
  - "[[CLAUDE]]"
---

# Loop Engineering - 14 Step Roadmap

**Source:** [@0xCodez on X](https://x.com/0xCodez/status/2064374643729773029), 9 June 2026, 7.3M views. Sourced from Anthropic engineering docs, Addy Osmani's loop-engineering essay, and measurement studies.

## The idea in one line

The leverage point has moved from typing prompts to designing the system that prompts the agent for you: a loop that finds work, hands it to the agent, checks the result, records what happened, and decides the next move on its own.

## The honest core (this is the part most threads skip)

Most developers do **not** need a loop yet. A loop only pays off when all four conditions hold:

1. **The task repeats** (at least weekly). One-off jobs want a good prompt, not a loop.
2. **Verification is automated** (test, type check, linter, build). No automated gate means you are back in the chair reading every diff.
3. **Your token budget can absorb the waste.** Loops re-read, retry, explore. This is why it reads as obvious to people with free tokens and reckless to people on a $20 metered plan.
4. **The agent has senior-engineer tools** (logs, a reproduction environment, ability to run the code).

Miss one and the loop costs more than it returns.

## The five building blocks

- **Automations** (the heartbeat): scheduled/triggered runs. Claude Code: `/loop` for cadence, Desktop scheduled tasks for restart-survival, Routines for laptop-off cloud runs. `/goal` keeps going until a condition is true, checked by a separate small model (maker-vs-checker on the stop condition itself).
- **Worktrees** (parallel without chaos): a git worktree gives each agent its own checkout so edits cannot collide. Claude Code exposes `--worktree` and `isolation: worktree` on subagents. Your review bandwidth is still the ceiling, not the tool.
- **Skills** (write project knowledge once, read every run): a `SKILL.md` folder. A loop without skills re-derives context from zero every cycle.
- **Connectors via MCP** (touch real tools): GitHub first (biggest day-one win), then Linear/Jira, Slack, error tracker. The difference between "here is the fix" and a loop that opens the PR, links the ticket, pings the channel.
- **Sub-agents** (keep maker away from checker): the model that wrote the code is too nice grading its own homework. A separate verifier, sometimes a different model, catches what the first talked itself into. This is the evaluator-optimiser pattern from Anthropic's Dec 2024 post.

## Build it right

- **State file** is the spine. A markdown file or Linear board outside the conversation holding what is done and what is next. "The agent forgets, the repo does not." Without it, every run restarts instead of resuming.
- **Minimum viable loop:** one automation, one skill, one state file, one gate. Get a manual run reliable, turn it into a skill, wrap it in a loop, then schedule it. Order matters.
- **The metric that matters:** cost per accepted change. If accepted-change rate is below 50%, you are doing review work the loop was meant to save, and the loop is losing.

## The failure modes (named)

- **Ralph Wiggum loop:** agent emits "done" early, loop exits on a half-done job. Fix: an objective gate (test passes/fails, build compiles/doesn't), not a verifier with an opinion.
- **Goal drift:** "don't do X" constraints vanish by turn 47 as summarisation loses them. Fix: a standing VISION.md/AGENTS.md reread each run.
- **Comprehension debt:** the faster the loop ships code you didn't write, the larger the gap between what the repo contains and what you understand. Fix: read the diffs, keep the loop off architecture.
- **Security tax:** an unattended loop is an unattended attack surface. Generated code shipping unreviewed, skills as injection vectors (520 of 17,022 audited skills leak credentials), credentials in logs, permission scope creep. Re-audit permissions every 30 days.

## Why it matters for Orwell

This is the rigorous version of what the [[Agent Org]] Routines are doing. The 4-condition test is the filter for deciding which Orwell tasks deserve a Routine vs a one-off prompt. The maker-checker split and the state-file discipline are directly applicable to the content-pipeline routines. The security section is a real checklist given the API-key exposure history in the portfolio.

## Honest read

The strongest of the four sources. It actively argues against over-building, names who should skip loops, and cites primary sources (Anthropic, Osmani, Huntley). Promotes the author's LinkedIn but sells nothing. Treat the "8x more code" figure with the same scepticism Anthropic itself flags (it calls the number almost certainly an overstatement).
