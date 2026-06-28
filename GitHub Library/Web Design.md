---
title: Web Design
tags: [github-library, web-design, animation, scroll, frontend]
updated: 2026-06-24
---

# Web Design

Animation, scroll, 3D and frontend-craft repos. The toolkit behind premium, motion-rich sites, the kind agencies charge $6k-35k for. Back to [[GitHub Library]]. Paired research: [[Advanced Web Design]].

| Repo / Source | What it is | What we'd pull | Feeds | Status |
|---|---|---|---|---|
| [darkroomengineering/lenis](https://github.com/darkroomengineering/lenis) | ~3kB smooth-scroll library (formerly Studio Freight). Production standard. Runs on native scroll, React/Vue/Framer adapters, snap plugin. Drop-in via CDN, no build step | The smooth-scroll layer for every motion site. Improves INP/Core Web Vitals too | [[Products]], [[SEO Portfolio]] | using |
| [greensock/GSAP](https://github.com/greensock/GSAP) | Industry-standard JS animation library. ScrollTrigger (positional scroll math), ScrollSmoother, timelines, custom eases | The animation engine. Pairs with Lenis on one ticker | [[Products]] | using |
| [github.com/topics/gsap-scrolltrigger](https://github.com/topics/gsap-scrolltrigger) | GitHub topic hub: hundreds of Awwwards-inspired scroll/animation templates and clones | Starter templates and effect references to reskin | [[Advanced Web Design]] | evaluating |
| [AKCodez Higgsfield UGC pipeline gist](https://gist.github.com/AKCodez/0d3f9874d0e147bd75a097ca0cc1dcc3) | Full Claude Code + Higgsfield + Playwright UGC automation: custom skills, CLAUDE.md rules, batch generation | The skills + CLAUDE.md + Playwright pattern for repeatable asset pipelines | [[Products]] | evaluating |

## Reference sources (not repos, worth tracking)

- [Codrops (tympanus.net)](https://tympanus.net/codrops/) - the best source for scroll-driven animation tutorials with full code. Infinite scroll, sticky grids, dual-wave text, etc.
- [DevDreaming Lenis + GSAP guide](https://devdreaming.com/blogs/nextjs-smooth-scrolling-with-lenis-gsap) - current (Apr 2026) Next.js 15/16 + Lenis 1.x + GSAP setup.
- [Svilenkovic scrollytelling trends 2026](https://svilenkovic.com/3d/scrollytelling-trends-2026) - where the trends are going: Lenis dominance, view-timeline CSS, ScrollTrigger 4.0, WebGPU fallbacks.
