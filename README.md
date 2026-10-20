# AI Voiceover Generator Skill

English | [简体中文](./README.zh-CN.md) | [日本語](./README.ja.md)

> 👉 See also [AI Voice Cloning Skill](https://github.com/beatra-ai/ai-voice-cloning-skill)

Pick or reuse a voice, turn scripts into narration ready for editing, plan ordered long-form or multilingual audio, and create a reusable custom voice, from inside Claude Code, Cursor, Codex, Windsurf, Cline, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Choose or reuse a voice, turn scripts into ready-to-edit narration, plan ordered long-form or multilingual audio, and create a reusable custom voice. |
| **Models** | MiniMax Voice Clone, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="A narration studio cover with a microphone and three colored waveforms, one for each voice in the sample. AI-generated with Beatra."></p>

*A narration studio cover with a microphone and three colored waveforms, one for each voice in the sample. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`voiceover-narration-studio`](skills/voiceover-narration-studio) | [SKILL.md](skills/voiceover-narration-studio/SKILL.md) | 0.2.8 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/voiceover-narration-studio). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-voiceover-generator-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-voiceover-generator-skill voiceover-narration-studio
```

Or clone this repository and copy `skills/voiceover-narration-studio` into `~/.claude/skills/` for Claude Code,
`~/.cursor/skills/` for Cursor, `~/.agents/skills/` for Codex, `~/.codeium/windsurf/skills/` for Windsurf,
`~/.cline/skills/` for Cline, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the voiceover-narration-studio skill from https://github.com/beatra-ai/ai-voiceover-generator-skill (folder skills/voiceover-narration-studio), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/cover.webp" width="800" alt="A narration studio cover with a microphone and three colored waveforms, one for each voice in the sample. AI-generated with Beatra."></p>

[▶ Listen (MP3)](assets/sample.mp3)

*Three short reads in three preset voices, in order: a calm product explainer, an upbeat short-video ad, and a documentary line, 41 seconds in total. AI-generated with Beatra.*

Ask your agent:

```text
Read these three short scripts in three different preset voices: a calm product explainer for the Tidewell desk lamp, an upbeat short-video ad for Crunchlane chips, and one documentary line. Deliver the three reads in that order.
```

Prompt:

```text
Meet Tidewell, a desk lamp that follows your day. In the morning, it glows cool and bright for focus. After sunset, it turns warmer, so your eyes can rest.

Okay, stop scrolling! Crunchlane spicy mango chips are here: sweet, hot, and seriously crunchy. Grab a bag this Saturday, and tell us how fast it disappeared!

