---
title: Intelligence Feed Sources
tags: [intelligence, feeds, sources, daily-report]
updated: 2026-06-28
---

# Intelligence Feed Sources

Canonical source list for all daily and weekly intelligence briefs. Two routines run against this:
- **Daily routine** — covers all five daily categories, fires every day
- **Weekly routine** — Niche Industry only, fires every Monday

Sources are embedded directly in the routine prompts. This file is the reference master. Back to [[CLAUDE]].

---

## Category 1: Tech & AI
**Folder:** `Intelligence Reports/Tech/YYYY Week WW/Tech YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | TechCrunch AI | https://techcrunch.com/category/artificial-intelligence/feed/ | Fast on launches and funding |
| T1 | SiliconANGLE AI | https://siliconangle.com/category/ai/feed | Model releases, enterprise AI, often early |
| T1 | arXiv cs.AI | http://export.arxiv.org/rss/cs.AI | Primary research |
| T1 | arXiv cs.MA | http://export.arxiv.org/rss/cs.MA | Multi-agent systems — agentic workflow watch |
| T1 | LangChain Blog | https://blog.langchain.dev/rss/ | Agentic workflow watch: LangGraph, orchestration |
| T2 | Artificial Analysis | https://artificialanalysis.ai/articles | Model benchmarks and Intelligence Index |
| T2 | Anthropic News | https://www.anthropic.com/news | First-party model and product announcements |
| T2 | OpenAI News | https://openai.com/news/ | First-party model and product announcements |
| T2 | Latent Space | https://www.latent.space/ | Agentic engineering practice |
| T2 | Interconnects | https://www.interconnects.ai/ | Independent LLM research analysis |
| T2 | GitHub Trending | https://github.com/trending | New agent frameworks gaining stars |

---

## Category 2: UAE Market
**Folder:** `Intelligence Reports/UAE/YYYY Week WW/UAE YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | Arabian Business | https://www.arabianbusiness.com/rss | Best English-language UAE daily |
| T1 | The National Business | https://www.thenationalnews.com/business/rss | UAE property and financial news, CBUAE |
| T1 | Zawya | https://www.zawya.com/en/rss | Financial data, company news, regional markets |
| T2 | Property Finder Insights | https://www.propertyfinder.ae/blog | Dubai transaction data, price trends |
| T2 | Bayut Market Reports | https://www.bayut.com/blog/category/market-reports | Dubai rental and sales data by area |
| T3 | CBUAE | https://www.centralbank.ae/en/news | Rate decisions, LTV regulation, banking circulars |
| T3 | DLD Open Data | https://www.dubailand.gov.ae/en/open-data | Dubai Land Department transaction data |

---

## Category 3: SEO & Search
**Folder:** `Intelligence Reports/SEO/YYYY Week WW/SEO YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | Search Engine Roundtable | https://www.seroundtable.com/feed | Best real-time algorithm tracking |
| T1 | Search Engine Land | https://searchengineland.com/feed | Algorithm updates, SEO strategy |
| T1 | Semrush Sensor | https://www.semrush.com/sensor/ | SERP volatility score — spikes = algorithm activity |
| T2 | Google Search Central | https://developers.google.com/search/blog/rss.xml | Official crawling, indexing, ranking announcements |
| T2 | Ahrefs Blog | https://ahrefs.com/blog/rss/ | Programmatic SEO and content strategy |
| T2 | Marie Haynes | https://www.mariehaynes.com/blog/feed/ | Best independent E-E-A-T and HCU analysis |
| T3 | Semrush Blog (GEO) | https://www.semrush.com/blog/feed/ | AI Overviews, GEO, LLM citation signals |

---

## Category 4: Markets & Macro
**Folder:** `Intelligence Reports/Markets/YYYY Week WW/Markets YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | Yahoo Finance Tech | https://finance.yahoo.com/rss/topstories | Market reaction, earnings, stock moves |
| T1 | Bloomberg Technology | https://bloomberg.com/feeds/technology.rss | Funding, M&A, earnings, macro |
| T1 | Futunn News | https://news.futunn.com | Chinese AI stock angle |
| T2 | CNBC Tech | https://cnbc.com/id/19854910/device/rss/rss.html | Earnings, analyst calls |
| T2 | Crunchbase News | https://news.crunchbase.com/feed/ | AI funding rounds and valuations |
| T3 | Federal Reserve | https://www.federalreserve.gov/feeds/press_all.xml | Rate decisions and statements |

