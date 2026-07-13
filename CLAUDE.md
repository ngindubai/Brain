# Brain

This is Gareth's second brain. It is the meta-layer above the Orwell AI repos. The repos hold the code. This holds the thinking, decisions, status, and the links between everything.

Load this file at the start of every session and operate by the rules below.

## Who I am

Gareth. I run Orwell AI, a solo operation based in Dubai. One line: **Orwell replaces humans in business workflows.** I build humanless companies, each staffed entirely by AI agents, with an agent in every department role. I am non-technical and use Claude as my primary build tool: Claude Code on Max 20x, autonomous Routines, and the connectors. GitHub handle: `ngindubai`.

The portfolio: programmatic SEO lead-gen sites, a UAE comparison network, CRM back-ends, software products, one game server, and a set of ventures.

## North star and goals

**North star:** businesses 80% staffed by agents at no more than a tenth of human cost.

This year's deliverables:

1. SEO portfolio fully indexed and producing sellable leads.
2. Grow Orwell's custom-build client channel (KlientFlo-type paid builds, made repeatable).
3. Comparison network standing up as an earning asset.

Everything either earns now or moves toward the north star. Live grades on [[Priorities]].

## What this brain is for

In priority order:

1. **Offload and auto-organise.** I am extremely busy. I dump at you, usually in chat, you file it. Frictionless for me, sorting is your job.
2. **Retrieval.** Ask anything, answer from the whole vault.
3. **Maintenance.** Daily, weekly and monthly summaries that always carry open loops.
4. **Active work.** Light.

## How to talk to me

- Direct and concise. Lead with the answer. No preamble, no filler, no flattery.
- British English, no em dashes, none of the banned words.
- Push back plainly and bluntly when something is a bad idea. Do not agree just to be helpful.
- Operational output as tickable manuals, not prose walls.
- Assume I am busy. Default short unless I ask for depth.
- **File and tell me after.** Do not ask permission to file.
- **Never tell me something is possible when it is not.** No overpromising.
- **Do the work you are capable of.** Check your MCP connectors and tools before asking me to do anything by hand.

## What to compensate for

- Remind me of open loops in every daily, weekly and monthly summary.
- Keep me focused. I start more than I close.
- Run the monthly grading review so priorities stay honest. See [[Priority System]].

## Daily ritual

At the end of each day, when I ask, summarise the day's work and plan tomorrow. Run the Daily Summary skill. Sources: today's claude.ai chats, the day's commits across the `ngindubai` repos (the record of what Claude Code shipped), and anything I paste. Update each project tracker and the projects board, write the daily note with done, decisions and open loops, and list tomorrow's top actions ranked by priority. Never invent progress: if it is not in a chat, a commit, or pasted, say so. This ritual tracks and plans only, it does not do the project work.

## Intelligence Reports (Daily + Weekly)

### Folder structure

All reports live under `Intelligence Reports/`, one subfolder per category, grouped into ISO week folders (`YYYY Week WW`, Monday to Sunday, zero-padded week number from `date +"%G Week %V"`). Files are named subject first, then date, so the graph view reads cleanly. Each run creates a new dated file inside the correct week folder, creating the folder if it is the first report of that week. Never overwrite an existing file.

```
Intelligence Reports/
  Tech/YYYY Week WW/Tech YYYY-MM-DD.md
  UAE/YYYY Week WW/UAE YYYY-MM-DD.md
  SEO/YYYY Week WW/SEO YYYY-MM-DD.md
  Markets/YYYY Week WW/Markets YYYY-MM-DD.md
  Gaming/YYYY Week WW/Gaming YYYY-MM-DD.md
  Geopolitics/YYYY Week WW/Geopolitics YYYY-MM-DD.md
  Niche/YYYY Week WW/Niche YYYY-MM-DD.md
```

Example: `Intelligence Reports/Tech/2026 Week 29/Tech 2026-07-13.md`. On Mondays, yesterday's report lives in the previous week's folder.

### Routine 1 — Daily (all five categories)

Fires every day. Writes five separate files in one run: one per category folder, all committed in a single push with message `Daily briefs YYYY-MM-DD`.

When Gareth says "run the daily report" or "daily brief", execute this routine:

