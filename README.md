# YuE2 AI 音乐提示词 / YuE2 AI Music Prompts

[中文](#中文) · [English](#english)

在 **[yue2ai.org](https://yue2ai.org)** 用这些提示词直接生成歌曲。  
Turn these prompts into songs at **[yue2ai.org](https://yue2ai.org)**.

## 中文

在 **[yue2ai.org](https://yue2ai.org)** 填上风格和歌词，即可生成歌曲。

这些文生曲提示词整理自 YuE2 官方演示和模型卡。每首需要两段文字：

- `style`：曲风、乐器、人声、情绪、速度
- `lyrics`：要唱的词，用 `[Verse]`、`[Chorus]` 这类段落标签分段

WaveSpeed `wavespeed-ai/yue2-3b/text-to-music` 提交时使用这两个字段，可选再加 `seed`。

### 来源

| 来源 | 内容 |
| --- | --- |
| [YuE2 官方演示](https://map-yue2.github.io/) | 99 首 Genre Explorer 原创曲的风格和歌词，以及 11 条翻唱的风格 |
| [m-a-p/YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | 模型卡示例。其中「今晚不眠」「Cyber Metal」已并入上面的 99 首，并补上了官方 seed；「Passion」只有风格和 seed，歌词没有公开 |

上游模型与官方示例的许可是 **CC BY-NC 4.0**。本仓库是带出处的编目，不主张这些歌词的著作权。非商业使用时请保留出处。

翻唱里《春天在哪里》《小苹果》《学猫叫》《贝加尔湖畔》《最炫民族风》的原词没有收录，只保留风格提示词。《Jingle Bells》和《Auld Lang Syne》是传统公共领域歌词，按官方演示原文收录。

### 怎么用

打开 [`prompts/index.md`](prompts/index.md) 按曲风浏览，或直接读 [`prompts/catalog.json`](prompts/catalog.json)。

单首文件形如：

```json
{
  "style": "City Pop, upbeat, danceable, groovy bass, electric guitar, synth, energetic, joyful, neon city night",
  "lyrics": "[Verse]\n路灯眨着眼睛 偷看谁的身影\n...",
  "cot": "full",
  "seed": 12300
}
```

`cot` 来自官方演示的生成方式：

| `cot` | 官方演示里的 mode | 含义 |
| --- | --- | --- |
| `full` | planned | 先写旋律和和弦，再生成整曲。默认用这个 |
| `off` | direct | 不写符号谱，直接生成 |

段落标签在官方示例里不统一，常见的有 `[Intro]`、`[Verse]`、`[Verse 1]`、`[Pre-Chorus]`、`[Chorus]`、`[Bridge]`、`[Interlude]`、`[Outro]`。风格描述可以是一串标签，也可以是一整段编曲说明。速度、乐器和人声是偏好，不是精确控制。

### 目录

- `prompts/genre/`：99 首原创曲
- `prompts/covers/`：11 条翻唱风格
- `prompts/official/passion.json`：模型卡补充，没有歌词
- `prompts/catalog.json`：上面全部内容的一份汇总

## English

Generate a song at **[yue2ai.org](https://yue2ai.org)** by filling in a style and lyrics.

These text-to-music prompts are collected from the official YuE2 demo and model card. Each song needs two texts:

- `style`: genre, instruments, vocal character, mood, and tempo
- `lyrics`: the words to sing, split with section tags such as `[Verse]` and `[Chorus]`

WaveSpeed `wavespeed-ai/yue2-3b/text-to-music` takes those two fields, plus an optional `seed`.

### Sources

| Source | What is included |
| --- | --- |
| [YuE2 demo](https://map-yue2.github.io/) | Style and lyrics for 99 original Genre Explorer songs, plus style prompts for 11 covers |
| [m-a-p/YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | Model-card examples. 「今晚不眠」 and 「Cyber Metal」 are already in the 99 songs above, with the official seeds added. Passion publishes only a style and a seed; its lyrics were not released |

The upstream model and official examples are licensed **CC BY-NC 4.0**. This repository is an attributed catalog and does not claim copyright in the lyrics. Keep the attribution for non-commercial use.

Lyrics were omitted for the copyrighted covers 《春天在哪里》, 《小苹果》, 《学猫叫》, 《贝加尔湖畔》, and 《最炫民族风》. Only the style prompts for those tracks are kept. *Jingle Bells* and *Auld Lang Syne* are traditional public-domain lyrics and are included as published in the official demo.

### How to use

Browse by genre in [`prompts/index.md`](prompts/index.md), or read [`prompts/catalog.json`](prompts/catalog.json).

A single prompt looks like this:

```json
{
  "style": "City Pop, upbeat, danceable, groovy bass, electric guitar, synth, energetic, joyful, neon city night",
  "lyrics": "[Verse]\n路灯眨着眼睛 偷看谁的身影\n...",
  "cot": "full",
  "seed": 12300
}
```

`cot` follows the official demo's generation mode:

| `cot` | Demo mode | Meaning |
| --- | --- | --- |
| `full` | planned | Plan melody and chords, then generate the full song. Use this by default |
| `off` | direct | Generate without a symbolic score |

Section tags are not consistent across the official examples. Common ones are `[Intro]`, `[Verse]`, `[Verse 1]`, `[Pre-Chorus]`, `[Chorus]`, `[Bridge]`, `[Interlude]`, and `[Outro]`. A style can be a short tag list or a full arrangement note. Tempo, instruments, and vocals are preferences, not exact controls.

### Layout

- `prompts/genre/`: 99 original songs
- `prompts/covers/`: 11 cover styles
- `prompts/official/passion.json`: model-card extra, lyrics not published
- `prompts/catalog.json`: one file with everything above
