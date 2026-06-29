---
title: Claude Loops While You Sleep
tags: [reading-list, summary, agentic-ai, claude-code, loops, routines, cron]
updated: 2026-06-29
source: https://x.com/hanakoxbt/status/2065807526268920103
author: "@hanakoxbt"
related:
  - "[[Reading List]]"
  - "[[Guide - Claude Loops While You Sleep]]"
  - "[[Loop Engineering - 14 Step Roadmap]]"
  - "[[Agent Org]]"
  - "[[CLAUDE]]"
---

# Claude Loops While You Sleep

**Source:** [@hanakoxbt on X](https://x.com/hanakoxbt/status/2065807526268920103), 13 June 2026, 1.4M views.

## The idea in one line

A loop is just Claude on a schedule via cron. One prompt runs once and dies; a loop runs on its own, repeatedly, and many loops in parallel let one person do the volume of a team.

## The method

- **A loop is Claude + cron.** Tell Claude to schedule a job and how often to repeat. No framework, no orchestration layer. The simplest thing that works.
- **Match the interval to the task.** Fast-changing things get tight loops (CI watcher every few minutes). Slow things get a nightly pass (daily summary waiting in the morning).
- **Parallel loops are the real power.** A handful, each owning one job: one babysits PRs and fixes failing CI, one keeps the test suite healthy, one clusters feedback every 30 minutes. None need you.
- **Routines move loops to the server** so closing the laptop doesn't stop them. Configure once, runs on a schedule/webhook/API call whether your machine is on or not.
- **Start with one loop, not ten.** The day-one mistake is building the whole system at once; it collapses by the weekend because you can't tell which loop did what.
- **Keep a human on the risky 5%.** Each loop has a lane. A PR babysitter can rebase and fix CI on its own, but merging to main still pings you. Set boundaries once in the loop's instructions.

## A good first loop has three properties

- Runs on a clear schedule.
- Has a narrow job it can't misread.
- Output you can glance at in seconds.

"Improve the codebase" is a wish. "Find functions over 50 lines and open an issue for each" is a loop.

## Why it matters for Orwell

This is the plain-language version of what the intelligence-report Routines already do, and a useful sanity check on the daily-brief design: narrow job, clear schedule, glanceable output. The "start with one" warning is exactly the lesson from setting up the six-category brief (which is why niche is weekly and the others phased).

## Honest read

The lightest of the four. Same substance as the Loop Engineering piece but without the rigour, the 4-condition test, or the failure-mode analysis. The "person who built Claude Code runs thousands of agents from his phone" hook refers to Boris Cherny and is real, but the figures are presented for awe, not accuracy. Ends in a Telegram-channel funnel. Read the Loop Engineering summary instead if you only read one; this is the motivational version.
