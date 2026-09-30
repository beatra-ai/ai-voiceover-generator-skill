# AI Voiceover Generator Skill

[English](./README.md) | 简体中文

从同一个入口选声音、把文稿做成可剪辑的配音、安排长篇或多语言音频，并创建可复用的品牌音色，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 从同一个入口选声音、把文稿做成可剪辑配音、安排长篇或多语言音频，并创建可复用的品牌音色。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。"></p>

*配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`voiceover-narration-studio`](skills/voiceover-narration-studio) | [SKILL.md](skills/voiceover-narration-studio/SKILL.md) | 0.2.2 |

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

也可以克隆本仓库，把 `skills/voiceover-narration-studio` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-voiceover-generator-skill 安装 voiceover-narration-studio skill（目录 skills/voiceover-narration-studio），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="配音样片封面：一支麦克风和三条不同颜色的声波，分别对应样片里的三种声音。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*用三个预设声音依次朗读三段短文案：平静的产品讲解、轻快的短视频广告和纪录片旁白，共 41 秒。由 Beatra AI 生成。*

提示词：

```text
Meet Tidewell, a desk lamp that follows your day. In the morning, it glows cool and bright for focus. After sunset, it turns warmer, so your eyes can rest.

Okay, stop scrolling! Crunchlane spicy mango chips are here: sweet, hot, and seriously crunchy. Grab a bag this Saturday, and tell us how fast it disappeared!

High in the northern mountains, the first snow falls without a sound. A red fox stops and listens. Something small is moving beneath the snow. She waits. Then she leaps.
```

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

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
