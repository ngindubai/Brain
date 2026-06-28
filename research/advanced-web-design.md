---
title: Advanced Web Design
area: research
tags: [research, web-design, animation, scroll, gsap, lenis, higgsfield, motion-websites]
status: exploring
updated: 2026-06-23
related:
  - "[[areas/products/products]]"
  - "[[areas/seo-portfolio/seo-portfolio]]"
  - "[[github-database/web-design]]"
  - "[[github-database/mcp-servers]]"
  - "[[github-database/skill-libraries]]"
source: https://x.com/zeuuss_01/status/1935009289... (Higgsfield motion-website playbook thread, 17 Jun 2026)
---

# Advanced Web Design

The main topic. We are learning this. The craft of premium, motion-rich, scroll-driven websites, and the AI workflow that now produces them at near-zero marginal cost.

## The idea in one line

Learn to build the cinematic, scroll-driven sites that agencies bill $6k-35k for, using both the underlying craft (GSAP, Lenis, Three.js) and the AI automation layer (Claude Code + Higgsfield MCP) that assembles them in one session.

## Why it matters

Two angles, both earn:

1. **Sellable deliverable.** A live, motion-rich site closes deals a deck cannot. The Higgsfield + Claude Code workflow drops marginal cost to a subscription plus a few dollars of credits, against an agency floor of ~$5,280 average / $6k-35k boutique. Build once, reskin, resell. Direct fit for the KlientFlo client-build channel.
2. **Portfolio lift.** Better sites across the SEO portfolio and comparison network. Smooth scroll also improves INP and Core Web Vitals, which is an SEO win, not just a cosmetic one.

## The two layers

### Layer 1: the craft (do this to actually understand it)

The production stack for premium scroll sites in 2026:

- **Lenis** ([darkroomengineering/lenis](https://github.com/darkroomengineering/lenis)) - smooth scroll, ~3kB. Handles momentum and easing.
- **GSAP + ScrollTrigger** - the animation engine. ScrollTrigger does the positional math, ScrollSmoother is an alternative to Lenis.
- **Three.js** - for 3D heroes and WebGL scroll scenes.
- They sync on one `gsap.ticker` loop. That sync is the whole trick to jank-free motion.
- Effects that signal "premium": film grain, particles, vignette, glass cards, colour tints, scroll pacing, pinned sections, parallax, staggered reveals.

Best learning sources: Codrops (tympanus.net) for full-code tutorials, DevDreaming for the current Next.js + Lenis + GSAP setup, the gsap-scrolltrigger GitHub topic for Awwwards-style templates to dissect.

### Layer 2: the AI automation (do this to ship fast)

Higgsfield shipped a **Motion Website Generator** Claude skill (June 2026). The pipeline:

1. Drop in a brand kit + business details.
2. Claude generates motion clips via the **Higgsfield MCP** (30+ models behind one connector).
3. Claude extracts every frame, writes the HTML/CSS, assembles a scroll-driven site.
4. Applies six cinematic effects with zero config: film grain, particles, vignette, glass cards, colour tints, scroll pacing.

It runs on two bits of Higgsfield plumbing: the MCP and Vibe Motion (a code-generating motion-graphics engine). The skill is just the recipe that makes the output consistent every run. Coordinates 4-6 systems (GSAP ScrollTrigger, Lenis, frame extraction, asset optimisation, layout, copy) in one agentic session.

## The economics (from the playbook)

- Agency pricing 2026: $2,500-$10,000+ standard, $6,000-$35,000+ boutique, ~$5,280 average project. Billed at $100-149/hr.
- Our marginal cost: a Claude subscription + a few dollars of Higgsfield credits.
- When delivery cost approaches zero, every price above it is margin. Build once, reskin, resell.
- Go-to-market: lead with a portfolio not a pitch. Build 3 niche demos (SaaS, e-commerce, local service). "Here's a live site for a business like yours" beats a proposal. ~63% of people prefer watching a short product video before buying, and a motion site is that, as the whole page.
- Best-fit clients: Shopify/Amazon sellers, Kickstarter campaigns, local SMBs with basic static sites.

## Open questions

- Do we learn the craft first, or go straight to the Higgsfield skill and reverse-engineer? (Leaning: do one hand-built Codrops tutorial so we can debug the AI output, then automate.)
- Which Orwell channel does this feed first - KlientFlo paid builds, or upgrading our own portfolio sites?
- What does a Higgsfield credit run actually cost per finished site? Need a real number before pricing.
- Can we package this as a repeatable KlientFlo product (fixed brief in, motion site out)?
- How well does the output score on Core Web Vitals once it is asset-heavy? Motion vs INP trade-off.

## What would make this a project

Any one of:
1. A first paying client who wants a motion site.
2. A decision to make "motion sites" a packaged KlientFlo offering.
3. One built demo good enough to lead the portfolio with.

## Tooling (filed in the github database)

All repos and sources for this live in [[github-database/web-design]], plus the Higgsfield MCP in [[github-database/mcp-servers]] and the Motion Website Generator skill in [[github-database/skill-libraries]].

## Notes

### Source correction

This note is built from the Higgsfield motion-website playbook thread by @zeuuss_01 (17 Jun 2026), which is the article actually intended. An earlier note, [[research/hermes-agent-personal-ai-os]], was filed against the wrong tweet ID and covers a different Zeus thread about the Hermes Agent. Kept because it is still useful, but it is not this topic.
