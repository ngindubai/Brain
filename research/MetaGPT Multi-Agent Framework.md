---
title: MetaGPT multi-agent framework
tags: [research, agent-frameworks, multi-agent, software-company, agent-org, orwell-lab]
status: exploring
updated: 2026-06-25
related:
  - "[[Agent Org]]"
  - "[[Agent Frameworks]]"
  - "[[Products]]"
  - "[[Hermes Agent Personal AI OS]]"
  - "[[Agent Skills Ecosystem]]"
  - "[[Agentic AI Keyword Forecast]]"
  - "[[Orwell Corp Stack Decisions]]"
source: https://github.com/FoundationAgents/MetaGPT
---

# MetaGPT multi-agent framework

## The idea in one line

MetaGPT is a multi-agent framework that models a full software company — product manager, architect, project manager, engineers — and produces working code, docs, APIs, and data structures from a single natural-language requirement line. Its core philosophy: `Code = SOP(Team)`.

## Why it might matter

Orwell Lab builds humanless companies. MetaGPT is the closest published open-source realisation of that exact model: an LLM-staffed company with defined roles, SOPs per role, and structured hand-offs between agents. It is not a runtime we would run as-is, but the architecture, role definitions, SOP patterns, and how it structures inter-agent communication are all directly relevant to the [[Agent Org]] design.

More concretely: MGX (MetaGPT X), the commercial product launched Feb 2025, was #1 Product of the Day and #1 Product of the Week on Product Hunt in March 2025. That is market validation that "AI software company" as a product category has real consumer pull. Directly feeds the positioning in [[Agentic AI Keyword Forecast]].

## Key takeaways

- **Role-based SOP model.** Each agent carries a defined role and follows a carefully orchestrated SOP. Product manager converts requirements into user stories; architect designs data structures and APIs; engineers write and review code. The SOP enforces quality without human supervision.
- **One-line input, full deliverable output.** `metagpt "Create a 2048 game"` produces a full repo: requirements, design docs, code, tests. This is the "natural language programming" framing.
- **69k GitHub stars, 8.8k forks.** One of the highest-starred agent frameworks in existence. Active, maintained, well-documented.
- **AFlow (ICLR 2025 oral, top 1.8%, #2 in LLM agent category).** Automated agentic workflow generation: the framework can self-optimise its own workflows. Academic credibility is high.
- **MGX (mgx.dev) is the commercial product layer.** The framework is open-source; MGX is the hosted "AI development team" product. Architecture separation to note if Orwell Lab ever productises builds similarly.
- **Python only (3.9-3.11).** Not a Node/TS stack. Relevant if we consider integration or pattern-borrowing vs direct use.
- **Data Interpreter.** A sub-agent that writes and runs code for data analysis tasks. Potential reference for any data-processing role in the Orwell agent org.
- **Runs on standard infra.** pip install, no specialist hardware required.

## Open questions

- Is the SOP architecture documented well enough to extract patterns for the Orwell agent-org department design, or does it need a deeper read of the source?
- MGX is a direct competitor / market proof-point for Orwell Lab's build-partner positioning. Worth monitoring their pricing and positioning as a benchmark.
- AFlow's automated workflow generation: could this technique (auto-optimising agent workflows against a benchmark) be applied to how Orwell Lab tunes its own agent team SOPs?
- Does MetaGPT's role taxonomy (PM, Architect, PM, Engineer) map to Orwell's six departments? Where does it differ?

## What would make this a project

Two triggers: (a) we decide to do a structured architecture review of MetaGPT SOPs and extract patterns for [[Agent Org]] department definitions, or (b) we decide to benchmark Orwell Lab's build output against MGX as a competitor reference. Either warrants a project stub.

## Source

- Repo: https://github.com/FoundationAgents/MetaGPT
- Commercial product: https://mgx.dev
- ICLR 2025 paper (AFlow): https://openreview.net/forum?id=z5uVAKwmjf
- Captured 2026-06-25.
