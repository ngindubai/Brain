---
title: Building 5000 Websites with Claude Code
tags: [reading-list, summary, claude-code, web-design, engineerkit, freelance]
updated: 2026-06-29
source: https://x.com/hey_madni/status/2070489937418527104
author: "@hey_madni"
related:
  - "[[Reading List]]"
  - "[[Guide - Cinematic Sites with EngineerKit]]"
  - "[[SEO Portfolio]]"
  - "[[Products]]"
  - "[[CLAUDE]]"
---

# Building 5000 Websites with Claude Code

**Source:** [@hey_madni on X](https://x.com/hey_madni/status/2070489937418527104), 26 June 2026, 88K views.

## The idea in one line

Use a paid Claude Code plugin called EngineerKit and its `/eng-site` command to generate a full cinematic website (optionally with AI images and a looping hero video) in minutes, then sell it to local businesses at market rate.

## The method

- **Tool:** EngineerKit ($14.99/month, theclaudekit.com). The `/eng-site` command takes one line of description and outputs a ready folder.
- **Full AI path:** needs a Gemini API key (aistudio.google.com/apikey), a Higgsfield account for video, and ffmpeg installed. Add `--images` for AI stills, `--video` for the hero clip. Deploy the output folder to Vercel/Netlify/Cloudflare Pages.
- **Free path:** just EngineerKit, no API keys, no flags. Builds a working site at $0, less cinematic.
- **The business play:** target local service businesses (dentists, electricians, gyms, law firms) who have offline revenue and aren't tech-savvy. Charge $3,000-5,000 per site, deliver in a day, stack $100-200/month maintenance retainers.

## Why it might matter for Orwell

Marginally relevant. Orwell already builds sites at scale (the SEO portfolio, the comparison network) with its own stack and design system. EngineerKit is a packaged shortcut, not a capability Orwell lacks. The one genuinely useful thread is the Higgsfield MCP for AI hero video, which connects to the creative-tools research ([[ComfyUI]], [[Meshy]]) and the existing Higgsfield MCP entry in the GitHub Library. The local-business cinematic-site offer could be a KlientFlo-adjacent product, but it is a crowded, low-moat play.

## Honest read

The most promotional of the four, effectively an ad for a $14.99/month product. The revenue maths ($15,500/month from 4 sites plus 10 retainers) is aspirational and ignores client acquisition, the hardest part by far. The "4 minutes" and "$0.12" figures are best-case and exclude the Gemini/Higgsfield usage costs and the real work of sales, revisions, and support. The underlying technique (Claude Code + a site-generation skill + Higgsfield video) is real and reproducible without EngineerKit if you write the skill yourself. No guide built beyond a lightweight setup walkthrough, because the value here is the tool pointer, not a deep method.
