# YuE2 AI 音乐提示词

从 YuE2 官方演示和模型卡整理的文生曲提示词。每首需要两段文字：

- `style`：曲风、乐器、人声、情绪、速度
- `lyrics`：要唱的词，用 `[Verse]`、`[Chorus]` 这类段落标签分段

WaveSpeed `wavespeed-ai/yue2-3b/text-to-music` 提交时使用这两个字段，可选再加 `seed`。

## 来源

| 来源 | 内容 |
| --- | --- |
| [YuE2 官方演示](https://map-yue2.github.io/) | 99 首 Genre Explorer 原创曲的风格和歌词，以及 11 条翻唱的风格 |
| [m-a-p/YuE2-3B](https://huggingface.co/m-a-p/YuE2-3B) | 模型卡示例。其中「今晚不眠」「Cyber Metal」已并入上面的 99 首，并补上了官方 seed；「Passion」只有风格和 seed，歌词没有公开 |

上游模型与官方示例的许可是 **CC BY-NC 4.0**。本仓库是带出处的编目，不主张这些歌词的著作权。非商业使用时请保留出处。

翻唱里《春天在哪里》《小苹果》《学猫叫》《贝加尔湖畔》《最炫民族风》的原词没有收录，只保留风格提示词。《Jingle Bells》和《Auld Lang Syne》是传统公共领域歌词，按官方演示原文收录。

## 怎么用

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

## 目录

- `prompts/genre/`：99 首原创曲
- `prompts/covers/`：11 条翻唱风格
- `prompts/official/passion.json`：模型卡补充，没有歌词
- `prompts/catalog.json`：上面全部内容的一份汇总
