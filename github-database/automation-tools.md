---
title: Automation Tools
area: github-database
tags: [github-database, automation, browser, scraping, pipelines]
updated: 2026-06-23
---

# Automation Tools

Browser automation, scraping, and pipeline glue. The tools that let agents act on the open web. Back to [[github-database/github-database]].

| Repo / Source | What it is | What we'd pull | Feeds | Status |
|---|---|---|---|---|
| [jo-inc/camofox-browser](https://github.com/jo-inc) | Stealth headless browser server with REST API. Bypasses Cloudflare, bot detection, anti-scraping. Puppeteer/Playwright drop-in. Used in production by askjo.ai | Reliable scraping/automation on a VPS where standard headless gets blocked | [[areas/seo-portfolio/seo-portfolio]], [[areas/ventures/ventures]] | shelf |
| Playwright MCP | Gives Claude control of a real browser. Pairs with Higgsfield for batch UGC/asset generation | Browser hands for any agent build needing real clicks | [[areas/products/products]] | evaluating |
| [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser) | CLI browser automation skill: navigate, click, fill forms, extract, screenshot. Fast and predictable | SERP pulls and AI-answer checks for the LLM Search and GEO workers | [[areas/agent-org/agent-org]] | evaluating |
| [browser-use/browser-use](https://github.com/browser-use/browser-use) | Browser automation with visual understanding, interacts by what it sees. Good when page structure is unknown | The crawler and SERP work when selectors are inconsistent | [[areas/agent-org/agent-org]] | evaluating |
| [scrapegraphai/just-scrape](https://github.com/scrapegraphai/just-scrape) | Scraping skill for structured extraction | Real crawl and competitor data once mock is removed (B24) | [[areas/agent-org/agent-org]] | evaluating |

Note: the energy-claims-scraper venture is a likely first home for camofox. The agent-browser, browser-use and just-scrape entries feed the real connector work in [[reference/orwell-corp-stack-decisions]].
