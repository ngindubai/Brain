---
title: Orwell Tours
tags: [project, product, orwell-tours, 3d, real-estate, mobile]
status: active
stage: Phase 0, proof of tour, pre-build
next_action: Run setup prompts P1 to P5, film one Dubai apartment, produce one live tour
updated: 2026-07-05
area: "[[Products]]"
---

# Orwell Tours

White-label, self-serve mobile app that turns an estate agent's phone video walkaround into an interactive 3D property tour, shared as a WhatsApp link. Sold to Dubai real estate agencies under the Orwell brand. Buyers never install anything; they open a web link.

Parent area: [[Products]]. Third-party code filed under [[3D Reconstruction]] in the [[GitHub Library]].

## The one goal

Ship an iOS and Android app that takes an agent from video walkaround to a shareable 3D tour link, self-serve, hosted on Render, with reconstruction starting on a hosted API and moving to our own GPU pipeline once proven.

## The documents

- [[Orwell Tours Build Plan]] is the full technical plan: phases, architecture, costs, licences. The standing brief for every Claude Code session on this project.
- [[Orwell Tours System Anatomy]] explains every component in plain words, with its GitHub repo, where it runs, and how it wires to the others. Read this first for understanding.
- [[Orwell Tours Setup Prompts]] holds the manual browser tasks (accounts, keys, hosting, app stores) and the master key ledger.
- These three notes are the canonical copy in the vault. The same content was also produced as rendered, idiot-proof HTML guides (visual versions with phone mockups and copy buttons); those files sit in the chat outputs and can be committed into a `Deliverables/` folder here on request.

## The stack in one line

Expo app writes video straight to Cloudflare R2, Render runs the API, job queue and public tour pages, a GPU worker (KIRI Engine in Phase 0, own RunPod pipeline in Phase 2) turns the video into a Gaussian splat, the PlayCanvas engine draws it in the buyer's browser, and the agent shares the link into WhatsApp. Records live in Neon Postgres.

## What we have learnt

- github.com/playcanvas is a toolbox, not a product. We use exactly three of its tools (engine, SuperSplat, splat-transform) plus the React connector, and build the rest ourselves. Full breakdown in [[Orwell Tours System Anatomy]].
- The differentiator is guided capture in the app (level line, room checklist, slow-down warnings), because reconstruction quality is decided at record time, not upload time.
- One app per store, re-themed per agency after sign-in. Apple rejects fleets of re-skinned clone apps unless each client holds its own developer account, so per-agency store listings are an enterprise upsell, never the default. White-labelling lives on the tour page and custom domain, which is all buyers ever see.
- Heavy files never pass through the API (phone to R2, R2 to GPU, R2 to buyer), which is why a cheap Render instance can serve a whole agency network.
- Licences in the serving and training path are all MIT, BSD or Apache 2.0. OpenSplat (AGPL) and the Inria reference implementation (non-commercial) are excluded on purpose.

## The plan

- [ ] Phase 0, proof of tour (week 1): film one Dubai apartment, run it through KIRI, clean in SuperSplat, publish one live tour page, share to WhatsApp. Go/no-go on visual quality here.
- [ ] Phase 1, self-serve MVP (weeks 2 to 5): API, Neon schema, R2 uploads, KIRI worker, viewer pages, Expo app with sign-in, capture, upload, push, share. TestFlight and Play internal. First friendly agency.
- [ ] Phase 2, own the pipeline (weeks 6 to 10): RunPod Docker pipeline replaces KIRI, guided-capture overlay ships, failure-reason mapping. Per-tour cost drops from dollars to cents.
- [ ] Phase 3, white-label and launch (weeks 10 to 14): tenant theming in app and viewer, custom tour domains, admin invitations, view analytics, Trakheesi enforcement, store production release.

## Progress

Done:

- Full technical blueprint researched and written (mobile version).
- Three deliverable notes produced and filed here; rendered HTML versions produced and held in outputs.

Frontier:

- Setup prompts not yet run. No accounts created. No code written.

## Next actions

1. Read [[Orwell Tours System Anatomy]] end to end for a full mental model.
2. Run setup prompts P1 to P4 from [[Orwell Tours Setup Prompts]] (Neon, R2, Render, KIRI). Start P5 (Apple) early; its D-U-N-S wait is the long pole.
3. Film one real Dubai apartment and hand it to a Claude Code session with [[Orwell Tours Build Plan]] as the brief.

## Open questions

- KIRI Engine per-scan price and whether Gaussian splat PLY export is included on the entry tier (resolved at prompt P4).
- Whether to register the Dubai entity's D-U-N-S now to unblock both Apple and Google store accounts.
- Short share domain choice (orwl.ae vs tours.orwell.ae).
