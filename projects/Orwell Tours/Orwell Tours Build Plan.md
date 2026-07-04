---
title: Orwell Tours Build Plan
tags: [project, orwell-tours, build-plan, architecture]
status: active
updated: 2026-07-05
project: "[[Orwell Tours]]"
---

# Orwell Tours Build Plan

Version 2.0, mobile. The standing brief for every Claude Code session on [[Orwell Tours]]. Companion notes: [[Orwell Tours System Anatomy]], [[Orwell Tours Setup Prompts]].

Product: iOS and Android app for real estate agents. Record a video walkaround on a phone, receive an interactive 3D tour, share it on WhatsApp. House style per [[House Style]]: British English, no em dashes.

## 1. What changed from the web blueprint

The first blueprint treated this as a browser dashboard agencies would integrate. This version replaces the agent surface with native mobile apps. Everything below the surface carries over.

| Area | Web blueprint | Mobile blueprint |
|---|---|---|
| Agent surface | Next.js dashboard | iOS and Android app (Expo) |
| Capture | Upload a file | Guided in-app capture with live coaching |
| Job status | Poll dashboard | Push notification when ready |
| Sharing | Copy link | Native share sheet into WhatsApp, plus QR |
| Buyer surface | Web tour link | Unchanged: web tour link, no install |
| White-label | Custom domain per agency | One app re-themed per agency, custom tour domain per agency |

Design rule: the app is for agents, the web is for buyers. A buyer opening a WhatsApp link sees the tour instantly with zero installs.

## 2. Product definition

1. Agent opens the app, taps New Tour, enters property details (title, community, price, Trakheesi permit number).
2. The app guides a video walkaround: coaching overlay, room checklist, quality guardrails.
3. Video uploads in the background to object storage. The agent can close the app.
4. A GPU pipeline turns the video into a 3D Gaussian splat scene.
5. Push notification when ready. Agent previews the tour in the app.
6. Agent taps Share; the sheet opens WhatsApp with a pre-filled message and the tour link, which unfurls with a cover image and title.
7. The buyer taps the link and walks through the property in their browser.

Out of scope for v1: buyer accounts, lead capture forms, floor plans, measurements, VR, offline mode.

## 3. Architecture

Agent app (Expo, iOS and Android): capture, upload, library, push, preview, share.
API and viewer (Render, one Next.js service): `/api/*` for the app, `/t/[slug]` for buyer tour pages with the PlayCanvas viewer and Open Graph tags.
Database: Neon Postgres (already in the stack). Render Postgres is the fallback.
Storage: Cloudflare R2. Free egress is the reason; splat files are 10 to 200 MB and every buyer view streams one.
Reconstruction: Phase 0 uses the KIRI Engine API. Phase 2 moves to self-hosted nerfstudio and gsplat on RunPod serverless GPUs at roughly 0.11 to 0.93 USD per tour.
Viewer: PlayCanvas engine (MIT) rendering compressed SOG splats produced by splat-transform (MIT). SuperSplat (MIT) for manual cleanup in Phase 0.

Full component map with repos and wiring: [[Orwell Tours System Anatomy]].

## 4. The agent app

Framework: Expo with React Native, one TypeScript codebase for both platforms. EAS Build compiles and signs both binaries in the cloud, so no Mac is needed. EAS Update ships JS fixes over the air. Expo Router for navigation, React Query and Zustand for state. Repos: `ngindubai/orwell-tours-app` and `ngindubai/orwell-tours-api`.

Guided capture is the differentiator. Phone video of apartments fails reconstruction for predictable reasons: motion blur, fast pans, textureless walls, mirrors, dark hallways. The app attacks each at record time.

- Record at 1080p60 minimum, 4K30 where supported. More frames means more sharp frames for the pipeline to pick.
- Coaching overlay: gyroscope horizon line, a slow-down warning from angular velocity, a torch prompt in low light.
- Room checklist: the agent declares rooms up front and ticks each off; the overlay nudges arcing around a room, not walking straight through.
- Guardrails: 60 seconds minimum, 5 minutes maximum, blocked under 2 GB free storage.

Upload: presigned multipart upload direct to R2 (video never touches Render), background uploads with resume on network change, Wi-Fi-only default.

Status, preview, share: Expo push (APNs on Apple, FCM on Android); preview is a WebView of the same `/t/[slug]` buyers see; share sheet plus a dedicated WhatsApp button using wa.me deep links; QR codes for print. Every tour stores and displays the Trakheesi permit number, since tour pages are property advertising under Dubai rules.

## 5. The pipeline

Phase 0, hosted reconstruction: KIRI Engine API returns a Gaussian splat PLY. The worker runs splat-transform to compress PLY to SOG (roughly 10 to 20x smaller), renders a poster frame, writes both to R2. Manual cleanup in SuperSplat where needed.

Phase 2, self-hosted: a Docker image on RunPod serverless: ffmpeg sharp-frame extraction, COLMAP camera poses, nerfstudio splatfacto training on gsplat, splat-transform, SOG. Target 20 to 40 minutes per tour on a 4090 or A100 class card. Job states: queued, extracting, posing, training, compressing, ready or failed. Queue is BullMQ on Render Key Value. Failures surface to the agent in plain English mapped from pipeline error classes.

