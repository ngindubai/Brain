---
title: Guide - The Trinity One-Person-Company System
tags: [guide, how-to, obsidian, claude-code, hermes, one-person-company]
updated: 2026-06-29
related:
  - "[[Guides]]"
  - "[[Trinity System - Hermes Obsidian Claude Code]]"
  - "[[Agent Org]]"
  - "[[Hermes Agent Personal AI OS]]"
---

# Guide - The Trinity One-Person-Company System

Built from [[Trinity System - Hermes Obsidian Claude Code]] (@cyrilXBT). Stack three tools so you never dig for an answer: Obsidian remembers, Claude Code processes, Hermes operates. Build them in this order, because each makes the next more useful.

> Note for Gareth: you already have most of this. The Brain vault is layer one, Claude Code is layer two, Hermes was installed as the orchestrator. Use this as a checklist to find the gaps, not a from-scratch build.

## Layer 1: Obsidian as memory

- [ ] Create a vault (or use the existing Brain vault).
- [ ] Make two top-level folders: `raw/` for unprocessed input, `wiki/` (or your existing area structure) for clean, linked, permanent notes.
- [ ] Create a `CLAUDE.md` at the vault root. Make it specific: exact folder rules, how to handle a duplicate topic, when to create a new note vs extend an existing one. Vague instructions produce inconsistent filing.
- [ ] Build the capture habit first. For a few days, just drop things into `raw/`, badly if necessary, until it is automatic. Captured beats perfect.

## Layer 2: Claude Code as processor

- [ ] Open the vault folder in Claude Code so it has read/write access to everything.
- [ ] Drop one real source into `raw/` (a transcript, an article, a screenshot).
- [ ] Tell Claude Code to ingest it: read it, pull the genuinely new ideas, check them against the existing wiki, and either extend a note or create one with backlinks.
- [ ] Watch what it does before trusting it with more. Correct the CLAUDE.md if the filing is off.
- [ ] Repeat. The value compounds: each source makes the next easier to place because Claude is working against a growing map, not a blank page.

Three jobs this layer does for a solo operator: knowledge capture (sources distilled and filed automatically), decision logging (decisions plus reasoning written where you can find them), and drafting (emails/proposals/content drawn from your actual vault so they sound like you).

## Layer 3: Hermes as operator

- [ ] Only start this once you know which routine tasks are genuinely repeatable. Do not automate everything on day one.
- [ ] Set up the agent. The article's path: one-click at agent.minimax.io for MaxHermes, which runs inside Telegram. (Orwell already runs Hermes as its orchestrator; use that instead of standing up MaxHermes unless you want the Telegram front-end specifically.)
- [ ] Hand it one low-stakes, reversible task. Customer-inquiry first response, overnight research compile, scheduled follow-up.
- [ ] Review its output closely for the first few weeks. Treat it like a new hire: tight leash first, loosen as the track record earns it.
- [ ] Let the learning loop work. After a complex task Hermes generates a reusable skill and stores it, so repeated tasks get faster. The skill library starts empty and fills over a week of real use.

## The morning routine this produces

- [ ] Ask the vault for a status update across active projects (pulled from notes you wrote, not memory).
- [ ] Review what Hermes handled overnight.
- [ ] Drop yesterday's new information into `raw/` and let Claude Code file it.
- [ ] Spend actual working hours only on the judgment calls that need a human.

## Where it breaks (avoid these)

- **Obsidian becomes a dumping ground.** Raw piles up, nothing moves to wiki. Fix: a standing weekly ingestion habit, even just once a week.
- **Vague CLAUDE.md.** Produces unpredictable filing. Fix: be exact about structure and rules.
- **Trusting Hermes too early.** Overnight autonomy is not unattended trust. Fix: start low-stakes, verify for weeks, expand slowly.

## The honest expectation

Week one feels like more setup than payoff because the vault is thin and the agent has no skills yet. That is the system before it has anything to compound on, not a sign it doesn't work. By month two or three the gap between this and doing everything manually stops being subtle.
