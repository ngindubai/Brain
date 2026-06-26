---
title: Intelligence Feed Sources
tags: [intelligence, feeds, sources, daily-report]
updated: 2026-06-26
---

# Intelligence Feed Sources

The canonical source list for the daily intelligence report. When running [[Daily Report Template]], fetch the top 5 stories from every Tier 1 and Tier 2 source. Tier 3 and 4 are reference-only; do not include them in the daily feed loop.

Back to [[CLAUDE]].

## Tier 1 - Daily feed (high signal, fast)

| # | Source | What it covers | URL / feed |
|---|---|---|---|
| 1 | Artificial Analysis | Model benchmarks, Intelligence Index rankings, launch analysis. Single best source for tracking where models rank | https://artificialanalysis.ai/articles |
| 2 | TechCrunch AI | Broad AI news, fast on launches and funding | https://techcrunch.com/category/artificial-intelligence/ / RSS: https://techcrunch.com/feed/ |
| 3 | arXiv cs.AI | Primary research papers. Where things appear before the news writes about them | http://export.arxiv.org/rss/cs.AI |
| 4 | arXiv cs.CL | Computational linguistics and LLM papers | http://export.arxiv.org/rss/cs.CL |
| 5 | arXiv cs.LG | Machine learning papers | http://export.arxiv.org/rss/cs.LG |
| 6 | SiliconANGLE AI | Model releases and enterprise AI, often early. Had Kimi K2.6 day one | https://siliconangle.com/category/ai/ / RSS: https://siliconangle.com/category/ai/feed |
| 7 | Stanford HAI | Authoritative big-picture state-of-play. Poll weekly, not daily | https://hai.stanford.edu / RSS: https://hai.stanford.edu/rss.xml |
| 8 | Dataconomy | AI market and model coverage | https://dataconomy.com |
| 9 | TechTimes | Tech/AI news, strong on geopolitics and market-reaction angle | https://www.techtimes.com |

## Tier 2 - Vendor and primary sources (authoritative but biased toward own announcements)

| # | Source | What it covers | URL |
|---|---|---|---|
| 10 | OpenAI Blog | OpenAI's own releases and research. Authoritative for OpenAI | https://openai.com/news/ |
| 11 | Futunn News | Markets-led coverage, strong on Chinese AI company and stock angle (Zhipu, DeepSeek funding) | https://news.futunn.com |
| 12 | Yahoo Finance (AI) | Market reaction stories. Good for the money side, noisy otherwise | https://finance.yahoo.com |

## Tier 3 - Specific facts, weaker as feeds

| # | Source | Notes |
|---|---|---|
| 13 | CodingFleet | Model-vs-model coding comparisons |
| 14 | MindStudio | Builder-focused model comparison blog |
| 15 | LushBinary | Open-weight model selection write-ups |
| 16 | InnFactory | Consulting blog, model profiles |
| 17 | KuCoin | Crypto exchange news. Carried one OpenRouter stat but not a quality AI source. Do not poll |

## Tier 4 - Reference only, do not include in feed

| # | Source | Notes |
|---|---|---|
| 18 | Wikipedia | Background reference (DeepSeek, Llama pages). Useful for lookups only |
| 19 | Oracle Docs | Cloud docs. Reference only |
| 20 | Blog aggregators | Small blog posts for individual fact confirmation only |

## Recommended additions (not yet in the feed, higher signal than several Tier 3/4 sources)

These did not surface in the initial research set but are better for ongoing monitoring:

- **The Information** - paid, but best lab-insider sourcing
- **Interconnects (Nathan Lambert)** - Substack, best independent LLM research analysis
- **Epoch AI** - training compute and scaling trends data
- **Hugging Face blog / trending** - open-weight model releases, sometimes before arXiv
- **LM Arena / LMSYS** - live model rankings by human preference
- **Anthropic news** - https://www.anthropic.com/news
- **DeepMind** - https://deepmind.google
- **Meta AI Blog** - https://ai.meta.com/blog
