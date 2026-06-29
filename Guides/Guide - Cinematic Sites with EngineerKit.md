---
title: Guide - Cinematic Sites with EngineerKit
tags: [guide, how-to, claude-code, web-design, engineerkit, higgsfield]
updated: 2026-06-29
related:
  - "[[Guides]]"
  - "[[Building 5000 Websites with Claude Code]]"
  - "[[SEO Portfolio]]"
  - "[[Products]]"
---

# Guide - Cinematic Sites with EngineerKit

Built from [[Building 5000 Websites with Claude Code]] (@hey_madni). How to generate and deploy a cinematic site with Claude Code. EngineerKit is a paid ($14.99/month) plugin; the underlying technique (Claude Code + a site skill + Higgsfield video) is reproducible without it if you write the skill yourself.

> Honest note: this is built from a promotional post. The technique is real. The revenue claims around it are not verified and ignore the hard part (getting clients). Use it as a fast site-generation method, not a get-rich plan.

## Path A: Free (EngineerKit only, no API keys)

- [ ] Install EngineerKit in Claude Code: `ck install engineerkit`
- [ ] Restart Claude Code.
- [ ] Run a site build: `/eng-site a portfolio for a staff backend engineer` (swap in your own description).
- [ ] No flags needed. It builds a working site at $0.
- [ ] Deploy the output folder to Vercel, Netlify, or Cloudflare Pages.

## Path B: Full cinematic (AI images + hero video)

Extra setup for AI stills and a looping hero video.

- [ ] Get a Gemini API key at aistudio.google.com/apikey (powers the AI image generation).
- [ ] Create a Higgsfield account at higgsfield.ai (powers the hero video).
- [ ] Install ffmpeg: `brew install ffmpeg` (handles the video encoding).
- [ ] Install EngineerKit: `ck install engineerkit`
- [ ] Add Higgsfield to your Claude Code MCP config:
```json
{
  "mcpServers": {
    "higgsfield": {
      "type": "http",
      "url": "https://mcp.higgsfield.ai/mcp"
    }
  }
}
```
- [ ] Restart Claude Code.
- [ ] Run with flags: `/eng-site a launch page for my SaaS that ships AI agents --images --video`
  - `--images` adds AI stills.
  - `--video` adds the looping hero clip.
  - Without either flag it builds a working site for $0.
- [ ] Deploy the output folder to Vercel, Netlify, or Cloudflare Pages.

## The cost reality

The post claims ~$0.12 and 4 minutes per site on the full path. That excludes the Gemini and Higgsfield usage costs and assumes everything works first time. Budget more for both money and time on a real client build with revisions.

## Relevance to Orwell

Orwell already builds sites at scale with its own stack and design system, so EngineerKit is a shortcut, not a missing capability. The genuinely useful piece is the **Higgsfield MCP for AI hero video**, which ties to the creative-tools research ([[ComfyUI]], [[Meshy]]) and the existing Higgsfield entry in the GitHub Library. If a cinematic hero video would lift a portfolio or comparison site, the Higgsfield MCP is the reusable part worth lifting, independent of EngineerKit.
