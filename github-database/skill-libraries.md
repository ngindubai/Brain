---
title: Skill Libraries
area: github-database
tags: [github-database, skills, agentskills, libraries]
updated: 2026-06-23
---

# Skill Libraries

Reusable agent skills we can lift or adapt. The agentskills.io open standard makes these portable across Claude, Hermes, OpenClaw and others. Back to [[github-database/github-database]].

| Repo / Source | What it is | What we'd pull | Feeds | Status |
|---|---|---|---|---|
| [skills.sh](https://www.skills.sh) ([vercel-labs/skills](https://github.com/vercel-labs/skills)) | Vercel's open agent-skills directory and CLI. `npx skills add owner/repo`. Hermes is a supported runtime | The install path and the directory itself; find-skills | [[areas/agent-org/agent-org]], [[research/agent-skills-ecosystem]] | using |
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | The marketing skill pack we already vendor, maintained: seo-audit, copywriting, ai-seo, schema-markup, programmatic-seo, page-cro, competitor-alternatives, pricing-strategy and more | ai-seo, schema-markup, competitor-alternatives, pricing-strategy plus the existing set, pinned to a SHA | [[areas/agent-org/agent-org]], [[areas/comparison-network/comparison-network]] | using |
| [obra/superpowers](https://github.com/obra/superpowers) | Process and quality skills for how an agent operates and how we build | verification-before-completion, subagent-driven-development, dispatching-parallel-agents, writing and executing plans | [[areas/agent-org/agent-org]] | using |
| [anthropics/skills](https://github.com/anthropics/skills) | Official Anthropic skills | webapp-testing, skill-creator, mcp-builder, frontend-design, docx and pdf and xlsx | [[areas/agent-org/agent-org]], [[areas/products/products]] | using |
| [vercel-labs/next-skills](https://github.com/vercel-labs/next-skills) | Next.js best-practice skills | next-best-practices for the Command Centre dashboard | [[areas/products/products]] | evaluating |
| [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Writing-quality skills: polish, critique, clarify, distill | Final polish pass on client-facing copy and reports | [[areas/agent-org/agent-org]] | evaluating |
| [leonxlnx/taste-skill](https://github.com/leonxlnx/taste-skill) | Design-taste skills: high-end visual design, brandkit, extract-design-system | brandkit and extract-design-system for the Brand agent; design quality | [[areas/products/products]] | evaluating |
| [xixu-me/skills](https://github.com/xixu-me/skills) | Mixed skills incl. openclaw-secure-linux-cloud (built for OpenClaw, do not install as written, take host-hardening principles only) | Host-hardening principles for the Hostinger VPS | [[reference/orwell-corp-stack-decisions]] | shelf |
| [mattpocock/skills](https://github.com/mattpocock/skills) | Engineering process skills: tdd, diagnose, triage, improve-codebase-architecture | Build-process discipline | [[areas/agent-org/agent-org]] | shelf |
| [agentskills.io](https://agentskills.io) | Open skill standard and community hub. Portable, shareable skill files | The standard our own skills/ could conform to | [[areas/agent-org/agent-org]] | shelf |
| [mukul975/Anthropic-Cybersecurity-Skills](https://github.com/mukul975) | 753+ structured cybersecurity skills mapped to MITRE ATT&CK | Security review skills for client builds and CRM hardening | [[areas/crm-systems/crm-systems]] | shelf |
| Higgsfield Motion Website Generator skill ([higgsfield.ai/skills](https://higgsfield.ai/skills)) | The downloadable Claude skill that scripts the full motion-website pipeline | The recipe for asset gen, frame extract, HTML/CSS, scroll site | advanced web design, [[areas/products/products]] | evaluating |

Note: our own internal skills live in `skills/` in this vault. This file is for **external** skills we import or model ours on. Audit findings for the Orwell-Corp set are in [[research/agent-skills-ecosystem]].