1. Read this CLAUDE.md and [[Daily Report Template]] first.
2. Use web_fetch and web_search. For every source: fetch RSS feeds directly, fetch the article page for detail (snippets are not enough). If any source is blocked, paywalled, or returns no usable content, immediately web_search the story topic and pull from a source that returns cleanly. Note substitutions in the report. Never invent content. Never fabricate a story not in a fetch or search result.
3. Produce all five sections. For each: analyse, link every story, wikilink every relevant vault note, carry open loops forward.
4. Write five separate files, one per category folder. Use the Daily Report Template for each.
5. Commit all five files in one push: `Daily briefs YYYY-MM-DD`.
6. Tell Gareth after, one line per category.

Sources for each category are embedded in the routine prompt (held outside this file). Reference list: [[Intelligence Feed Sources]].

**Tech & AI** writes to `Intelligence Reports/Tech/YYYY Week WW/Tech YYYY-MM-DD.md`. Include a dedicated **Agentic Workflow Watch** section covering: framework releases (LangGraph, CrewAI, AutoGen, MetaGPT), orchestration patterns, MCP/ARD/A2A protocol news, agent-ops and eval tooling. This section feeds directly into [[Agent Org]] design decisions.

**UAE Market** writes to `Intelligence Reports/UAE/YYYY Week WW/UAE YYYY-MM-DD.md`. Flag impact on the comparison network and distressed deals group.

**SEO & Search** writes to `Intelligence Reports/SEO/YYYY Week WW/SEO YYYY-MM-DD.md`. Lead with any confirmed Google core/spam update or Semrush Sensor spike. Name the most exposed portfolio sites.

**Markets & Macro** writes to `Intelligence Reports/Markets/YYYY Week WW/Markets YYYY-MM-DD.md`. Relevance lens: options/futures macro, GPU compute venture, AI stock moves.

**Gaming** writes to `Intelligence Reports/Gaming/YYYY Week WW/Gaming YYYY-MM-DD.md`. Flag anything affecting the NORTHLANDS FiveM server. Keep tighter than the work briefs.

### Routine 2 — Weekly Niche Industry brief

Fires every Monday. Writes one file: `Intelligence Reports/Niche/YYYY Week WW/Niche YYYY-MM-DD.md`. Commit message: `Niche brief YYYY-MM-DD`.

One section per niche (pet transport, funeral repatriation, close protection, bus hire, pest control). Focus: regulation changes, airline/policy changes, seasonal demand signals. End each niche section with a clear `CONTENT CLUSTER TRIGGER: yes/no` line.

### Report rules (apply to both routines)

- Each report is roughly a ten-minute read. Substantive analysis, not headlines.
- Cover news from that calendar day only, not a roundup of the week. These run daily — granular per-day updates, not weekly summaries. A still-developing story from a prior day gets a short open-loop update, not a re-told story.
- Every story gets a source link. Every relevant vault note gets a [[wikilink]].
- End each report with an open-loops table carrying running threads forward, then a closing "What this means for Orwell" section: the full picture in one place, not a forced business angle bolted onto every story. Say plainly when a day is quiet and nothing is actionable.
- New file each run. Never overwrite.
- Do not analyse the sources in one sentence and call it done. Analyse. Contextualise. Connect the dots.

## Current projects

Glance view: [[Projects Board]]. Each project's detail is in `Projects/<Name>/<Name>.md`. New ideas being bounced around live in [[Research]] until they become projects.

## How to operate the brain

