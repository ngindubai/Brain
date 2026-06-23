---
title: Agent skills ecosystem (skills.sh)
area: research
tags: [research, skills, agentskills, agent-org, orwell-corp, marketing]
status: exploring
updated: 2026-06-23
related:
  - "[[areas/agent-org/agent-org]]"
  - "[[areas/products/products]]"
  - "[[areas/comparison-network/comparison-network]]"
  - "[[areas/ventures/ventures]]"
  - "[[research/hermes-agent-personal-ai-os]]"
  - "[[reference/orwell-corp-stack-decisions]]"
  - "[[projects/hermes-compare-reporting/hermes-compare-reporting]]"
  - "[[projects/marketing-department/marketing-department]]"
source: https://www.skills.sh
---

# Agent skills ecosystem (skills.sh)

## The idea in one line

skills.sh is Vercel's open directory of installable agent skills, and Hermes Agent (what we run) is a supported runtime, so we can install maintained worker and process skills into the agent org with one command and pin each to a version.

## Why it might matter

The agent org already carries two skill libraries as frozen copies inside the Orwell-Corp repo. Those go stale and nobody maintains them. skills.sh installs maintained SKILL.md knowledge with `npx skills add <owner>/<repo>`, and it carries skills we do not yet use, two of which (ai-seo, schema-markup) are exactly the depth the compare-site reports need. Where this lands in the build is in [[reference/orwell-corp-stack-decisions]].

## Key takeaways

- **Install path.** `npx skills add <owner>/<repo>` drops SKILL.md files in; Hermes reads them across sessions. Nous Research is a listed runtime.
- **Skills are knowledge, not powers.** What the company may do is set by the Hermes tool allow and deny list, so a skill cannot make it publish, send or spend. Recommendation-only holds.
- **The marketing pack we already vendor is here, maintained** (`coreyhaines31/marketingskills`), with additions the current map lacks: `ai-seo`, `schema-markup`, `competitor-alternatives`, `pricing-strategy`.
- **Process skills upgrade how the org runs and how we build** (`obra/superpowers`): verification-before-completion, subagent-driven-development, dispatching-parallel-agents, writing and executing plans.
- **The autonomous loop** (the "ralph" pattern) is the model for the always-on run and for the future blog builder.
- **Audit posture.** Install only audited or official skills, pin each to a commit, read each SKILL.md first.
- **Curator control.** Hermes can write its own skills; set it to opt-in with a review gate for client work.

## Audit findings (read against the live files, 23 June)

| Skill | Verdict |
|---|---|
| `ai-seo` (coreyhaines31) | Install. Current, strong, knowledge only. Exact fit for report depth. |
| `schema-markup` (coreyhaines31) | Install. Rich results and AI search. |
| `verification-before-completion` (obra) | Install. Evidence before any "done". |
| `webapp-testing` (anthropics) | Install. Official Playwright toolkit, used at go-live. |
| `openclaw-secure-linux-cloud` (xixu-me) | Do not install as written. Safe content but built for OpenClaw, not Hermes. Take its host-hardening principles only. |
| Sentry monitoring | Review at source. Partner skill, not a public repo. |

## Worker to skill mapping

CMO: marketing-psychology, marketing-ideas. Market Intelligence: competitor-alternatives. SEO Strategy: seo-audit. Technical SEO: seo-audit, schema-markup. Content Strategy: content-strategy, programmatic-seo. Content Writer: copywriting, copy-editing. Brand: brandkit, extract-design-system. SEO Verification: verification-before-completion. Internal Linking: seo-audit. Programmatic SEO: programmatic-seo. LLM Search: ai-seo. GEO and Citation: ai-seo, schema-markup. CRO: page-cro, popup-cro, paywall-upgrade-cro. Analytics and Attribution: analytics-tracking. Opportunity: marketing-ideas.

For the three compare sites the standout additions are competitor-alternatives, pricing-strategy, schema-markup and ai-seo, because they target comparison tables, rate framing, rich results and AI answers.

## Install manifest

```
npx skills add coreyhaines31/marketingskills
npx skills add obra/superpowers --skill verification-before-completion
npx skills add obra/superpowers --skill subagent-driven-development
npx skills add obra/superpowers --skill dispatching-parallel-agents
npx skills add obra/superpowers --skill writing-plans
npx skills add obra/superpowers --skill executing-plans
npx skills add anthropics/skills --skill webapp-testing
npx skills add vercel-labs/next-skills --skill next-best-practices
# monitoring: install Sentry from its own official source, reviewed first
# security: do not install the openclaw skill; fold its principles into go-live
```

## Open questions

- Pin the whole marketing pack, or only the skills each worker uses?
- Does the ralph loop pattern replace or sit beside the current delegation routine?
- Which monitoring: the Sentry partner skill, or wire Sentry by hand from its own docs?

## What would make this a project

It already feeds [[reference/orwell-corp-stack-decisions]] as steps S1 and S2 of the build-next plan. Promote fully if we standardise one skills manifest across every business, not just the compare slice.

## Source

- Directory: https://www.skills.sh ; Nous runtime page: https://www.skills.sh/agent/nous-research
- Repos filed in [[github-database/skill-libraries]] and [[github-database/automation-tools]].
- Captured 2026-06-23. Skill files read directly on GitHub for the audit.
