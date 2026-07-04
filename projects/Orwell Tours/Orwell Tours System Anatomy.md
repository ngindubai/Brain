---
title: Orwell Tours System Anatomy
tags: [project, orwell-tours, architecture, reference, 3d]
status: active
updated: 2026-07-05
project: "[[Orwell Tours]]"
---

# Orwell Tours System Anatomy

Every part of [[Orwell Tours]] in plain words: what it is, where its code lives, which computer runs it, and how it plugs into its neighbours. Read this first for a full mental model. Companion notes: [[Orwell Tours Build Plan]], [[Orwell Tours Setup Prompts]]. All third-party repos are catalogued in [[3D Reconstruction]].

## First, the honest picture

The starting link, github.com/playcanvas, is the PlayCanvas organisation page: a games technology company that open-sourced its tools. Nothing in it is a real estate platform. We take three of their tools, add three tools from other workshops, build two repos of our own, and rent four services. That is the entire machine.

Borrowed tools (free, MIT/Apache/BSD): [playcanvas/engine](https://github.com/playcanvas/engine), [playcanvas/supersplat](https://github.com/playcanvas/supersplat), [playcanvas/splat-transform](https://github.com/playcanvas/splat-transform), [@playcanvas/react](https://github.com/playcanvas/react), plus ffmpeg, COLMAP and nerfstudio for the video-to-3D maths in Phase 2.

Our own repos (github.com/ngindubai): `orwell-tours-api` (brain plus tour pages) and `orwell-tours-app` (the phone app).

Rented services: Render (hosting), Neon (database), Cloudflare R2 (storage), KIRI then RunPod (the 3D maths as a service).

## One video's journey

1. Born on the agent's phone in the app as a ~1.5 GB 4K video. The app asks the API for a one-time upload address and pushes the file straight into Cloudflare R2. The big file never touches our web server.
2. Registered and queued: the API writes a row in Neon and drops a job ticket into the queue (Render Key Value).
3. Video becomes a 3D scene on a GPU worker (KIRI in Phase 0, RunPod in Phase 2): pick sharp frames, work out where the camera stood, train a Gaussian splat. Out comes a PLY file, ~50 to 200 MB.
4. Shrunk for phones by splat-transform: PLY to SOG, ~5 to 15 MB, plus a cover image. Both go back to R2, the row flips to ready, the API fires the push notification.
5. Walked through in WhatsApp: the agent shares the link, the buyer taps it, Render serves the tour page, the PlayCanvas engine streams the SOG from R2 and draws the flat at 60 fps in the browser. No app, no account.

In one sentence: a big video goes into storage, a rented GPU turns it into a tiny 3D file, and a web page anyone can open draws that file as a walkthrough.

## The parts

### C1 PlayCanvas Engine (borrowed)

Repo: https://github.com/playcanvas/engine. Licence MIT. The display engine that draws a 3D scene on screen 60 times a second and responds to touch. Has built-in Gaussian splat rendering and can stream compressed SOG files. Runs inside the buyer's own browser, so zero hosting cost per viewer. In: SOG from R2. Out: interactive walkthrough. Plugs into the tour page (C8) and R2 (C10).

### C2 @playcanvas/react (borrowed)

Repo: https://github.com/playcanvas/react. Licence MIT. The adaptor that lets our React tour pages drop in a splat viewer in one line, with ready-made camera controls we tune for one-thumb walkthroughs. Runs in the buyer's browser inside the tour page. Plugs into the engine (C1) and the API repo (C8).

### C3 SuperSplat (borrowed, desktop tool)

Repo: https://github.com/playcanvas/supersplat. Licence MIT. A free browser editor (superspl.at) for tidying a raw scan by hand: crop, delete speckles, set the opening camera. In Phase 0 you use it personally, which teaches you good versus bad captures. From Phase 2 the pipeline does routine cleanup automatically and SuperSplat becomes the rescue tool. Runs on your Windows desktop in Chrome. In: raw PLY. Out: cleaned PLY.

### C4 splat-transform (borrowed)

Repo: https://github.com/playcanvas/splat-transform. Licence MIT. The command-line compressor that converts bulky PLY (50 to 200 MB) into SOG (5 to 15 MB) so phones can load it over 4G. Runs automatically as the final pipeline step inside the worker. In: cleaned PLY. Out: SOG plus cover image. Plugs into the worker (C7) and R2 (C10).

### C5 The 3D maths: ffmpeg plus COLMAP plus nerfstudio (borrowed)

Repos: https://github.com/FFmpeg/FFmpeg (LGPL build), https://github.com/colmap/colmap (BSD), https://github.com/nerfstudio-project/nerfstudio (Apache 2.0) using https://github.com/nerfstudio-project/gsplat (Apache 2.0). ffmpeg slices the video into frames and bins blurry ones; COLMAP works out where the camera stood for each frame; nerfstudio trains the Gaussian splat. Not run at all in Phases 0 and 1 (KIRI does the equivalent). In Phase 2 these three are boxed into one Docker image on RunPod, at pennies per tour. In: video from R2. Out: raw PLY. Plugs into the worker (C7) and splat-transform (C4).

### C6 KIRI Engine API (rented, Phases 0 to 1)

Service: https://www.kiriengine.app (no repo). We post a video, their GPUs do everything C5 describes, a finished scan comes back, pay per scan. Removes the hardest engineering from the first two phases so the app, sharing and business get proven fast. Phase 2 swaps this card for C5 and cost drops from dollars to cents; the swap is invisible to agents. Runs on KIRI's servers; we hold an API key. Plugs into the worker (C7).

### C7 The worker and queue (ours)

Lives inside `ngindubai/orwell-tours-api`. A small always-on programme (TypeScript, BullMQ) that watches the queue (Render Key Value), picks up one job at a time, and walks it through: fetch video, send to KIRI or RunPod, wait, compress with splat-transform, save to R2, mark the Neon row ready, tell the API to ping the agent. The queue decouples the agent tapping upload from the GPU finishing half an hour later; a crash mid-job leaves the ticket to be picked up again. Runs on Render as a Background Worker. Plugs into the queue, KIRI (C6), RunPod (C5), R2 (C10), Neon (C9).

### C8 orwell-tours-api: the brain and shop window (ours)

Repo: github.com/ngindubai/orwell-tours-api. One repo, two faces. The API is the brain the app talks to (sign-ins, records, upload addresses, tour lists, queue, push). The tour pages are the shop window: the public `/t/<slug>` pages buyers open, with the viewer (C1 plus C2), agency branding, the Trakheesi line, the WhatsApp preview tags, and the Chat with the agent button. Claude Code pushes to GitHub, Render redeploys within minutes. Runs on Render as a Web Service (Next.js). Plugs into the app (C9a), Neon (C9), R2 (C10), the queue (C7), push services.

### C9a orwell-tours-app: the thing in the agent's hand (ours)

Repo: github.com/ngindubai/orwell-tours-app. The iOS and Android app, one Expo (React Native) codebase. Four jobs: guided capture, background upload to R2, the tour library with push, and the share sheet into WhatsApp. EAS compiles and signs both versions in the cloud (no Mac); binaries go to TestFlight and Play testing then the stores; small fixes ship over the air. Runs on agents' phones. Plugs into the API (C8), R2 (C10), the WhatsApp share sheet.

### C9 Neon Postgres: the ledger (rented)

Console: https://console.neon.tech (no repo). The filing cabinet of record: every agency, agent, tour, job and view count is a row. Already in the Orwell stack, free tier to start, independent of Render so hosting can change without moving data. Read and written by the API and worker only.

### C10 Cloudflare R2: the warehouse (rented)

Dashboard: https://dash.cloudflare.com (no repo). Stores everything heavy: videos, PLY scans, SOG files, cover images. The database holds the paperwork; R2 holds the goods, each row noting the shelf reference. Chosen over Amazon because R2 charges nothing for downloads, and every buyer view streams 5 to 15 MB. In: videos from the app, scans from workers. Out: SOG streams to every buyer. Plugs into the app (C9a), worker (C7), engine (C1).

Two PlayCanvas repos we deliberately do not use: [playcanvas/model-viewer](https://github.com/playcanvas/model-viewer) (a generic viewer, less flexible than building our page with C2) and [playcanvas/editor](https://github.com/playcanvas/editor) (their game studio, irrelevant here).

## The wiring

| From | To | Carrying | Over |
|---|---|---|---|
| App (C9a) | API (C8) | Sign-ins, tour details, upload address requests, library lists | HTTPS |
| App (C9a) | R2 (C10) | The raw video, in resumable chunks | One-time presigned upload address |
| API (C8) | Neon (C9) | Every record read and write | Database connection |
| API (C8) | Queue (C7) | New job tickets | Redis (Render Key Value) |
| Worker (C7) | KIRI (C6) / RunPod (C5) | Video out, PLY back | Their APIs, our keys |
| Worker (C7) | splat-transform (C4) | PLY in, SOG plus cover out | Runs it directly, same machine |
| Worker (C7) | R2 (C10) plus Neon (C9) | Files stored, row marked ready | Storage API plus database |
| API (C8) | Agent's phone | Tour ready ping | APNs / FCM push via Expo |
| Buyer's browser | API (C8) then R2 (C10) | Tour page, then SOG stream into engine (C1) | Plain web links |
| GitHub (ngindubai) | Render plus EAS | Every code change, deployed automatically | Push to main |

Safety property: heavy files always travel edge to edge (phone to R2, R2 to GPU, R2 to buyer) and never through the brain. The API only moves small text records, which is why a cheap Render instance serves an entire agency network.

## Plain words

- repo: a folder of code with full change history on GitHub. One repo, one tool or product.
- Gaussian splat: a 3D scene made of millions of tiny soft coloured blobs. Photoreal, fast on phones, buildable from ordinary video.
- PLY / SOG: two formats for the same scan. PLY is the heavyweight master (50 to 200 MB); SOG is the compressed delivery copy (5 to 15 MB) buyers stream.
- API: a waiter for programmes. The app asks in a fixed format, the server replies in a fixed format. An API key is the pass proving you may order.
- worker / queue: a queue is a waiting line of job tickets; a worker serves the line one at a time. How slow jobs run without anything waiting on them.
- presigned upload: a one-time single-file permission slip letting a phone put a file straight into storage without holding warehouse keys.
- GPU: a graphics processor, thousands of small calculators at once. Splat training is exactly that shape of maths, hence renting by the second.
- Docker image: a sealed box with a programme plus everything it needs, so it runs identically on any rented machine. How the Phase 2 factory ships to RunPod.
- WebGL: the browser's built-in 3D drawing, present in every modern phone browser including WhatsApp's, so buyers install nothing.
- OTA update: over the air; app fixes delivered straight to phones, skipping store review, for anything that is not native code.
- Open Graph tags: hidden labels (title, image) WhatsApp reads to draw the rich preview card when a link is shared.
