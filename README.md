# SubPilot

本地视频双语字幕播放器：播放时自动识别语音（英/日/韩等）并实时翻译成中文，字幕跑在播放进度前面（追赶式预跑）。源码私有，本仓库仅作为公开发布通道。

## 下载

到 [Releases](https://github.com/ceoifung/subpilot-pub/releases) 选择：

| 文件 | 平台 | 说明 |
|---|---|---|
| `SubPilot-x.y.z-x64-setup.exe` | Windows | 通用 CPU 版 |
| `SubPilot-x.y.z-x64-GPU-setup.exe` | Windows | NVIDIA 显卡版，**显存自适应**：识别恒走 GPU（提速数倍）；剩余显存 ≥10GB 时翻译也自动上 GPU，不足则留 CPU。CUDA 运行库已内置，仅需正常装显卡驱动 |
| `subpilot-x.y.z_amd64.deb` | Linux (Ubuntu 22.04+) | 通用 CPU 版 |
| `subpilot-x.y.z_amd64-GPU.deb` | Linux | 显存自适应 GPU 版（需已安装 NVIDIA 驱动与 CUDA 运行库） |

## 模型（首次使用必读）

程序本体不含模型。到 [models-v1 Release](https://github.com/ceoifung/subpilot-pub/releases/tag/models-v1) 下载（免登录）：

```
安装目录/models/
├── whisper-turbo/
│   └── ggml-model.bin        ← 由 ggml-large-v3-turbo.bin 改名 (约1.6G)
└── qwen3-4b-q4km.gguf        ← 分卷合并: cat qwen3-4b-q4km.gguf.part* > qwen3-4b-q4km.gguf (约2.4G)
```

- Windows 安装目录：`C:\Program Files\SubPilot\`（或安装时选择的目录）
- Linux：程序所在目录的 `models/`
- 完整性校验：`SHA256SUMS.txt`
- 国内下载慢可从 hf-mirror.com 取同名原文件（`ggerganov/whisper.cpp` / `bartowski/Qwen_Qwen3-4B-Instruct-2507-GGUF`）

## 使用

- 拖入视频（mp4/mkv/webm/mov/avi/ts 及常见音频格式）→ 自动生成双语字幕
- 📦 批量：多文件后台依次生成 SRT（保存在各视频旁边，同名 `.srt`）
- 📋 列表：播放记录快速重播（保存在 `%APPDATA%\subpilot` / `~/.local/share/subpilot`）
- 💾 导出：当前视频字幕导出（`.xs.srt` 缓存，二次打开秒出）
- 快捷键：空格暂停 / ←→ 快退快进 5 秒 / ↑↓ 音量

## 构建说明

私有仓库打 tag（`v*`）→ 自动触发双平台 × CPU/GPU 四路构建并发布。模型文件由 models workflow 托管在本仓库 Release。

问题反馈请开 [Issues](https://github.com/ceoifung/subpilot-pub/issues)。
