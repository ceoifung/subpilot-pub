<div align="center">

# SubPilot

**闻弦歌 · 知雅意**

### 把世界读给你听 · 100% 本地 AI 双语字幕播放器

任何视频拖进来，实时出中文字幕 —— 无需账号、无需搜索字幕、无一字节上传。

[![release](https://img.shields.io/github/v/release/ceoifung/subpilot-pub?label=%E6%9C%80%E6%96%B0%E7%89%88%E6%9C%AC)](https://github.com/ceoifung/subpilot-pub/releases)
[![platform](https://img.shields.io/badge/%E5%B9%B3%E5%8F%B0-Windows%20%7C%20Linux-blue)](#-下载安装)
[![size](https://img.shields.io/badge/CPU%E5%AE%89%E8%A3%85%E5%8C%85-6.6MB-success)](#-下载安装)
[![privacy](https://img.shields.io/badge/%E9%9A%90%E7%A7%81-100%25%E6%9C%AC%E5%9C%B0%E6%8E%A8%E7%90%86-important)](#-为什么是-subpilot)

**[⬇️ 立即下载](#-下载安装)** · **[🚀 快速开始](#-快速开始)** · **[❓ 常见问题](#-faq)** · **[English](README.en.md)**

</div>

---

**6.6MB** CPU 版安装包 · **99+** 种语音识别语言 · **0** 字节上传 · **2** 个大模型全程本地运行

## 🎬 为什么是 SubPilot

看生肉视频的老三样烦恼：**字幕搜不到、时间轴对不上、云服务要传片还要登录。**

SubPilot 把两 个 AI 大模型装进你的电脑：语音识别与翻译全程本地运行，字幕自动生成、逐句对齐时间轴，永远跑在播放进度前面。

| | 字幕网站 | 云端转写服务 | **SubPilot** |
|---|:---:|:---:|:---:|
| 拿到字幕 | 靠运气搜索 | 上传排队 | **拖进来就有** |
| 时间轴对齐 | 经常错位 | 视情况 | **逐句精确对齐** |
| 隐私 | — | 音视频上传云端 | **100% 本地，零上传** |
| 费用 / 账号 | 广告 / 弹窗 | 订阅 / 限额 | **免费 · 免登录** |
| 断网可用 | ❌ | ❌ | ✅ |

## ✨ 特性

**🎬 播放器**
- 常见视频 / 音频格式拖入即播（mp4 / mkv / webm / mov / avi / ts …）
- 在线视频：HLS（m3u8）点播与直播边播边识别
- 批量任务：多文件后台依次生成 SRT，每个文件可单独设置识别语言与翻译目标
- 播放列表：播放记录持久化，快速重播；快捷键 `空格` 暂停 · `←→` 快退快进 5 秒 · `↑↓` 音量

**⚡ 字幕引擎**
- 追赶式预跑：字幕始终跑在播放进度前面，而不是追着进度跑
- 拖动秒响应：拖到哪，识别立即从目标点优先补跑，不装死不等队列
- 逐句精确对齐：识别时间戳逐 token 对齐到画面，长句自动拆分、幻觉自动过滤
- 缓存秒开：已看过的视频再打开，字幕直接就位，并可导出 `.srt` 复用

**🧠 AI 双引擎（全本地）**
- 识别：Whisper large-v3-turbo，支持 99+ 种语言
- 翻译：Qwen3-4B 指令模型，带上下文连贯翻译，懂语气、懂梗
- 字幕语言：源语言 / 目标语言自由组合

**🔒 隐私与性能**
- 100% 本地推理：音频不出机器，断网照用
- GPU 版显存自适应：识别恒走 GPU（提速数倍），剩余显存充足时翻译也自动上 GPU
- CPU 版人人能跑：安装包仅 6.6MB，内置解码器，零额外依赖

## 🚀 快速开始

**① 下载安装** —— 到 [Releases](https://github.com/ceoifung/subpilot-pub/releases) 选一个版本（见下方选择表）

**② 下载模型** —— 首次启动按引导一键下载（免登录、断点续传、国内镜像直连）；或手动放置，见 [模型说明](#-模型说明)

**③ 拖入视频** —— 播放并等待几秒，双语字幕（原文 + 中文）自动出现

## 📥 下载安装

| 文件 | 平台 | 说明 |
|---|---|---|
| `SubPilot-x.y.z-x64-setup.exe` | Windows | **通用 CPU 版**（绝大多数人选这个） |
| `SubPilot-x.y.z-x64-GPU-setup.exe` | Windows | NVIDIA 显卡版：识别恒走 GPU 提速数倍，显存充足时翻译也上 GPU。CUDA 运行库已内置，装好显卡驱动即可 |
| `subpilot-x.y.z_amd64.deb` | Linux (Ubuntu 22.04+) | 通用 CPU 版 |
| `subpilot-x.y.z_amd64-GPU.deb` | Linux | GPU 版（需 NVIDIA 驱动；CUDA 运行库已随包） |

> 💡 GPU 版体积较大（约 628MB）属正常现象：包含为各代显卡预编译的 CUDA 设备码与运行库。RTX 30 系首次启动会做一次性的 JIT 编译，稍等片刻即可，之后永久缓存。

## 🤖 模型说明

程序本体不含模型（这也是安装包小的原因）。两种获取方式：

**方式一：应用内下载（推荐）** —— 首次启动自动检测并引导下载，支持断点续传与取消，国内走镜像直连。

**方式二：手动放置** —— 从 [models-v1 Release](https://github.com/ceoifung/subpilot-pub/releases/tag/models-v1) 下载（免登录），按下述布局放入：

```
安装目录/models/
├── whisper-turbo/
│   └── ggml-model.bin        ← 由 ggml-large-v3-turbo.bin 改名（约 1.6G）
└── qwen3-4b-q4km.gguf        ← 分卷合并后放入（约 2.4G）
                               cat qwen3-4b-q4km.gguf.part* > qwen3-4b-q4km.gguf
```

- Windows 安装目录：`C:\Program Files\SubPilot\`
- Linux：程序所在目录的 `models/`
- 完整性校验：`SHA256SUMS.txt`
- 也可从 [hf-mirror.com](https://hf-mirror.com) 获取同名原文件（`ggerganov/whisper.cpp` / `bartowski/Qwen_Qwen3-4B-Instruct-2507-GGUF`）

## ❓ FAQ

**GPU 版为什么那么大？**
包含为 NVIDIA 各代显卡预编译的 CUDA 设备码与完整运行库（用户免装 CUDA）。换来的是识别速度数倍提升。不需要 GPU 加速就用 CPU 版，只有 6.6MB。

**RTX 30 系显卡首次启动久？**
30 系走一次性 PTX JIT 编译（几十秒到几分钟，视机器而定），完成后写入驱动缓存，之后启动与 40 系一样快。

**支持哪些语言的识别？**
Whisper 支持的 99+ 种语言均可（英 / 日 / 韩 / 法 / 德 / 俄 / 西 ……），翻译目标语言自由选择。

**生成的字幕能单独保存吗？**
能。批量任务自动在视频旁生成同名 `.srt`；播放中也可随时导出当前字幕。

**对电脑配置有要求吗？**
CPU 版无特殊要求，人人能跑；GPU 版需 NVIDIA 显卡与正常驱动。模型加载约需 6GB 以上内存/显存余量，启动时有真实进度显示。

**和在线字幕 / 转写服务的本质区别？**
不需要上传任何音视频，不依赖字幕资源站的存在，断网可用，永久免费。

## 🗺️ Roadmap

- [ ] 字幕样式自定义（字体 / 大小 / 位置）
- [ ] 更多可切换的翻译模型
- [ ] 字幕时间轴手动微调
- [ ] macOS 支持
- [ ] 移动端探索

## 🙏 支持一下

如果 SubPilot 帮到了你，欢迎点一个 **⭐ Star** 让更多人看到 —— 这是对持续更新最大的鼓励。

遇到问题或有好想法？请开 [Issues](https://github.com/ceoifung/subpilot-pub/issues) 告诉我。

---

<div align="center">

<sub>闻弦歌 · 知雅意</sub>

</div>
