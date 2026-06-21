# brain

My second brain. A text-only Obsidian vault that lives as a private GitHub repo. Claude files into it; I read and capture from it on mobile.

## How it works

- **Capture:** I mostly tell Claude things in chat. Claude files them into this repo via GitHub, named and linked. I can also drop raw notes into `_inbox/` myself.
- **Sync:** the GitSync app on Android pulls this repo to my phone. Obsidian opens the synced folder.
- **Retrieve:** ask Claude, or browse the graph in Obsidian.
- **Autopilot:** a daily routine files the inbox and writes a short summary into `00-dashboard/daily/`.

## Structure

- `_inbox/` raw capture, unsorted
- `00-dashboard/` the map, plus daily notes and summaries
- `areas/` ongoing domains
- `projects/` time-boxed work, one goal each
- `reference/` durable knowledge and house style
- `skills/` reusable workflows Claude runs on command

## Operating context

`CLAUDE.md` at the root is the instruction set Claude loads every session.