---

## Category 5: Gaming
**Folder:** `Intelligence Reports/Gaming/YYYY Week WW/Gaming YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | PC Gamer | https://www.pcgamer.com/rss/ | Releases, open-world and survival coverage |
| T1 | IGN | https://feeds.ign.com/ign/games-all | Broad industry news and releases |
| T2 | Rock Paper Shotgun | https://www.rockpapershotgun.com/feed | PC focus, survival and base-building |
| T2 | CFX / FiveM Forum | https://forum.cfx.re | FiveM/QBox updates — NORTHLANDS tie-in |
| T2 | r/FiveM | web search: r/FiveM latest this week | FiveM community news |
| T2 | Rockstar Newswire | https://www.rockstargames.com/newswire | GTA/GTA VI news affecting FiveM ecosystem |
| T3 | GamesIndustry.biz | https://www.gamesindustry.biz/feed | Industry business side, sales data |

---

## Category 6: Niche Industry (weekly, Mondays)
**Folder:** `Intelligence Reports/Niche/YYYY Week WW/Niche YYYY-MM-DD.md`

| Tier | Source | URL | Notes |
|---|---|---|---|
| T2 | IPATA | https://ipata.org/news | Pet transport association trade news |
| T2 | NAFD | https://nafd.org.uk/news/ | Funeral directors, repatriation news |
| T2 | SIA | https://www.sia.homeoffice.gov.uk/home/news/ | Close protection licensing and regulation |
| T2 | Coach & Bus Week | https://www.coachandbusweek.com/rss | Bus hire industry news |
| T2 | PCT Online | https://www.pctonline.com/rss | US pest management, regulatory updates |

---

## Category 7: Alternative News (daily)
**Folder:** `Intelligence Reports/Alternative News/YYYY Week WW/Alternative News YYYY-MM-DD.md`

Independent/investigative outlets on state and corporate accountability. Investigations, analysis and documents-based pieces only — no wire copy, podcasts, video-only posts, or link round-ups. Source health tracked in `Intelligence Reports/Alternative News/_Source Health.md`.

| Tier | Source | URL | Notes |
|---|---|---|---|
| T1 | The Intercept | https://theintercept.com/ | Strongest source in the register |
| T1 | ProPublica | https://www.propublica.org/ | Republishing licence, paraphrase anyway |
| T1 | Declassified UK | https://www.declassifieduk.org/ | UK military, MI6, Foreign Office. Blocked (403) on all paths as of 18 July 2026 — under watch |
| T1 | Drop Site News | https://www.dropsitenews.com/archive | Substack, JS-gated archive — discover via web search, fetch /p/ article pages directly |
| T2 | The Dissenter | https://thedissenter.org/ | Press freedom, whistleblowers, Espionage Act |
| T2 | Responsible Statecraft | https://responsiblestatecraft.org/ | Quincy Institute, foreign policy/military-industrial |
| T2 | openDemocracy | https://www.opendemocracy.net/ | Homepage only, tag pages sort oddly |
| T2 | Byline Times | https://bylinetimes.com/columns/special-investigation/ | Much of the paper is print-only |
| T2 | OCCRP | https://www.occrp.org/en/ | Verified 18 July 2026, strong daily cadence |
| T2 | Bellingcat | https://www.bellingcat.com/ | Verified 18 July 2026 |
| T2 | Investigate Europe | https://www.investigate-europe.eu/ | Verified 18 July 2026, EU cross-border |
| T2 | The Markup | https://www.themarkup.org/ | Verified 18 July 2026, tech/data accountability |
| T3 | Type Investigations | https://www.typeinvestigations.org/ | Verified 18 July 2026, slow cadence |
| T3 | Source Material | https://www.source-material.org/ | Verified 18 July 2026, slow cadence |
| T3 | Disclose | https://disclose.ngo/en | Verified 18 July 2026 |
| T3 | Lighthouse Reports | https://www.lighthousereports.com/ | Verified 18 July 2026, irregular/long-form |
| T3 | The Ferret | https://theferret.scot/ | Verified 18 July 2026, Scotland-specific |
| T3 | Correctiv | https://correctiv.org/en | Verified 18 July 2026, thin English output |
| T3 | Michael West Media | https://www.michaelwest.com.au/ | Verified 18 July 2026, AU-specific, filter opinion vs investigation |
