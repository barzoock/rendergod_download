<div align="center">

<img src="https://rendergod.app/icon.png" alt="RenderGod" width="100" />

# RenderGod

**Render management & automation tool for Blender**

Process monitoring · Crash recovery · Queue management · Telegram integration · Performance tuning

<br/>

[![Release](https://img.shields.io/github/v/release/barzoock/rendergod_download?style=flat-square&label=latest)](https://github.com/barzoock/rendergod_download/releases/latest)
![Platform](https://img.shields.io/badge/platform-Windows_10%2F11-0078D6?style=flat-square&logo=windows&logoColor=white)
![Blender](https://img.shields.io/badge/Blender-4.0%2B-E87D0D?style=flat-square&logo=blender&logoColor=white)
![Runtime](https://img.shields.io/badge/runs-100%25_local-darkgreen?style=flat-square)

<br/>

<img src="https://rendergod.app/RendegodUI.png" alt="RenderGod UI" width="700" />

<br/>

[Website](https://rendergod.app/) · [Documentation](https://rendergod.app/docs) · [Download](https://github.com/barzoock/rendergod_download/releases/latest)

</div>

---

## Overview

RenderGod wraps around Blender's rendering pipeline to provide process supervision, automatic crash recovery, queue management, and remote control via Telegram. Everything runs locally — no cloud, no external servers, no data leaves your machine.

---

## Features

### UnCrash — Process Recovery Engine

Monitors the Blender process and automatically recovers from failures. Resumes from the exact frame where it stopped.

<div align="center">
<table>
<tr>
<td width="280">

**Crash Detection**
Watches the Blender process. On unexpected exit, restarts and resumes from last completed frame.

</td>
<td width="280">

**Freeze Detection**
Monitors frame render time against configurable thresholds. Kills and restarts stuck frames automatically.

</td>
<td width="280">

**Reboot Survival**
Persists state to disk. After OS crash or power loss, resumes on next boot — bypasses Windows login via encrypted session.

</td>
</tr>
</table>
</div>

`Configurable retry limits` · `Telegram alerts on recovery` · `Per-job settings`

---

### Telegram Bot — Remote Control

Full bidirectional control over your render pipeline through a Telegram bot. Not just notifications — actual command execution.

<div align="center">
<img src="https://rendergod.app/telegram-iphone.webp" alt="Telegram Bot Interface" width="260" />
</div>

| Command Type | Description |
|---|---|
| **Live Previews** | Sends rendered frame previews (image + video) to chat |
| **Queue Control** | Pause, resume, stop, skip, reorder jobs remotely |
| **Status Polling** | Current frame, ETA, progress percentage, job info |

---

### Render Queue

<div align="center">
<img src="https://rendergod.app/Features/renderqueue.webp" alt="Render Queue" width="650" />
</div>

Manages multiple `.blend` files, scenes, cameras, and view layers as independent queue items. Supports drag reorder, priority, and per-item render settings.

`Real-time status` · `ETA tracking` · `Bulk operations` · `Saveable presets`

---

### Batch Generator

<div align="center">
<img src="https://rendergod.app/Features/queuemultiple.webp" alt="Batch Generator" width="650" />
</div>

Enumerates all scenes, cameras, and view layers in a `.blend` file and generates queue entries for any combination. Replaces manual per-camera/per-scene queue setup.

`Multi-scene` · `Auto-camera detection` · `Combinatorial generation`

---

### Live Preview

<div align="center">
<img src="https://rendergod.app/Features/Preview.webp" alt="Live Preview" width="650" />
</div>

Displays each rendered frame as it completes. Supports scrolling through completed frames, zoom, and grid view for File Output nodes and render layers.

`Frame-by-frame playback` · `Scroll-wheel zoom` · `Multi-output grid` · `EXR + Multilayer support`

---

### Performance Optimization

System-level and Blender-level tweaks applied before render start to reduce per-frame render time.

<div align="center">

| | Metric |
|---|---|
| **Benchmark** | RTX 4090 · Classroom scene · 32 samples · OptiX |
| **Result** | **18.11% faster** vs stock Blender |

</div>

`Process priority elevation` · `GPU memory management` · `Scene-level optimization toggles` · `NVIDIA GPU acceleration`

---

### Image Sequence ↔ Video

<div align="center">
<img src="https://rendergod.app/img2vdo.webp" alt="Sequence to Video" width="650" />
</div>

Bidirectional conversion between image sequences and video files. Supports ProRes 4444 with alpha, H.264, and other professional codecs via integrated encoders.

`One-click conversion` · `ProRes Alpha` · `Frame extraction from video`

---

### Smart Export

<div align="center">
<img src="https://rendergod.app/Features/SmartExport.svg" alt="Smart Export" width="650" />
</div>

Automatically structures output directories using dynamic path tokens (`{scene}`, `{camera}`, `{layer}`, etc.). Handles versioning and supports Blender's File Output nodes natively — syncs paths across multiple compositor outputs.

`Dynamic folder paths` · `Auto-versioning` · `File Output Node sync` · `Customizable templates`

---

### Post-Render Actions

<div align="center">
<img src="https://rendergod.app/actionwhendone.webp" alt="Actions When Done" width="650" />
</div>

Configurable actions triggered on queue completion or per-job completion.

`Auto shutdown / sleep` · `Auto image-sequence → video` · `Custom shell commands`

---

### Blender Addon

<div align="center">
<img src="https://rendergod.app/Features/BlenderAddon.webp" alt="Blender Addon" width="650" />
</div>

Native Blender addon — adds a sidebar panel for sending the current project directly to RenderGod's queue. Detects scene settings, cameras, and frame range automatically.

`Blender sidebar integration` · `One-click send to queue` · `Auto settings detection`

---

### Auto Bake Physics

<div align="center">
<img src="https://rendergod.app/Features/autobake.webp" alt="Auto Bake" width="650" />
</div>

Automatically bakes all physics simulations (rigid body, cloth, fluid, smoke, soft body) before render start. Prevents non-deterministic results and mid-render cache misses.

`All simulation types` · `Pre-render bake` · `Deterministic output`

---

## Workflow

```
1. Configure    →  Set UnCrash preferences, link Telegram bot, configure post-actions
2. Import       →  Drag-and-drop .blend files or send from Blender addon
3. Optimize     →  Toggle performance settings, batch generate queue items
4. Render       →  Live preview, real-time progress, frame-by-frame monitoring
5. Control      →  Telegram commands for remote queue management
6. Post-process →  Auto-convert sequences to video, run custom actions, shutdown
```

---

## Requirements

| Component | Version |
|---|---|
| OS | Windows 10 / 11 (64-bit) |
| Blender | 4.0+ |
| RAM | 4 GB minimum |
| Disk | ~100 MB |

---

## Install

1. Download the latest release from [Releases](https://github.com/barzoock/rendergod_download/releases/latest)
2. Extract to any directory
3. Run `RenderGod.exe`

Auto-updates are built in — the app checks for updates on launch and applies them automatically.

---

## Architecture

- Runs as a standalone Windows process alongside Blender
- Monitors Blender via process supervision (not Blender scripting API)
- State persisted to local disk for crash/reboot recovery
- Telegram integration via bot API with encrypted local bridge
- No external servers, no telemetry, no cloud dependencies
- All file operations stay on the local filesystem

---

## Links

- **Website:** [rendergod.app](https://rendergod.app/)
- **Docs:** [rendergod.app/docs](https://rendergod.app/docs)
- **Releases:** [GitHub Releases](https://github.com/barzoock/rendergod_download/releases/latest)

---

<div align="center">

**License:** Proprietary. All rights reserved.

</div>
