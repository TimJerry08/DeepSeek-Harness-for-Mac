# DeepSeek Harness for macOS

> **Truly open‑box‑ready**: download, double‑click, and you’re in.  
> No terminal, no Node.js, no browser tabs – just a native macOS app.

[![Platform](https://img.shields.io/badge/Platform-macOS-1E90FF?style=flat&logo=apple)](https://www.apple.com/macos/)
[![Apple Silicon](https://img.shields.io/badge/Apple%20Silicon-M1%2F2%2F3%2F4-333333?style=flat&logo=apple)](https://www.apple.com/mac/)
[![Version](https://img.shields.io/badge/Version-0.1.0-blue)](https://github.com/your-username/your-repo/releases)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-000000)](https://github.com/your-username/your-repo)

---

## Introduction

**DeepSeek Harness for macOS** is a native Swift + WKWebView wrapper around the official [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) CLI tool.

It turns the command‑line experience into a **double‑clickable desktop application** – perfect for anyone who wants to use DeepSeek’s powerful local evaluation/sandbox environment without touching a terminal.

---

## Features

- **Truly open‑box ready** – everything is included: Node.js v24.19.0 LTS and `@deepseek-ai/dsh@0.1.0-rc.7` are bundled inside the app.
- **Native macOS experience** – built with Swift and WKWebView (zero Electron/Tauri overhead). Launches in **under 3 seconds** on Apple Silicon.
- **Minimal download size** – the compressed `.dmg` is only **87 MB** (expands to ~393 MB on disk).
- **Single‑process lifecycle** – the `dsh web` server runs as a child process in its own process group; it is fully terminated when you quit the app.
- **Menu bar presence** – the app stays alive in the menu bar when you close the window, using the app’s cover icon. One‑click restart, open in browser (for debugging), and copy the service address.
- **Native diagnostics** – if something goes wrong, you can view live logs, copy diagnostic info, or open the log file directly from the app.
- **Clean about panel** – clearly shows built‑in runtime versions and copyright attribution.

---

## System Requirements

- **Apple Silicon Mac** (M1, M2, M3, or M4) – Intel Macs are **not** supported in this release.
- macOS 13.0 (Ventura) or later.

---

## Installation

1. Download the latest `.dmg` from the [Releases].
2. Open the `.dmg` and drag `DeepSeek Harness.app` to your `Applications` folder.
3. Double‑click the app to launch it.

> **Important**: The app is not notarised yet. When you first open it, macOS may show a warning that it “cannot be verified”. Simply **Control‑click** the app and select **Open** – then confirm you want to open it. This is a one‑time step.

---

## How It Works

- The app starts a local HTTP server on `127.0.0.1` (port `3080` by default, automatically falls back to another port if occupied).
- It then loads the DeepSeek Harness Web UI inside a native WKWebView window – **no separate browser tab needed**.
- All data stays on your machine; no external network requests are made (except for DeepSeek API calls if you configure them).

---

## Known Limitations (v0.1.0)

- **Apple Silicon only** – Intel builds are not provided due to lack of testing hardware.
- **Not notarised** – you’ll need to allow the app to run via the Control‑click method described above.
- **Size** – the expanded app is ~393 MB because Node.js and all dependencies are embedded. We plan to optimise this in future releases.
- **No auto‑update** – for now, please check the Releases page manually for new versions.

---

## Development / Building (for advanced users)

The source code of this wrapper is **not open‑source** at this time. However, if you are curious, the app is built using:

- Swift (AppKit & WKWebView)
- Node.js (bundled as a runtime)
- The official `@deepseek-ai/dsh` package

If you wish to build a similar wrapper for yourself, you can inspect the binary structure – but we do not provide build scripts publicly.

---

## Credits & Licensing

- **DeepSeek Harness** – developed by DeepSeek AI, released under the [MIT License](https://github.com/deepseek-ai/deepseek-harness/blob/main/LICENSE).
- **Node.js** – Copyright Node.js contributors, released under the [MIT License](https://github.com/nodejs/node/blob/main/LICENSE).

**This wrapper (the macOS app shell)** is © 2026 Timothy-Wang. All rights reserved.  
It is not open‑source; you are granted a limited license to use the provided binary for personal or commercial purposes, but you may not redistribute, reverse‑engineer, or modify it without explicit permission.

---

## Feedback & Support

- For bug reports or feature suggestions, please [open an Issue](https://github.com/your-username/your-repo/issues).
- For general questions, you can reach out via [Twitter / other contact method] (optional).

---

**Made with ❤️ by a high‑school graduate who believes great software should never require a terminal.**

*Download now and experience the true open‑box readiness.*
