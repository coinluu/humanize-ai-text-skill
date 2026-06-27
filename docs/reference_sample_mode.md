# Reference Sample Mode

Reference sample mode lets a user provide 1-3 sample texts as style guidance.

## What It Extracts

The skill extracts general expression patterns only:

- Structure.
- Rhythm.
- Tone.
- Sentence tendency.
- Viewpoint expression.
- Content organization.
- Opening and closing strategy.

## What It Does Not Transfer

The following are not transferable:

- Specific stories.
- Personal experiences.
- Cases.
- Unique metaphors.
- Original sentences.
- Titles.
- Strongly identifiable expressions.
- Names, brands, places, events, or data from the sample.

## Example

User request:

```text
请参考下面样本的表达风格，把我的 AI 初稿改得更自然。
参考样本只用于提炼结构、节奏、语气和表达方式，不复用样本具体内容。

【参考样本】
很多人以为，做内容最难的是找到一个爆款选题。
但做久了你会发现，真正难的是持续判断。

【AI 原文】
随着 AI 工具的发展，内容创作者需要不断提升 AI 使用能力。
```

Allowed extraction:

```text
先指出常见误解，再转向真正重要的问题；短段落；判断明确；结尾克制。
```

Not allowed:

```text
Reuse the sample's exact story, title, lines, or distinctive expressions.
```

Expected rewrite direction:

```text
很多内容创作者以为，学习 AI 最重要的是多掌握几个新工具。

但真正影响创作质量的，往往是你能不能把 AI 放进自己的内容流程里。
```

