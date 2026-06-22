---
title: Agent behaviour design (The Glass Office)
area: agent-org
tags: [agents, behaviour, design, observability]
source: https://claude.ai/chat/8ed658bc-9b08-4a45-84bd-3561ee4dc195
updated: 2026-06-22
---

# Agent behaviour design

From "The Glass Office", the companion to [[areas/agent-org/humanless-company-design]]. How the agents behave, coordinate, and are watched. Feeds the visual office in [[projects/orwell-corp-office/orwell-corp-office]]. Part of [[areas/agent-org/agent-org]].

## The central behaviour lesson

Left to free-form chat, agents drift, form odd social dynamics, and get stuck. This is proven by the agent-society experiments, not theoretical. So behaviour is constrained by design:

- **Coordinate through the blackboard, not conversation.** Agents read and write shared state with a status field. No agent messages another.
- **Recommendation-only by default for the marketing agents,** enforced by withholding the publish and send tools, not by instruction. See [[projects/marketing-department/marketing-department]].
- **Quality control as a watchdog chain.** A three-tier watchdog and circuit-breaker layer catches bad output before it spreads (the gastown pattern).

## Observability: the glass office

The point of the visual office is to watch real working agents, not a toy. Agents appear as workers; events (a PR review, a standup, an approval alert) drive the view, with camera-lock onto a worker. This is the design target for the Orwell Corp 3D office.

## Prior art reviewed (around 20 builds)

**Visualisers wired to real agents:** CLAW3D (3D isometric, nearest to the end state), claude-office (paulrobello, PixiJS, multi-floor command centre), agents-in-the-office (gukosowa, Tauri/Rust, hook-driven events), agent-office (Pixel-Process-UG), pixel-agents (the canonical VS Code extension), pixtuoid (Rust ASCII, hook-safe), agent-world-viewer (wojacklabs, Three.js, runs via npx), claude-code-agent-visualizer (tormodt), gastown (three-tier watchdog chain, relevant to QC).

**Self-running company prototypes:** agent-office (harishkotra, self-growing teams that hire, Colyseus and SQLite), ai-simulated-startup (simerusm, CEO/CTO/Marketer under one orchestrator).

**Society research, the cautionary tales:** Generative Agents / "Smallville" (the origin, agents as a society, and it drifts), AI Village (free-form collaboration gets stuck), Emergence World (ten agents forming governments and breaking down), SIMA 2 (DeepMind, embodied, the far horizon), VirtualHome-Social (coordination research, background for the comms design).

Source: chat 8ed658bc. The full original HTML lives in that conversation.