High in the northern mountains, the first snow falls without a sound. A red fox stops and listens. Something small is moving beneath the snow. She waits. Then she leaps.
```

## Technical Specifications & Output Limits

As of 2026-10-18. Live list: https://docs.beatra.ai/en/docs/models

- **Uploads** — up to 100 MB per file; the per-model input limits below also apply
- **Voice cloning** — 1 model (MiniMax Voice Clone); sample 10–300 s, up to 20 MB; consent attestation required
- **Text to speech** — 2 models (MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo); FLAC, MP3, OPUS, PCM, WAV; 40 languages; sample rates 8, 16, 22.05, 24, 32, 44.1 kHz; up to 50000 characters per request
  - Languages (ISO 639 codes): zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af

## Why use Beatra instead of calling model APIs directly

- **One account for every model this skill uses** — Voice cloning 1; Text to speech 2 (MiniMax Voice Clone, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo) (as of 2026-10-18), behind one Beatra sign-in; no keys from individual model providers to manage.
- **You decide what gets paid for** — Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate.
- **Direction before rendering** — the skill plans, directs, and reviews the work, then renders it on Beatra.
- **Files you can verify** — every file under `skills/` matches the release archive on cdn.beatra.ai byte for byte, checked by SHA-256 before each push.
- **Updates you control** — no self-updater; update with the tool you installed it with.
- **Runs in your agent** — Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw.

## How it compares

| | Beatra (this skill) | [scenario-labs/skills](https://github.com/scenario-labs/skills) | [vargHQ/skills](https://github.com/vargHQ/skills) |
| --- | --- | --- | --- |
| Account or key needed | A Beatra account; no model provider keys | A Scenario account (OAuth) or a Scenario API key ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L105)) | A VARG_API_KEY, required for all skills ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L70)) |
| Models | Voice cloning 1; Text to speech 2 (MiniMax Voice Clone, MiniMax Speech 2.8 HD, MiniMax Speech 2.8 Turbo) | Voice and speech generation through its scenario-audio skill ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L175)) | Kling, Flux, ElevenLabs, Sora and more through the varg platform ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L3)) |
| Before spending | Paid renders run only when you ask for that exact render or approve its card, which shows the live credit estimate | Dry-run price estimates in its quality-gate and model-comparison skills ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L208-L210)) | A free `--preview` render before the full render ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L158-L160)) |
| Agents | Claude Code, Cursor, Codex, Windsurf, Cline, OpenClaw | Claude Code, Cursor, Codex, Copilot and 70+ others ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L30)) | Claude Code, Cursor, Windsurf, OpenCode, ClawHub and any Agent Skills tool ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L10)) |
| Install | `npx skills add beatra-ai/ai-voiceover-generator-skill` | `npx skills add scenario-labs/skills`, then connect the Scenario MCP server (https://mcp.scenario.com/mcp) ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/README.md#L89-L105)) | `npx skills add vargHQ/skills` ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/README.md#L59)) |
| License | MIT-0 | MIT ([source](https://github.com/scenario-labs/skills/blob/49dd26e47371163ae0020c7f5627d0993626bfc2/LICENSE)) | MIT ([source](https://github.com/vargHQ/skills/blob/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d/LICENSE)) |
| Last updated | Updated with every release (v0.2.8) | 2026-10-15 ([source](https://github.com/scenario-labs/skills/commit/49dd26e47371163ae0020c7f5627d0993626bfc2)) | 2026-10-01 ([source](https://github.com/vargHQ/skills/commit/862c0297ba2063b10eeb5d4d1058b0f90dc9f92d)) |

Facts checked on 2026-10-16. Corrections: open an issue in [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/issues).

## What you get

- **Choose the right route first** — Start with a single voiceover, ordered long-form work, supplied multilingual scripts, or a reusable custom voice and keep each route easy to follow.
- **Use a current voice** — Compare only voices that fit the language and use, and keep a selected voice consistent across continuing content.
- **Keep long-form audio organized** — Arrange chapters, lessons, languages, and recurring reads in a clear sequence so every delivered audio item is easy to find and edit.

## Use cases

- **Short-video voiceover** — Turn a script into one ready-to-edit read with a voice and pace chosen for the audience.
- **Audiobooks and course narration** — Pilot a supplied passage, then keep chapters or lessons ordered with one accepted narrator.
- **Supplied multilingual scripts** — Choose a suitable voice for each prepared language version and keep the resulting audio grouped by language and section.
- **A reusable brand voice** — Create a named custom voice from a clean sample, then choose it again for later narration.

## FAQ

### What can I make in the Voice Studio?

You can make a single voiceover, ordered audiobook or course narration, audio from supplied multilingual scripts, or a reusable custom voice for later narration.

### How many languages are available?

Current live speech models cover 40 languages, including Mandarin Chinese and Cantonese. Each production still checks both the selected current voice and the speech model for the requested language.

### Can I use my own voice?

Yes. Use a clean single-speaker sample to create a named custom voice, then select it again for later narration, courses, updates, and recurring brand content.

### How are long-form and multilingual projects organized?

Audio is arranged by chapter, lesson, language, market, or recurring use case, making each delivered item easy to review, edit, and reuse.

## Updates and security

Since the 2026-10 release, this skill contains no self-updater: it runs only the
files you installed and never replaces them on its own. Update it with the tool
you installed it with — `npx skills update voiceover-narration-studio` or `gh skill update voiceover-narration-studio`.
Details: `references/updates-and-security.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.

## Links

- Website — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill
- Docs — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-voiceover-generator-skill
- Console — https://console.beatra.ai
- For AI agents — https://beatra.ai/llms.txt (index) · https://beatra.ai/llms-full.txt (every skill in one file)
