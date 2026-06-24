---
title: File Inbox
tags: [skill]
trigger: "file the inbox", "sort this", or any raw dump in chat
updated: 2026-06-24
---

# Skill: File Inbox

Run this when I dump information at you in chat, or when the Inbox has loose notes.

## Steps

1. Read the dump, or every file in `Inbox/`.
2. For each item, decide the destination:
   - a new idea to bounce around to `Research/` as its own note, not a project yet
   - ongoing domain to the right `Areas/` folder
   - time-boxed work with one goal to a folder in `Projects/`
   - durable knowledge to `Reference/`
   - an external git repo to `GitHub Library/`
   - cannot place confidently: leave in `Inbox/` with a `#needs-filing` tag and flag it
3. Name the file in Title Case so the graph stays readable.
4. Add frontmatter: title, tags, updated.
5. Add `[[wikilinks]]` (short basename form) to the relevant area or index and any related notes.
6. Check for duplicates. If it extends an existing note, append rather than create.
7. Write a one-line entry into today's daily note in `Dashboard/Daily/`.
8. Commit.

## Rules

- Do not ask me which folder. Decide. Only ask if genuinely ambiguous.
- A loose idea is research, not a project.
- Apply house style. Keep it text-only.
