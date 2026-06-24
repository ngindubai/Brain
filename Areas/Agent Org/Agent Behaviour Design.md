---
title: Agent Behaviour Design
area: Agent Org
tags: [agents, behaviour, design, observability]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-24
---

# Agent Behaviour Design

From "The Glass Office", the companion to [[Humanless Company Design]]. How the agents behave, coordinate, and are watched. Feeds the visual office in [[Orwell Corp Office]]. Part of [[Agent Org]].

## The central behaviour lesson

Left to free-form chat, agents drift, form odd social dynamics, and get stuck. This is proven by the agent-society experiments, not theoretical. So behaviour is constrained by design:

- **Coordinate through the blackboard, not conversation.** Agents read and write shared state with a status field. No agent messages another.
- **Recommendation-only by default for the marketing agents,** enforced by withholding the publish and send tools, not by instruction. See [[Marketing Department]].
- **Quality control as a watchdog chain.** A three-tier watchdog and circuit-breaker layer catches bad output before it spreads (the gastown pattern).

## Observability: the glass office

The point of the visual office is to watch real working agents, not a toy. Agents appear as workers; events (a PR review, a standup, an approval alert) drive the view, with camera-lock onto a worker. This is the design target for the Orwell Corp 3D office.

## Prior art reviewed (around 20 builds)

**Visualisers wired to real agents:** CLAW3D (3D isometric, nearest to the end state), claude-office (paulrobello, PixiJS), agents-in-the-office (gukosowa, Tauri/Rust, hook-driven), agent-office (Pixel-Process-UG), pixel-agents (the canonical VS Code extension), pixtuoid (Rust ASCII), agent-world-viewer (wojacklabs, Three.js), claude-code-agent-visualizer (tormodt), gastown (three-tier watchdog chain, relevant to QC).

**Self-running company prototypes:** agent-office (harishkotra, self-growing teams that hire, Colyseus and SQLite), ai-simulated-startup (simerusm, CEO/CTO/Marketer under one orchestrator).

**Society research, the cautionary tales:** Generative Agents / "Smallville" (the origin, and it drifts), AI Village (free-form collaboration gets stuck), Emergence World (ten agents forming governments and breaking down), SIMA 2 (DeepMind, embodied), VirtualHome-Social (coordination research).

Source: chat 8ed658bc. The full original HTML lives in that conversation.
