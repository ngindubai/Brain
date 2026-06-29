---
title: Trinity System - Hermes Obsidian Claude Code
tags: [reading-list, summary, agentic-ai, obsidian, claude-code, hermes, one-person-company]
updated: 2026-06-29
source: https://x.com/cyrilXBT/status/2071034792288686588
author: "@cyrilXBT"
related:
  - "[[Reading List]]"
  - "[[Guide - The Trinity One-Person-Company System]]"
  - "[[Agent Org]]"
  - "[[Hermes Agent Personal AI OS]]"
  - "[[CLAUDE]]"
---

# Trinity System - Hermes Obsidian Claude Code

**Source:** [@cyrilXBT on X](https://x.com/cyrilXBT/status/2071034792288686588), 28 June 2026, 209K views.

## The idea in one line

Stack three tools so a solo operator never has to dig for an answer: Obsidian holds everything (memory), Claude Code reads the vault and turns it into something you can talk to (processor), Hermes Agent runs in the background and gets better over time (operator).

## The three layers

- **Obsidian = memory.** Capture everything, badly if needed. Minimal structure: a `raw/` folder for unprocessed input (articles, transcripts, screenshots), a `wiki/` folder for the processed, linked, permanent version, and a `CLAUDE.md` at the root telling Claude Code how the vault works.
- **Claude Code = processor.** Open the vault in Claude Code and it has read/write access to everything. Drop a transcript into `raw`, tell it to ingest, and it pulls the new ideas, checks them against the existing wiki, and either extends a note or creates one with backlinks. The compounding is the point: month six it surfaces connections you would never make yourself.
- **Hermes Agent = operator.** The open-source framework behind MaxHermes. The differentiator is a built-in learning loop: after a complex task it generates a reusable skill and stores it permanently, so repeated tasks get faster. MaxHermes runs inside Telegram, one-click setup at agent.minimax.io, no server or API keys.

## Why it matters for Orwell

This is almost exactly the Orwell setup already in motion: the [[Brain]] vault is the memory, Claude Code is the processor, and Hermes was already installed as the agent orchestrator (see [[Hermes Agent Personal AI OS]]). The article is useful as an outside articulation of the same thesis, and as a checklist for what is missing. The build order it prescribes (Obsidian first, then Claude Code, then Hermes) matches how the Brain was built.

## Key takeaways

- Build in order. Each layer makes the next more useful. Obsidian first, capture habit first, processing second, automation last.
- "Captured beats perfect." Raw is messy by design, wiki is clean by design, the agent moves content between them, not you at midnight.
- The CLAUDE.md must be specific. "Organise notes well" produces inconsistent filing. Exact folder rules, duplicate-handling, and new-note-vs-extend rules produce a predictable system.
- Start Hermes on low-stakes, reversible tasks. Treat it like a new hire: review closely first, loosen as it earns trust.
- The compounding only shows up past week one. Early on it feels like more setup than payoff. That is the system before it has anything to compound on.

## Where it breaks (the author's own warnings)

- Treating Obsidian as a dumping ground with no processing step. Fix: a standing weekly habit of running ingestion on whatever piled up.
- Vague CLAUDE.md. Fix: be exact.
- Trusting Hermes with no verification step. Fix: start low-stakes, build trust over weeks.

## Honest read

No product being sold here directly, though it promotes MaxHermes/MiniMax and agent.minimax.io. The method is sound and matches established practice. The "one-person company" framing is aspirational marketing language, but the underlying build is real and already partly in place at Orwell.
