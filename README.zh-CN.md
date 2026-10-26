# AI Voiceover Generator Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [AI Voice Cloning Skill](https://github.com/beatra-ai/ai-voice-cloning-skill)

从同一个入口选声音、把文稿做成可剪辑的配音、安排长篇或多语言音频，并创建可复用的品牌音色，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 从同一个入口选声音、把文稿做成可剪辑配音、安排长篇或多语言音频，并创建可复用的品牌音色。 |
| **底层模型** | MiniMax Voice Clone、MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。"></p>

*配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`voiceover-narration-studio`](skills/voiceover-narration-studio) | [SKILL.md](skills/voiceover-narration-studio/SKILL.md) | 0.2.9 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/voiceover-narration-studio) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-voiceover-generator-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-voiceover-generator-skill voiceover-narration-studio
```

也可以克隆本仓库，把 `skills/voiceover-narration-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-voiceover-generator-skill 安装 voiceover-narration-studio skill（目录 skills/voiceover-narration-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*用三个预设声音依次朗读三段短文案：平静的产品讲解、轻快的短视频广告和纪录片旁白，共 41 秒。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
用三个不同的预设声音读这三段短稿：Tidewell 台灯的平静产品讲解、Crunchlane 薯片的活泼短视频广告、一句纪录片旁白。按这个顺序交付三段音频。
```

提示词：

```text
Meet Tidewell, a desk lamp that follows your day. In the morning, it glows cool and bright for focus. After sunset, it turns warmer, so your eyes can rest.

Okay, stop scrolling! Crunchlane spicy mango chips are here: sweet, hot, and seriously crunchy. Grab a bag this Saturday, and tell us how fast it disappeared!

High in the northern mountains, the first snow falls without a sound. A red fox stops and listens. Something small is moving beneath the snow. She waits. Then she leaps.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **声音克隆** — 1 个模型（MiniMax Voice Clone）；样本 10–300 秒，最大 20 MB；需提交授权声明
- **语音合成** — 2 个模型（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）；FLAC、MP3、OPUS、PCM、WAV；40 种语言；采样率 8、16、22.05、24、32、44.1 kHz；单次最多 50000 字符
  - 语言（ISO 639 代码）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 声音克隆 1；语音合成 2（MiniMax Voice Clone、MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

## 与同类方案对比

| | Beatra（本 skill） | [scenario-labs/skills](https://github.com/scenario-labs/skills) | [vargHQ/skills](https://github.com/vargHQ/skills) |
| --- | --- | --- | --- |
| 需要的账号或 key | 一个 Beatra 账号，不需要各家模型的 key | Scenario 账号（OAuth 登录）或 Scenario API key（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)） | VARG_API_KEY，所有 skill 都需要（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L70)） |
| 模型 | 声音克隆 1；语音合成 2（MiniMax Voice Clone、MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo） | 通过 scenario-audio skill 生成配音和语音（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L175)） | 通过 varg 平台使用 Kling、Flux、ElevenLabs、Sora 等模型（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L3)） |
| 花钱前 | 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费 | 质量检查和模型对比两个 skill 可先 dry-run 试算价格（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)） | 完整渲染前可先用 `--preview` 免费预览（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L158-L160)） |
| 支持的 Agent | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw | Claude Code、Cursor、Codex、Copilot 及另外 70 多种编程 Agent（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)） | Claude Code、Cursor、Windsurf、OpenCode、ClawHub 以及任何支持 Agent Skills 的工具（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L10)） |
| 安装 | `npx skills add beatra-ai/ai-voiceover-generator-skill` | `npx skills add scenario-labs/skills`，再连接 Scenario MCP 服务器（https://mcp.scenario.com/mcp）（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)） | `npx skills add vargHQ/skills`（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L59)） |
| 许可证 | MIT-0 | MIT（[出处](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)） | MIT（[出处](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/LICENSE)） |
| 最近更新 | 随每次发布更新（v0.2.9） | 2026-10-15（[出处](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)） | 2026-10-01（[出处](https://github.com/vargHQ/skills/commit/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d)） |

事实核对于 2026-10-16。有误请到 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/issues) 提 issue。

## 你能得到什么

- **先选对流程** — 单条配音、长篇旁白、已备好的多语言文稿和品牌音色各自有清楚的制作方式。
- **沿用所选音色** — 只比较符合语言与用途的候选音色，让持续更新的内容保持熟悉听感。
- **让长篇音频保持清晰顺序** — 按章节、课程、语言和持续更新场景整理音频，让每一段成品都方便查找、剪辑和复用。

## 适用场景

- **短视频配音** — 把文稿做成一条可直接剪辑的口播，并按受众选择音色和节奏。
- **有声书与课程配音** — 先用一段代表性内容试听，再让章节或课程保持顺序和同一个所选音色。
- **多语言配音** — 为已经备好的各语言文稿分别选择合适音色，成品按语言和段落归类。
- **品牌专属声音** — 用单人清晰样本创建有名字的音色，之后为新的文稿继续选择使用。

## 常见问题

### 可以制作哪些语音内容？

可以制作单条短视频配音、按顺序安排的有声书或课程旁白、基于各语言文稿的多语言音频，也可以创建可复用的品牌专属声音。

### 支持哪些语言？

当前语音合成模型覆盖 40 种语言，包括普通话和粤语；每次制作仍会确认当前所选音色和语音合成模型都支持目标语言。

### 可以使用自己的声音吗？

可以。使用单人清晰样本创建有名字的音色，再用于后续旁白、课程、通知和持续更新的品牌内容。

### 长篇和多语言项目怎样保持清晰顺序？

音频可按章节、课程、语言、市场或持续更新场景整理，让每一段成品都方便查看、剪辑和复用。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update voiceover-narration-studio` 或 `gh skill update voiceover-narration-studio`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt （索引）· https://www.beatra.cn/llms-full.txt （全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