## 6. Viewer and sharing

- `/t/[slug]` serves the PlayCanvas viewer loading the SOG from R2. Fly-through camera tuned for one-handed phone use, orbit fallback.
- Open Graph tags per tour: title, poster image (1200x630, under 300 KB so WhatsApp accepts it), community, beds, price. This makes the link unfurl as a rich card.
- WhatsApp in-app browser: WebGL2 works but memory is tighter than Safari or Chrome, so the viewer ships a lightweight mode (capped splat count, no MSAA) on webview detection, plus an open-in-browser hint if WebGL fails.
- wa.me pre-fill from the agent's share button; a Chat with the agent button on the tour page deep-links to the listing agent's WhatsApp. The tour becomes a lead channel back to the agent without building lead capture.
- Custom domains: each agency points tours.theirbrand.ae at Render (per-service custom domains, automatic TLS). Tour pages carry the agency logo and colours from tenant config.

## 7. White-label strategy on mobile

Apple 4.2.6 rejects apps from a commercialised template or generation service unless submitted under the content owner's own account; 4.3 rejects duplicates. A separately branded store app per agency would need each agency to hold its own developer account and review cycle. That is an agency IT project, not a product.

The design that avoids it: one app in each store, themed to the agency after sign-in (logo, accent, name in share messages). The buyer-facing tour page, the only thing customers see, is fully white-labelled on the agency's own domain. A client demanding their own store listing becomes a paid enterprise tier where they enrol their own accounts and we submit for them.

## 8. Store accounts and release

| Item | Detail | Cost |
|---|---|---|
| Apple Developer Program | Organisation enrolment wants a D-U-N-S number for the Dubai entity; individual works to start but shows a personal seller name | 99 USD/year |
| Google Play Console | Organisation account also wants D-U-N-S; personal accounts created after Nov 2023 must run a 12-tester, 14-day closed test first | 25 USD one-off |
| Expo and EAS | Free tier covers early builds | 0 to start |
| APNs push key | Created in the Apple portal, uploaded to EAS | included |
| Firebase project | For FCM push credentials on Android | free |

Release train: EAS Build, then TestFlight internal and Play internal, then closed testing with a few friendly agents, then store review, then production. Apple review is typically 1 to 3 days first time; budget a rejection round. JS-only fixes ship over the air.

## 9. Data model (Neon Postgres)

- tenants: id, name, slug, logo_url, accent_hex, tour_domain, wa_number
- users: id, tenant_id, name, email, phone, role, push_token
- tours: id, tenant_id, user_id, slug, title, community, beds, price_aed, trakheesi_no, status, poster_key, sog_key, ply_key, video_key, duration_s, created_at, published_at
- jobs: id, tour_id, provider, state, error_class, gpu_seconds, cost_usd, timings
- share_events: id, tour_id, channel, created_at
- view_events: id, tour_id, ua_class, created_at

view_events gives agents a viewed-N-times number, the retention hook.

## 10. Phases

Phase 0 proof of tour (week 1). Phase 1 self-serve MVP (weeks 2 to 5). Phase 2 pipeline ownership (weeks 6 to 10). Phase 3 white-label and commercial (weeks 10 to 14). Each phase is its own Claude Code session with this note as the brief.

## 11. Costs

| | Setup | 0/mo | 50/mo | 500/mo |
|---|---|---|---|---|
| Render (web, worker, Key Value) | | ~21 | ~28 | ~60 |
| Neon | | 0 | 0 to 19 | 19 |
| R2 | | ~0 | ~2 | ~15 |
| Reconstruction Phase 0 (KIRI) | | 0 | ~50 to 150 | move to Phase 2 |
| Reconstruction Phase 2 (RunPod) | | 0 | ~5 to 45 | ~55 to 465 |
| Apple, Google, Expo | 124 first year | ~8 | ~8 | 8 plus EAS |
| Indicative total | ~124 | ~29/mo | ~90 to 200/mo | ~160 to 570/mo |

Matterport charges per space plus subscriptions and needs special cameras or slow scans. A phone-video-in, WhatsApp-link-out product undercuts it on cost and workflow. Price per published tour or a monthly agency bundle.

## 12. Manual setup

Full browser prompts in [[Orwell Tours Setup Prompts]]: Render, Neon, Cloudflare R2, KIRI (Phase 0), RunPod (Phase 2), Apple Developer, Google Play, Expo, Firebase, tours domain, and optional Meta WhatsApp Business.

## 13. Licences

PlayCanvas engine MIT, SuperSplat MIT, splat-transform MIT, playcanvas/react MIT, nerfstudio Apache 2.0, gsplat Apache 2.0, COLMAP BSD, ffmpeg as an LGPL build. Excluded: OpenSplat (AGPL), Inria 3DGS reference (non-commercial), GLOMAP (verify before ever adopting). Repo detail in [[3D Reconstruction]].
