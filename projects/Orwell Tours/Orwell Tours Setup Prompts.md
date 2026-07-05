---
title: Orwell Tours Setup Prompts
tags: [project, orwell-tours, setup, manual-tasks, keys]
status: active
updated: 2026-07-05
project: "[[Orwell Tours]]"
---

# Orwell Tours Setup Prompts

The manual browser tasks for [[Orwell Tours]]: accounts, keys, hosting, app stores. Each is a job Claude Code cannot do because it needs a human account, a payment card, or an identity check. Paste each prompt into the Claude browser extension on the named site. Work top to bottom; NOW cards block the build, LATER cards wait for their phase. Save each output into the ledger at the bottom. A rendered HTML version of these prompts with copy buttons was also produced; it sits in the chat outputs and can be committed here on request. Companion notes: [[Orwell Tours Build Plan]], [[Orwell Tours System Anatomy]].

Order of play: run P1 to P9 (P5 first, its D-U-N-S wait is the long pole), then open a Claude Code session with [[Orwell Tours Build Plan]] as the brief and the ledger in hand. Phase 0 needs only P1 to P4.

## P1 Neon, database (Now, console.neon.tech)

Holds every tenant, user, tour and job. New project in the existing Neon account.

Prompt: Sign in to console.neon.tech. Create a new project named orwell-tours with Postgres 16, region AWS Europe (Frankfurt) or closest to the Middle East. Open the project dashboard, select the pooled connection option, and copy the full connection string (starts with postgresql://). Do not create tables; the build scripts handle the schema.

Save: connection string as `DATABASE_URL`.

## P2 Cloudflare R2, storage (Now, dash.cloudflare.com)

Stores videos, 3D files and cover images. No bandwidth charges.

Prompt: Sign in to dash.cloudflare.com. Open R2 Object Storage and enable it if prompted (needs a card; usage sits in the free tier initially). Create a bucket named orwell-tours. Go to Manage R2 API Tokens, create a token named orwell-tours-api with Object Read and Write scoped to the orwell-tours bucket only. Copy the Access Key ID, Secret Access Key, and the S3 endpoint URL (https://ACCOUNT_ID.r2.cloudflarestorage.com). Leave public access off for now.

Save: `R2_ACCESS_KEY_ID`, `R2_SECRET_ACCESS_KEY`, `R2_ENDPOINT`, `R2_BUCKET=orwell-tours`.

## P3 Render, hosting (Now, dashboard.render.com)

Runs the API, viewer pages, queue and worker. Sign in via GitHub for automatic deploys.

Prompt: Go to dashboard.render.com and sign in using the GitHub account ngindubai, authorising Render. Create a Key Value instance named orwell-tours-queue on Starter, region Frankfurt, and copy its internal connection URL. Do not create the web service or worker yet; Claude Code creates them from a render.yaml blueprint. In Account Settings, GitHub, ensure the authorisation covers new repositories.

Save: `REDIS_URL` (the Key Value internal URL).

## P4 KIRI Engine, reconstruction (Now, kiriengine.app)

The hosted video-to-splat service for Phases 0 and 1. Pay per scan.

Prompt: Go to kiriengine.app and create an account with the Orwell email. Find the Developer or API section, subscribe to API access on the entry tier, and generate an API key. Note the per-scan price and confirm 3D Gaussian Splatting PLY export is included on the tier (we need Gaussian splat PLY, not just mesh).

Save: `KIRI_API_KEY` and the per-scan price.

## P5 Apple Developer Program (Now, slow, start first, developer.apple.com)

Required for TestFlight and the App Store. Organisation enrolment needs a D-U-N-S number for the Dubai entity, which can take days.

Prompt: Go to developer.apple.com/programs/enroll and sign in with the Orwell Apple ID (create one with two-factor if needed). Choose Organisation enrolment, legal entity name exactly as on the Dubai trade licence. For the D-U-N-S number, first check for an existing one via Apple's lookup link; if none, submit the free D-U-N-S request in the same flow (up to five working days, confirmation by email). Complete enrolment and pay 99 USD. If the wait blocks everything, enrol as Individual to unblock TestFlight, noting the seller name shows as a person until migrated. Afterwards note the Team ID under Membership Details.

Save: `APPLE_TEAM_ID`, the Apple ID email, the D-U-N-S number when it arrives.

## P6 Google Play Console (Now, play.google.com/console)

Required for Android. The organisation route avoids the 12-tester, 14-day rule for new personal accounts.

Prompt: Go to play.google.com/console/signup with the Orwell Google account. Choose Organisation, legal name as on the trade licence, provide the D-U-N-S from P5 (pause and return if it has not arrived). Pay the 25 USD fee and complete identity verification with passport or Emirates ID. Note the developer account name and owner email.

Save: developer account name and owner email.

## P7 Expo, app builds (Now, expo.dev)

EAS Build compiles and signs both apps in the cloud; no Mac needed.

Prompt: Go to expo.dev and sign up with the GitHub account ngindubai. Create an organisation named orwell and a project named orwell-tours. In Account Settings, Access Tokens, create a robot token named claude-code with owner access; copy it. Note the project slug and EAS project ID.

Save: `EXPO_TOKEN`, `EAS_PROJECT_ID`.

## P8 Firebase, Android push (Now, console.firebase.google.com)

Android push travels over Firebase Cloud Messaging. Free, ten minutes.

Prompt: Go to console.firebase.google.com with the same Google account as P6 and create a project named orwell-tours (Analytics optional). Add an Android app with package name ae.orwell.tours and download google-services.json. In Project Settings, Service Accounts, Generate new private key and download the service account JSON. Keep both files.

Save: google-services.json and the service account JSON, both handed to Claude Code.

## P9 Domain, tours web address (Now, your registrar)

The address on every shared link. Short matters in WhatsApp: orwl.ae or tours.orwell.ae.

Prompt: Sign in to the registrar for the Orwell domain. Add a CNAME with host tours pointing to the Render service address (orwell-tours.onrender.com once P3's service exists; return after Phase 1 if doing this early). If a new short domain is wanted, buy it first then add the CNAME. Render verifies and issues TLS automatically under the service Settings, Custom Domains.

Save: the chosen tours domain.

## P10 RunPod, own GPU pipeline (Phase 2, runpod.io)

Pay-per-second GPUs that replace KIRI and cut cost to cents per tour. Skip until Phase 2.

Prompt: Go to runpod.io, create an account with the Orwell email, add a card and load 25 USD. In Settings, API Keys, create a key named orwell-tours with serverless endpoint management. Do not create an endpoint; Claude Code deploys the worker image and endpoint itself.

Save: `RUNPOD_API_KEY`.

## P11 Meta, WhatsApp Business API (Optional, Phase 3+, business.facebook.com)

Only needed to send tours programmatically from the platform's own number. Normal share-sheet and wa.me sharing, the whole v1 design, needs nothing from Meta. Leave until a client asks.

Prompt: Go to business.facebook.com and create a Meta Business portfolio for Orwell, completing verification with the trade licence. In developers.facebook.com create a Business app, add WhatsApp, register a phone number for the Cloud API. Note the phone number ID and generate a permanent system-user token with whatsapp_business_messaging. Note the per-conversation price for the UAE.

Save: `WA_PHONE_ID`, `WA_TOKEN`.

## Key ledger

Hand this filled to Claude Code at the start of Phase 1.

| Key | From | Used for |
|---|---|---|
| DATABASE_URL | P1 Neon | All records |
| R2_ACCESS_KEY_ID / SECRET / ENDPOINT | P2 Cloudflare | Video and 3D storage |
| REDIS_URL | P3 Render | Job queue |
| KIRI_API_KEY | P4 KIRI | Reconstruction Phases 0 to 1 |
| APPLE_TEAM_ID | P5 Apple | iOS signing, TestFlight, App Store |
| Play developer account | P6 Google | Android distribution |
| EXPO_TOKEN / EAS_PROJECT_ID | P7 Expo | Cloud builds and OTA |
| google-services.json plus service JSON | P8 Firebase | Android push |
| Tours domain | P9 Registrar | Every shared link |
| RUNPOD_API_KEY | P10 RunPod | Own GPU pipeline, Phase 2 |
| WA_PHONE_ID / WA_TOKEN | P11 Meta | Programmatic sending, only if wanted |

Keep this note private; it is the master key list.
