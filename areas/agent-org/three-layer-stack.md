---
title: Three-layer stack (Claude and Hermes)
area: agent-org
tags: [agents, hermes, architecture]
source: https://claude.ai/chat/1b691260-9403-43f1-9bc4-118d3a273236
updated: 2026-06-22
---

# Three-layer stack

From the Hermes workflow document, 15 June. How Claude and Hermes fit together.

## The correction

"Opus for prompting, Hermes for building" was back to front. Hermes is an orchestrator that calls a model, not a builder. Quality output still needs Claude as the model behind any Hermes-triggered job.

## The three layers

- **Brain.** Opus and Projects. Strategy and prompting. Unchanged.
- **Hands.** Claude Code and the Claude API. The only thing that builds.
- **Operations.** Hermes. Always-on scheduling, memory, monitoring and notifications, with no routine cap.

This removes two current constraints: the 15-routine-per-day cap on Claude Code Routines, and the requirement for Cowork tasks to run with the desktop open.

## Build-engine families across the portfolio

Read from the live repos:

- **Family A.** Python page-stamper engines: pet-transport, funeral-repatriation, global-bus-hire, close-protection.
- **Family B.** Hand-authored static HTML, no build step: the .ae comparison and professional services sites.
- **Family C.** Next.js application build: pest-control-usa.
- **Family D.** Running software products (George/Jarvis, the CRMs): need uptime and webhook management, not scheduled builds.

## Hardware finding

No part of the build pipeline needs GPU or heavy local compute. The intelligence is Claude via the API; the compile steps run free in GitHub Actions. This is why distributed GPU was not needed on the build side.

## Billing

Hermes runs on a metered API key. It cannot draw from a subscription pool, that path is closed to third-party agents. Set a spend limit before the first run.

Source: chat 1b691260. The full original HTML lives in that conversation.
