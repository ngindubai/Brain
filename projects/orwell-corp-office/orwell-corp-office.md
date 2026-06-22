---
title: Orwell Corp 3D office - tracker
area: products
tags: [project, orwell-corp, 3d]
status: active
stage: Viewer visual polish and designed-asset swap
next_action: Restore Blender, retry Poly Pizza asset fetch one at a time with hard socket timeouts
updated: 2026-06-22
---

# Orwell Corp 3D office

Area: [[areas/products/products]]. Design target: [[areas/agent-org/agent-behaviour-design]] (the glass office).

## The one goal

A polished 3D office in the Orwell-Corp command centre that shows the real agent architecture, built in Blender, exported as a GLB, and loaded in the React Three Fiber Office tab.

## What we have learnt

- Two office options live in the app: the procedural R3F office, and the Blender-built option B GLB.
- The Blender MCP is the official Blender Foundation lab server (port 9876). It needs Allow Online Access on and the MCP bridge running, or it silently fails.
- N8AO ambient occlusion is the confirmed performance killer. Bloom, explicit ACES Filmic tone mapping and a subtle vignette are the cheap wins. The composer default is AgX, which looks grey.
- Binary GLB cannot be pushed via the GitHub connector. Upload by hand to `public/office/`.
- A Poly Pizza GLB fetch froze Blender (synchronous Python on a hanging socket). Retry one asset at a time with hard timeouts.

## Progress

Done:
- ~1,045-object scene built and exported (orwell-office-optionB.glb). R3F loader and the third toggle wired and deploying.
- Lighting and tone-mapping pass done. Furniture layout fixes done.

Frontier:
- Swap scripted primitives for designed CC0 assets (Poly Pizza, Quaternius, Kenney). Blender needed a restart after the freeze.

## Next actions

1. Save a .blend checkpoint.
2. Retry Poly Pizza fetch, one asset, hard socket timeout.
3. Test a designed robot and desk GLB; if good, replicate across the six zones.
4. Re-export GLB, upload by hand to `public/office/`.

## Open questions

- Keep both office options, or retire the procedural one once the GLB is good?