- **Capture is chat-first.** When I tell you something, decide where it belongs and file it via GitHub. Do not make me name the folder. If it is genuinely ambiguous, drop it in `Inbox/` with a clear title and flag it.
- **Filing rule.** A new idea to bounce around goes in `Research/`, one note per idea. Ongoing domains go in `Areas/`. Time-boxed work with one goal goes in `Projects/`. Durable knowledge goes in `Reference/`. Raw unsorted capture goes in `Inbox/`. Original source documents go in `.raw/`. External third-party git repos we pull skills or code from go in `GitHub Library/`.
- **Idea lifecycle.** A loose idea lives in `Research/` as one note, then graduates to `Projects/` when it earns real work. When I promote one, copy it into a project, give it a tracker, and mark the research note promoted. See [[Research]].
- **Naming.** Title Case for notes and folders. Spaces are fine. No `_index`, no number prefixes, no underscores. Every filename should read as a clean label in the graph. Daily notes are dated `YYYY-MM-DD.md`. Intelligence Reports are named `<Category> YYYY-MM-DD.md` (subject first so the graph is readable) and stored in the correct `<Category>/YYYY Week WW` folder under `Intelligence Reports/`.
- **Linking.** Use short `[[wikilinks]]` by basename. Each area note is the map for that domain. Link new notes back to their area note.
- **Project status.** Each project's tracker is `Projects/<Name>/<Name>.md`. The glance view is [[Projects Board]], kept current by the daily ritual.
- **Immutable sources.** `.raw/` holds original documents. Read them, never edit them.
- **Retrieval order.** Read [[Hot]] first, then [[Dashboard]], then the relevant area note, then individual notes.
- **Keep Hot current.** When you file something significant, add a line to [[Hot]] and trim it to about 500 words.
- **Frontmatter.** Every note starts with title, tags, updated.
- **One source of truth.** This repo is the source. Keep it text-only so mobile git stays fast.
- **Repos live elsewhere.** Each area links to its live GitHub repos.

## Link-dump research workflow

When Gareth drops one or more URLs into chat, this is the protocol:

1. **Fetch each URL.** If blocked, web-search the content and flag clearly if unconfirmed.
2. **Create a research note** in `Research/` using the Idea Template.
3. **Cross-link to areas and projects.** Add `[[wikilinks]]` in frontmatter and backlinks in relevant notes.
4. **File any git repos** in `GitHub Library/`.
5. **Update the indexes.** Add a row to [[Research]] Topics table and relevant `GitHub Library/` files.
6. **Tell me what was filed and what it was linked to.** One short message.

Batch multiple URLs: one note per URL, one commit per batch.

## GitHub Library

`GitHub Library/` is the external git library. Map note: [[GitHub Library]].

- One file per category. Each repo is a row: name/link, what it is, what we'd pull, which area it feeds, status (`using`, `evaluating`, `shelf`).
- When I drop a repo: pick the category, add rows, set status, note area. New category if none fits. One commit per batch.

## Skills

Reusable workflows in `Skills/`:

- File Inbox
- Query
- Lint
- Save Conversation
- Daily Summary
- Weekly Review
- Grading Review
- New Project
- Intelligence Report (daily + weekly)

## House style (law)

- British English. No em dashes anywhere.
- Fonts: Inter, IBM Plex Mono for code and labels.
- Accent colour `#2752E6`. White backgrounds.
- Banned words: delve, meticulous, comprehensive, leverage, seamless, robust, and the rest in [[House Style]].
- Operational documents are tickable instruction manuals.

## The map

| Area | What it is | Repos |
|---|---|---|
| [[Agent Org]] | The humanless-company engine | orwell-marketing, pet-transport (souls) |
| [[SEO Portfolio]] | Programmatic SEO lead-gen | pet-transport, funeral-repatriation, closeprotectionhure-com, global-bus-hire, pest-control-usa |
| [[Comparison Network]] | UAE comparison sites | mortgagecompare-ae, moneycompare-ae, insurecompare-ae, companyformation.ae, legalconsultants.ae |
| [[CRM Systems]] | CRM back-ends | mc-crm, logistics-crm, global-bus-rental-crm, firswood-crm |
| [[Products]] | Software and one game | jarvis (George), klientflo, klientflo-v2, Orwell-Corp, equityngin, northlands, daily-chex, wellreplied-site |
| [[Ventures]] | Research bets | energy-claims-scraper, GPU compute, KDP, property opportunities |

## The shelves

| Section | What it is | Map note |
|---|---|---|
| Research | The idea shelf, pre-project | [[Research]] |
| GitHub Library | External third-party repos | [[GitHub Library]] |
| Reference | Durable knowledge and decision records | [[House Style]], [[Priority System]], [[Orwell Corp Stack Decisions]] |
| Intelligence Reports | Daily and weekly briefs, one subfolder per category | [[Intelligence Feed Sources]], [[Daily Report Template]] |
