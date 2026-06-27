# Integration

This document explains how agents can integrate `humanize-ai-text-skill`.

## When to Call

Call this skill when the user asks to:

- Make AI-generated Chinese text more natural.
- Reduce stiff, template-like, official, or generic tone.
- Rewrite for Xiaohongshu, Douyin, WeChat, Zhihu, Moments, sales copy, or business documents.
- Use reference samples for style guidance.
- Preserve facts while improving readability.

Do not call it for tasks that require generating unsupported facts, data, personal experiences, legal conclusions, medical claims, financial results, or customer stories.

## Input Format

Agents may pass free-form user requests. Recommended structured fields:

```yaml
mode: basic_humanize | platform_humanize | sample_guided_humanize
platform: xiaohongshu | douyin_script | wechat_article | zhihu | moments | private_group | sales_copy | business_doc | generic_text
content_type: article | social_note | short_video_script | sales_copy | title | caption | comment_reply | private_message | email | resume | business_doc | knowledge_explanation | generic_text
output_mode: concise | standard | full | debug
rewrite_intensity: auto | 1 | 2 | 3 | 4 | 5
source_text: |
  ...
reference_sample: |
  ...
requirements:
  - preserve facts
  - do not add cases
```

## Output Format

Default `standard` output:

```markdown
## AI 感诊断

## 改写策略

## 真人化改写版

## 修改说明

## 风险提示
```

## Recommended System Prompt

```text
When the user asks to humanize AI-generated Chinese text, adapt content to a platform, or rewrite based on a reference sample, call humanize-ai-text-skill. Preserve source meaning and protected facts. Do not fabricate facts, data, cases, personal experiences, or endorsements. Use conservative rewriting for high-risk domains. Unless source text is missing, always return a usable rewritten version.
```

## Codex

In Codex-style workflows, keep the skill as a project directory and instruct the agent to read `skill.md`, then use `prompts/main.md` as the controller. Load detailed prompt and rule files only when needed.

## Claude

Use the skill as a project knowledge folder or attached instruction set. Put `skill.md` and `prompts/main.md` in primary context, then reference `rules/` and `examples/` as needed.

## Cursor

Store the project in the workspace. Add a project rule that routes humanization requests to `skill.md` and `prompts/main.md`. Use `tests/` for manual verification after prompt edits.

## OpenClaw and Other Agents

Use `skill.md` as the entrypoint, `prompts/main.md` as the execution graph, and `rules/` as policy constraints. The skill is stateless and does not require a database or backend.

