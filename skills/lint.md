---
title: Skill - lint
tags: [skill]
trigger: "lint the brain"
updated: 2026-06-22
---

# Skill: lint

Health check on the vault. Run every couple of weeks or on request.

## Steps

1. Find orphan notes (no links in or out) and propose links.
2. Find broken `[[wikilinks]]`.
3. Find notes with no frontmatter or missing fields.
4. Find stale notes (no update in 30 or more days) and flag them.
5. Find duplicate or near-duplicate notes and propose merges.
6. Clear leftover `#needs-filing` items in `_inbox/`.
7. Write findings to today's daily note and fix the safe ones.
