# UniPlay

A lightweight game launcher and RAM reclamation utility 
for Windows, built with Rust and Tauri.

## Overview

UniPlay is a native Windows desktop application that 
provides a clean game library interface and reclaims 
physical RAM from idle background processes when you 
launch a game.

Built as an alternative to bloated game launchers — 
UniPlay's own footprint stays light while giving your 
game more breathing room on launch.

## What It Does

- Scans your Steam library automatically on launch
- Moves idle background processes out of physical RAM 
  when a game starts
- Logs exactly how much RAM was reclaimed per session
- Lets you set trim preferences per game
- Manual flush button for mid-session use
- No background monitoring loop — only runs when called

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Rust |
| Frontend | Tauri v2 + HTML/CSS/JS |
| System API | Windows (process management) |
| Licensing | LemonSqueezy (Merchant of Record) |
| State | Arc<Mutex> thread-safe pattern |

## Architecture Highlights

**Async game discovery**
Steam library scanning runs on a background thread via 
Tauri's async runtime — UI stays responsive during 
indexing regardless of library size.

**Accurate RAM measurement**
Background processes are batch trimmed first, then a 
settle period allows Windows to complete the operation 
before measuring. This prevents mid-trim readings that 
would inflate reported savings.

**Thread-safe state**
Shared application state is managed via Arc<Mutex> 
across async operations — game launches, trim operations, 
and UI updates don't interfere with each other.

**Lightweight by design**
Built on Tauri's native OS webview rather than bundling 
Chromium — no Electron overhead.

## Features

**Free tier:**
- Full Steam game library
- Safe mode RAM reclamation (Steam processes)
- Total RAM saved counter
- Manual turbo flush

**Pro tier:**
- Balanced mode (additional background processes)
- Per-game trim settings saved automatically
- Full session history and ledger
- Per-game RAM reclamation logs

## Status

v1.0.0 — Live and publicly available. Download at uniplay.systems

## License & Commercial Use

UniPlay is a commercial product. The source code in 
this repository is provided for transparency and 
portfolio purposes only.

## Links

- Website: [uniplay.systems](https://uniplay.systems)
- Support: supportuniplay@gmail.com

Proprietary. © 2026 UniPlay LTD. All rights reserved.

---
**Built by: Imaad Akhtar Irfan
 LinkedIn: Imaad Akhtar Irfan 
• Age 19 •  | Focusing on systems, logic, and building 
things that do what they say.
