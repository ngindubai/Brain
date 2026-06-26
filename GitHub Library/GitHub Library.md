---
title: GitHub Library
tags: [github-library, repos, skills, tools, moc, master-list]
updated: 2026-06-25
---

# GitHub Library

The external git library. Every third-party repo we pull skills, tools, or reference code from lives here, sorted by category. This is **not** Orwell's own code (that is in the live repos linked from each [[CLAUDE]] area). This is the outside world: agent frameworks, MCP servers, skill libraries, web-design kits, and anything else worth keeping a pointer to.

## How it works

- One file per category, named after the category.
- Each repo gets a row: name, link, what it is, what we'd pull from it, status.
- **Status:** `using` (in active use), `evaluating` (testing), `shelf` (parked, might use later).
- When a repo earns real use, note which Orwell area or project it feeds in the row.
- This master note is the index. The category files hold the detail.

## Categories

| Category | What it holds | File |
|---|---|---|
| Agent frameworks | Self-hosted agent runtimes and orchestration | [[Agent Frameworks]] |
| MCP servers | Model Context Protocol connectors | [[MCP Servers]] |
| Skill libraries | Reusable agent skills (agentskills.io etc) | [[Skill Libraries]] |
| Web design | Animation, scroll, 3D, frontend craft | [[Web Design]] |
| Automation tools | Browser automation, scraping, pipelines | [[Automation Tools]] |
| Creative AI tools | Image, video, 3D and audio generation engines | [[Creative AI Tools]] |
| Reference directories | Curated use-case lists, tutorial collections, prior art | [[AI Agent Use Case Directory]] |

## Master list (all repos, by category)

### Agent frameworks

| Repo | What it is | Status |
|---|---|---|
| [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent) | Self-improving autonomous agent runtime, persistent memory, self-written skills, runs on a $5 VPS, model-agnostic. The Orwell agent-org runtime | evaluating |
| [0xNyk/awesome-hermes-agent](https://github.com/0xNyk/awesome-hermes-agent) | Curated list of Hermes skills, tools, integrations | shelf |
| [FoundationAgents/MetaGPT](https://github.com/FoundationAgents/MetaGPT) | Multi-agent framework: full software company in LLM agents (PM, architect, engineer), role-based SOPs, one-line-to-repo output. 69k stars. Commercial product: mgx.dev | evaluating |

### MCP servers

| Repo | What it is | Status |
|---|---|---|
| Higgsfield MCP ([higgsfield.ai/mcp](https://higgsfield.ai/mcp)) | 30+ image/video generation models behind one connector. Works with Claude, Cowork, Claude Code | evaluating |

### Skill libraries

| Repo | What it is | Status |
|---|---|---|
| [skills.sh](https://www.skills.sh) ([vercel-labs/skills](https://github.com/vercel-labs/skills)) | Vercel's open agent-skills directory and CLI. Hermes is a supported runtime | using |
| [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) | The marketing skill pack, maintained; adds ai-seo, schema-markup, competitor-alternatives, pricing-strategy | using |
| [obra/superpowers](https://github.com/obra/superpowers) | Process and quality skills (verification, subagents, plans) | using |
| [anthropics/skills](https://github.com/anthropics/skills) | Official skills: webapp-testing, mcp-builder, frontend-design, docx/pdf/xlsx | using |
| [vercel-labs/next-skills](https://github.com/vercel-labs/next-skills) | Next.js best-practice skills for the dashboard | evaluating |
| [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | Writing-quality polish skills | evaluating |
| [leonxlnx/taste-skill](https://github.com/leonxlnx/taste-skill) | Design-taste, brandkit, extract-design-system | evaluating |
| [xixu-me/skills](https://github.com/xixu-me/skills) | Mixed; openclaw security skill not used as written, principles only | shelf |
| [mattpocock/skills](https://github.com/mattpocock/skills) | Engineering process skills | shelf |
| [agentskills.io](https://agentskills.io) | Open skill standard and community hub | shelf |
| [mukul975/Anthropic-Cybersecurity-Skills](https://github.com/mukul975) | 753+ cybersecurity skills mapped to MITRE ATT&CK | shelf |

### Web design

| Repo | What it is | Status |
|---|---|---|
| [darkroomengineering/lenis](https://github.com/darkroomengineering/lenis) | ~3kB smooth-scroll library, the production standard. React/Vue/Framer adapters | using |
| [GSAP (greensock)](https://github.com/greensock/GSAP) | Industry-standard JS animation library. ScrollTrigger, ScrollSmoother | using |
| [github.com/topics/gsap-scrolltrigger](https://github.com/topics/gsap-scrolltrigger) | Topic hub: hundreds of Awwwards-style scroll/animation templates | evaluating |
| [AKCodez Higgsfield UGC pipeline gist](https://gist.github.com/AKCodez/0d3f9874d0e147bd75a097ca0cc1dcc3) | Full Claude Code + Higgsfield + Playwright UGC build, skills + CLAUDE.md pattern | evaluating |

### Automation tools

| Repo | What it is | Status |
|---|---|---|
| [jo-inc/camofox-browser](https://github.com/jo-inc) | Stealth headless browser, bypasses Cloudflare/bot detection. Puppeteer/Playwright drop-in | shelf |
| [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) | CLI browser automation, predictable structured tasks | evaluating |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Browser automation with visual understanding | evaluating |
| [scrapegraphai/just-scrape](https://github.com/scrapegraphai/just-scrape) | Structured scraping skill | evaluating |

### Creative AI tools

| Repo / Product | What it is | Status |
|---|---|---|
| [Comfy-Org/ComfyUI](https://github.com/Comfy-Org/ComfyUI) | Node-graph diffusion engine: image, video, 3D, audio. 118k stars, REST API, self-hostable, GPL-3.0 | evaluating |
| [Meshy](https://www.meshy.ai) | AI 3D generation SaaS: text/image → textured 3D model in ~1 min. 10M users, REST API, ComfyUI plugin. Meshy 6 (Jan 2026) is production-ready | evaluating |

### Reference directories

| Repo | What it is | Status |
|---|---|---|
| [ashishpatel26/500-AI-Agents-Projects](https://github.com/ashishpatel26/500-AI-Agents-Projects) | 500+ curated AI agent use cases across industries. Organised by framework: CrewAI, AutoGen, Agno, LangGraph. 31.6k stars | shelf |
| [NirDiamant/GenAI_Agents](https://github.com/NirDiamant/GenAI_Agents) | 52 runnable notebook tutorials: beginner to advanced multi-agent systems. LangGraph, LangChain, AutoGen, CrewAI. 22k stars. Non-commercial licence | shelf |

## Adding a repo

When I drop a git link, file it: pick the category, add a row to that category file and to the master list above, set status, note any Orwell area it feeds. One commit per batch. Tell me after.
