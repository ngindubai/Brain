---
title: NORTHLANDS - tracker
area: products
tags: [project, northlands, fivem, hobby]
status: active
stage: Deploying custom resource fixes
next_action: FTP-upload the flattened nl_deathdrop, verify only fxmanifest.lua and main.lua
updated: 2026-06-22
---

# NORTHLANDS

Area: [[areas/products/products]]. Spare-time hobby. FiveM zombie extraction-survival server, QBox base, ZAP-Hosting.

## What we have learnt

- Seven-pass source review done. City Bible master HTML compiled.
- Fix pack NORTHLANDS-FIXES.zip: nl_deathdrop, nl_taxifix, v-containerrobbery config fix.
- nl_zones rewritten with the zombie-zone boundary (around Y=0) and an IsInZombieZone export.
- Server restart only reloads files already on disk. It does not pull from GitHub. Changes must be uploaded via FTP.
- nl_deathdrop had to be flattened to a single top-level main.lua (the server/ subfolder did not survive FTP).

## Progress

Done:
- Source review, City Bible, custom resources written and pushed to the repo.

Frontier:
- The flattened nl_deathdrop is in the repo but not yet uploaded via FTP, so the server still warns.

## Next actions

1. Stop the server, delete the existing nl_deathdrop folder on the FTP right pane.
2. Upload the flattened folder, verify only fxmanifest.lua and main.lua, no server subfolder.
3. Restart, confirm the warning is gone.

## Open questions

- Build the from-scratch zombie spawner next, or source a community mod?
