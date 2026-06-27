# Usage

This guide shows how to call `humanize-ai-text-skill` in normal Agent conversations.

## Basic Humanize

Use `basic_humanize` when you want a general AI-generated draft rewritten into more natural Chinese.

```text
请调用 humanize-ai-text-skill，把下面这段 AI 文本改得更自然、更像真人表达。

【原文】
在当今 AI 快速发展的时代，越来越多企业开始关注 AI 工作流。AI 工作流不仅能够帮助企业提升效率，而且能够优化业务流程，推动企业实现智能化升级。
```

Expected behavior:

- Diagnose AI-like tone.
- Rewrite in natural Chinese.
- Preserve the original meaning.
- Avoid adding facts, cases, or data.
- Use `standard` output mode by default.

## Platform Humanize

Use `platform_humanize` when the target channel matters.

```text
请调用 humanize-ai-text-skill，把下面这段内容改成适合小红书发布的风格。
要求：短段落、真实感、低官方感，不虚构案例。

【原文】
AI 工作流可以帮助个人和团队提升效率，优化重复性工作流程，并更好地管理日常任务。
```

Supported platform directions include:

- Xiaohongshu
- Douyin script
- WeChat article
- Zhihu
- Moments
- Private group
- Sales copy
- Business document
- Generic text

## Sample-Guided Humanize

Use `sample_guided_humanize` when the user provides reference samples.

```text
请调用 humanize-ai-text-skill，参考下面样本的表达风格，把我的 AI 初稿改得更自然。
参考样本只用于提炼结构、节奏、语气和表达方式，不复用样本具体内容。

【参考样本】
很多人以为，做内容最难的是找到一个爆款选题。
但做久了你会发现，真正难的是持续判断。

【AI 原文】
随着 AI 工具的发展，内容创作者需要不断提升 AI 使用能力，以便提升内容生产效率并实现长期发展。
```

Expected behavior:

- Analyze the reference sample.
- Extract general style patterns.
- Rewrite from the user's source text.
- Do not reuse sample-specific stories, lines, titles, or identifiable expressions.

## Output Modes

If no output mode is specified, the skill uses `standard`.

Use:

- `concise` for rewritten text only.
- `standard` for diagnosis, strategy, rewrite, notes, and risk note.
- `full` for detailed review, alternate version, and publish-readiness score.
- `debug` for complete intermediate analysis.

