<div align="center">

# SubPilot

**Hear every word, in your language.**

### A 100% local AI bilingual-subtitle player

Drop in any video and get real-time subtitles in your language — no account, no subtitle hunting, not a single byte uploaded.

[![release](https://img.shields.io/github/v/release/ceoifung/subpilot-pub?label=latest)](https://github.com/ceoifung/subpilot-pub/releases)
[![platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue)](#-download)
[![size](https://img.shields.io/badge/CPU%20installer-6.6MB-success)](#-download)
[![privacy](https://img.shields.io/badge/privacy-100%25%20local%20inference-important)](#-why-subpilot)

**[⬇️ Download](#-download)** · **[🚀 Quick Start](#-quick-start)** · **[❓ FAQ](#-faq)** · **[简体中文](README.zh-CN.md)**

</div>

---

**6.6MB** CPU installer · **99+** recognized languages · **0** bytes uploaded · **2** large models running fully local

## 🎬 Why SubPilot

The classic pain of watching foreign-language videos: **subtitles you can't find, timelines that don't line up, and cloud services that want your video *and* your login.**

SubPilot puts two large AI models on your own machine — speech recognition and translation run entirely locally, subtitles are generated automatically, aligned sentence by sentence, and always stay ahead of your playback position.

| | Subtitle sites | Cloud transcription | **SubPilot** |
|---|:---:|:---:|:---:|
| Getting subtitles | Luck-based search | Upload & queue | **Drop it in, done** |
| Timeline sync | Often off | Varies | **Precise per-sentence alignment** |
| Privacy | — | Media uploaded to cloud | **100% local, zero upload** |
| Cost / account | Ads | Subscription / quota | **Free · no sign-up** |
| Works offline | ❌ | ❌ | ✅ |

## ✨ Features

**🎬 Player**
- Drag & play for common video/audio formats (mp4 / mkv / webm / mov / avi / ts …)
- Online video: HLS (m3u8) VOD and live streams, transcribed while playing
- Batch mode: generate SRT files for a whole queue in the background, with per-file language settings
- Persistent playlist; hotkeys: `Space` pause · `←→` seek ±5s · `↑↓` volume

**⚡ Subtitle engine**
- Catch-up prefetching: subtitles always run *ahead* of playback, never behind
- Instant seeking: drag anywhere and recognition immediately re-prioritizes from that point
- Token-level timestamp alignment; long sentences auto-split, hallucinations filtered
- Cached for instant re-open; exportable as `.srt`

**🧠 Dual AI engines (fully local)**
- Recognition: Whisper large-v3-turbo, 99+ languages
- Translation: Qwen3-4B instruction model, context-aware — catches tone and nuance
- Free combination of source / target languages

**🔒 Privacy & performance**
- 100% local inference: audio never leaves your machine, works offline
- GPU edition with adaptive VRAM: recognition always on GPU (several times faster); translation moves to GPU when VRAM allows
- CPU edition runs anywhere: 6.6MB installer, decoder bundled, zero dependencies

## 🚀 Quick Start

**① Install** — grab a build from [Releases](https://github.com/ceoifung/subpilot-pub/releases) (see the table below)

**② Get the models** — first launch guides you through a one-click download (no login, resumable, mirror-friendly); or place them manually, see [Models](#-models)

**③ Drop in a video** — wait a few seconds and bilingual subtitles (original + translation) appear

## 📥 Download

| File | Platform | Notes |
|---|---|---|
| `SubPilot-x.y.z-x64-setup.exe` | Windows | **Universal CPU build** (the right choice for most) |
| `SubPilot-x.y.z-x64-GPU-setup.exe` | Windows | NVIDIA build: recognition always on GPU, translation too when VRAM allows. CUDA runtime bundled — just have a normal driver |
| `subpilot-x.y.z_amd64.deb` | Linux (Ubuntu 22.04+) | Universal CPU build |
| `subpilot-x.y.z_amd64-GPU.deb` | Linux | GPU build (NVIDIA driver required; CUDA runtime bundled) |

> 💡 The GPU build is large (~628MB) by design: it ships pre-compiled CUDA device code for multiple GPU generations plus the runtime. RTX 30-series cards do a one-time JIT compilation on first launch; it's cached permanently afterwards.

## 🤖 Models

The installer ships without models — that's how it stays tiny. Two ways to get them:

**Option A: in-app download (recommended)** — first launch detects and guides you, resumable and cancellable.

**Option B: manual placement** — download from the [models-v1 Release](https://github.com/ceoifung/subpilot-pub/releases/tag/models-v1) (no login) and lay them out as:

```
install dir/models/
├── whisper-turbo/
│   └── ggml-model.bin        ← rename of ggml-large-v3-turbo.bin (~1.6G)
└── qwen3-4b-q4km.gguf        ← merge parts first (~2.4G)
                               cat qwen3-4b-q4km.gguf.part* > qwen3-4b-q4km.gguf
```

- Windows install dir: `C:\Program Files\SubPilot\`
- Linux: `models/` next to the binary
- Integrity: `SHA256SUMS.txt`

## ❓ FAQ

**Why is the GPU build so big?**
It bundles pre-compiled CUDA device code for NVIDIA GPU generations plus the full CUDA runtime (no CUDA install needed on your side). The payoff is a multi-fold speedup. If you don't need GPU acceleration, the CPU build is only 6.6MB.

**RTX 30-series first launch is slow?**
A one-time PTX JIT compilation runs (tens of seconds to a few minutes depending on the machine), then it's cached by the driver for good.

**Which languages are supported?**
Anything Whisper recognizes — 99+ languages — with a free choice of translation target.

**Can I keep the generated subtitles?**
Yes. Batch jobs write a matching `.srt` next to each video; you can also export anytime during playback.

**What are the system requirements?**
The CPU build has no special requirements. The GPU build needs an NVIDIA card and driver. Leave ~6GB+ of free memory/VRAM for the models; startup shows real loading progress.

**How is this different from online subtitle/transcription services?**
No media ever leaves your machine, no dependency on subtitle sites, works offline, free forever.

## 🗺️ Roadmap

- [ ] Customizable subtitle styling (font / size / position)
- [ ] More interchangeable translation models
- [ ] Manual timeline fine-tuning
- [ ] macOS support
- [ ] Mobile exploration

## 🙏 Show your support

If SubPilot helps you, a **⭐ Star** goes a long way in helping others find it.

Run into trouble or have an idea? Open an [Issue](https://github.com/ceoifung/subpilot-pub/issues).

---

<div align="center">

<sub>闻弦歌 · 知雅意 — Hear the music, know the heart.</sub>

</div>
