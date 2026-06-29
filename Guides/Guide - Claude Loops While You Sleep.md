---
title: Guide - Claude Loops While You Sleep
tags: [guide, how-to, claude-code, loops, cron, routines]
updated: 2026-06-29
related:
  - "[[Guides]]"
  - "[[Claude Loops While You Sleep]]"
  - "[[Guide - Loop Engineering]]"
  - "[[Agent Org]]"
---

# Guide - Claude Loops While You Sleep

Built from [[Claude Loops While You Sleep]] (@hanakoxbt). The simple version: a loop is just Claude on a cron schedule. Start with one, then scale to parallel loops. For the rigorous version with the should-you-even-do-this test, see [[Guide - Loop Engineering]] first.

## Step 1: Understand what a loop is

- A single prompt runs once and dies. A loop runs on its own, repeatedly, without you starting it each time.
- The mechanism: Claude uses cron to schedule a job, and you tell it how often to repeat (every minute, every 30 minutes, every night).
- No framework, no orchestration layer. The simplest thing that works.

## Step 2: Build your first loop (just one)

- [ ] Pick the most annoying recurring task you have: the thing you check every morning out of habit.
- [ ] Make sure it has three properties: runs on a clear schedule, has a narrow job it can't misread, and produces output you can glance at in seconds.
- [ ] Write the job as a tight instruction. "Improve the codebase" is a wish. "Find functions over 50 lines and open an issue for each" is a loop.
- [ ] Set the interval to match the task: fast-changing things get tight loops (CI watcher every few minutes), slow things get a nightly pass (daily digest waiting in the morning).
- [ ] Let it run for a few days. Watch where it overreaches and where it misses. Tighten the instruction.

## Step 3: Keep a human on the risky part

- [ ] Give each loop a lane. The agent does the volume, you keep the judgment.
- [ ] Put a human gate on anything irreversible. A PR babysitter can rebase and fix CI on its own, but merging to main pings you. A migration loop can open a hundred PRs, but a human approves the first before the rest go out.
- [ ] Set the boundaries once, in the loop's instructions. They hold every run after. You're babysitting the rules, not the work.

## Step 4: Move loops to the server so the laptop can close

- [ ] Convert the loop to a Routine (the server version) so it runs whether your machine is on or not.
- [ ] Configure it once to run on a schedule, a webhook, or an API call.
- [ ] Now the work happens overnight and you see the result when you're ready.

## Step 5: Scale to parallel loops, slowly

- [ ] Once you trust one loop, add a second. It takes about ten minutes.
- [ ] Build up to a handful, each owning one job: one babysits PRs and fixes failing CI, one keeps the test suite healthy, one clusters feedback every 30 minutes.
- [ ] Don't build ten on day one. That collapses by the weekend because you can't tell which loop did what. Each loop should earn its place.

## What changes after a week

Day one feels like overhead: writing schedules, watching loops misfire. By the end of the week the math flips. You stop opening Claude to ask it things and start opening it to check on things it already did. The chat window becomes a status board, not a workspace.

## The trigger for spotting a loop

Anything you do more than twice, anything you keep checking manually, anything that breaks at 3am: that's a loop waiting to exist.
