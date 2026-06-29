---
title: Guide - Loop Engineering
tags: [guide, how-to, claude-code, loops, automation, codex]
updated: 2026-06-29
related:
  - "[[Guides]]"
  - "[[Loop Engineering - 14 Step Roadmap]]"
  - "[[Guide - Claude Loops While You Sleep]]"
  - "[[Agent Org]]"
---

# Guide - Loop Engineering

Built from [[Loop Engineering - 14 Step Roadmap]] (@0xCodez). How to decide whether you need a loop, then build the smallest one that works without hurting you. The most important part is the test at the start: most people do not need a loop yet.

## Tier 1: Should you even build a loop?

### Step 1: Run the 4-condition test. All four must be true.

- [ ] **The task repeats**, at least weekly. One-off job → use a good prompt, not a loop.
- [ ] **Verification is automated**: a test, type check, linter, or build can fail the work without you in the room.
- [ ] **Your token budget can absorb waste.** Loops re-read, retry, explore, and burn tokens whether or not anything ships. On a $20 metered plan, heavy loops are reckless.
- [ ] **The agent has senior-engineer tools**: logs, a reproduction environment, the ability to run the code it writes.

Miss one and stop here. The loop will cost more than it returns.

### Step 2: Run the 30-second tactical check on the specific task.

- [ ] Happens at least weekly.
- [ ] A test/type check/build/linter can reject bad output.
- [ ] The agent can run the code it changes.
- [ ] The loop has a hard stop (token budget, iteration count, or time limit).
- [ ] A human reviews before anything irreversible (merge, deploy, dependency change).

**Good first loops:** CI failure triage, dependency-bump PRs, lint-and-fix passes, flaky-test reproduction, issue-to-PR drafts on well-tested code.

**Bad first loops (need a human in the chair):** architecture rewrites, auth or payments code, production deploys, vague product work, anything where "done" is a judgment call.

## Tier 2: The five building blocks

### Step 3: Set up the automation (the heartbeat).

- [ ] In Claude Code, use `/loop` for a session-scoped cadence, Desktop scheduled tasks for restart survival, or Routines for laptop-off cloud runs.
- [ ] Use `/goal` when you want it to run until a condition is actually true, not just on a timer.
- [ ] Example: `/loop 30m /goal All tests in test/auth pass and lint is clean. Scan src/auth for new failures, propose fixes in claude/auth-fixes, open draft PR when goal condition holds.`

### Step 4: Use worktrees for parallel work.

- [ ] The moment you run more than one agent, give each its own git worktree so their edits cannot collide.
- [ ] In Claude Code: the `--worktree` flag opens a session in its own checkout; `isolation: worktree` on a subagent gives each helper a fresh checkout that cleans itself up.
- [ ] Remember the real ceiling is your review bandwidth, not the tool.

### Step 5: Write a skill so context isn't re-derived every run.

- [ ] Create a `SKILL.md` folder holding the project conventions, build steps, and "we don't do it like this because of that incident" rules.
- [ ] A loop without a skill re-derives your whole project context from zero every cycle. With one, intent compounds.

### Step 6: Add connectors via MCP so the loop touches real tools.

- [ ] GitHub first: read repos, create branches, open PRs, comment on issues. Biggest day-one win.
- [ ] Then Linear/Jira (update tickets, link PRs), Slack (post results, ping on escalations), your error tracker (investigate alerts).

### Step 7: Split the maker from the checker with sub-agents.

- [ ] Have one agent write and a separate agent check, ideally a different model. The model that wrote the code is too nice grading its own homework.
- [ ] In Claude Code, define subagents in `.claude/agents/`. The usual split: one explores, one implements, one verifies against the spec.

## Tier 3: Build it right or don't build it

### Step 8: Create the state file. This is the spine.

- [ ] Make a markdown file (e.g. `STATE.md` in the repo) or a Linear board that lives outside the conversation and records what is done and what is next.
- [ ] Include sections: last run, in progress, completed today, escalated to humans, lessons learned, stop conditions met.
- [ ] "The agent forgets, the repo does not." Without state, every run restarts instead of resuming.
- [ ] For long loops, pair it with a standing `VISION.md` or `AGENTS.md` the agent rereads each run. State says where it is; the spec says where to go.

### Step 9: Build the minimum viable loop. Four parts, no swarm.

- [ ] One automation (scheduled run, clear stop condition).
- [ ] One skill (the SKILL.md).
- [ ] One state file.
- [ ] One gate (the test/type check/build that fails bad work automatically).
- [ ] Order: get one manual run reliable → turn it into a skill → wrap it in a loop → then schedule it. Skipping ahead is how loops fail in production.
- [ ] Track **cost per accepted change**. If your accepted-change rate is below 50%, the loop is losing: you're doing the review work it was meant to save.

### Step 10: Defend against the failure modes.

- [ ] **Ralph Wiggum loop** (exits on a half-done job): use an objective gate (test passes/fails, build compiles/doesn't), never a verifier that just has an opinion.
- [ ] **Goal drift** (constraints vanish by turn 47): standing VISION.md reread each run.
- [ ] **Self-preferential bias**: separate verifier subagent with no exposure to the maker's reasoning.
- [ ] **Agentic laziness** ("done enough"): `/goal` with an objective stop condition checked by a fresh model.

### Step 11: Pay the security tax.

- [ ] Add security checks to the gate (SAST, dependency audit, secret scanning) so insecure generated code can't merge automatically.
- [ ] Audit any skill's source before installing. Skills are prompt-injection vectors (520 of 17,022 audited skills were found to leak credentials).
- [ ] Disable verbose logging in production loops so credentials don't scatter across logs.
- [ ] Re-audit permissions every 30 days. Scope creep is how a read-only loop quietly gains write access.

## The one-line summary

Most developers don't need a loop yet. If you pass the 4-condition test, build small: one automation, one skill, one state file, one gate. Get a manual run reliable first. Stay the engineer, read the diffs.
