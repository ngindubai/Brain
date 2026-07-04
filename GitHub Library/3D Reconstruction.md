---
title: 3D Reconstruction
tags: [github-library, repos, 3d, gaussian-splatting, reconstruction]
updated: 2026-07-05
---

# 3D Reconstruction

Third-party repos for photogrammetry, Gaussian splatting, and 3D web viewing. The stack behind [[Orwell Tours]]: video walkaround to interactive 3D property tour. Part of the [[GitHub Library]]. Feeds area [[Products]].

Status key: `using` in active use, `evaluating` testing, `shelf` parked. Full explanation of how each slots together is in [[Orwell Tours System Anatomy]].

## Viewer and editor (PlayCanvas, MIT)

| Repo | What it is | What we pull | Status |
|---|---|---|---|
| [playcanvas/engine](https://github.com/playcanvas/engine) | WebGL/WebGPU engine with built-in Gaussian splat rendering, streams compressed SOG. Runs in the buyer's browser | The splat viewer for tour pages | evaluating |
| [playcanvas/react](https://github.com/playcanvas/react) | React components to embed the engine in one line, with camera controls | The tour page viewer wrapper | evaluating |
| [playcanvas/supersplat](https://github.com/playcanvas/supersplat) | Browser editor for cleaning splats: crop, despeckle, set opening camera. superspl.at | Manual scan cleanup in Phase 0 | evaluating |
| [playcanvas/splat-transform](https://github.com/playcanvas/splat-transform) | CLI: converts and compresses PLY to SOG, ~10 to 20x smaller | Final pipeline compression step | evaluating |
| [playcanvas/model-viewer](https://github.com/playcanvas/model-viewer) | Generic 3D and splat viewer. Less flexible than building with react | Not used, reference only | shelf |

## Reconstruction pipeline (video to splat)

| Repo | What it is | What we pull | Status |
|---|---|---|---|
| [nerfstudio-project/nerfstudio](https://github.com/nerfstudio-project/nerfstudio) | Splatfacto training method, Apache 2.0. The splat trainer | Phase 2 self-hosted training | evaluating |
| [nerfstudio-project/gsplat](https://github.com/nerfstudio-project/gsplat) | CUDA Gaussian splatting library under nerfstudio, Apache 2.0 | The training maths | evaluating |
| [colmap/colmap](https://github.com/colmap/colmap) | Structure-from-motion, works out camera poses from frames. BSD | Camera pose step in Phase 2 | evaluating |
| [FFmpeg/FFmpeg](https://github.com/FFmpeg/FFmpeg) | Video to frames, sharp-frame selection. Use LGPL build | Frame extraction | evaluating |
| [ArthurBrussee/brush](https://github.com/ArthurBrussee/brush) | Newer Rust splat trainer, cross-platform | Watch, lighter alternative | shelf |

## Excluded on licence (do not use in the product)

| Repo | Why excluded |
|---|---|
| [pierotofy/opensplat](https://github.com/pierotofy/opensplat) | AGPL. Poisons a commercial white-label SaaS. Avoid |
| Inria 3DGS reference (graphdeco-inria) | Non-commercial research licence. Avoid; nerfstudio and gsplat are the clean route |
| [colmap/glomap](https://github.com/colmap/glomap) | Verify licence before ever adopting; earlier versions were restrictive |

## Reconstruction as a service (not repos, for reference)

- KIRI Engine ([kiriengine.app](https://www.kiriengine.app)): hosted video-to-splat API, pay per scan. The Phase 0 and 1 provider. Setup at [[Orwell Tours Setup Prompts]] P4.
- Luma AI: hosted splat capture, fallback comparison.
- RunPod ([runpod.io](https://www.runpod.io)): serverless GPUs that host our own Phase 2 pipeline. Not a reconstruction tool itself, the compute under it.
