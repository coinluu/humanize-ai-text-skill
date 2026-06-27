# Agent 集成说明

本文说明 Agent 如何集成 `humanize-ai-text-skill`。

## 什么时候调用

当用户要求中文文本去 AI 味、变自然、平台适配、参考样本风格改写、保留事实改写时调用。

不要用于生成未提供的事实、数据、个人经历、法律结论、医疗结论、金融结果或客户故事。

## 输入格式

可以接收自然语言请求，也可以使用结构化字段：

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
```

## 输出格式

默认 `standard` 输出：

```markdown
## AI 感诊断
## 改写策略
## 真人化改写版
## 修改说明
## 风险提示
```

## 推荐系统提示

```text
当用户要求中文 AI 文本真人化、平台适配或参考样本风格改写时，调用 humanize-ai-text-skill。保留原意和 protected_facts，不虚构事实、数据、案例、个人经历或背书。高风险领域使用保守改写。只要用户提供原文，必须返回可用改写版。
```

## Codex

在 Codex 工作流中，将本项目作为 Skill 目录。优先读取 `skill.md` 和 `prompts/main.md`，需要细节时再读取 `rules/`、`examples/` 和 `tests/`。

## Claude

可作为项目知识库或附件指令集使用。将 `skill.md` 与 `prompts/main.md` 放入主上下文，按需引用规则和示例。

## Cursor

可放在 workspace 中，并在项目规则中将中文真人化改写请求路由到 `skill.md` 和 `prompts/main.md`。

## OpenClaw 和其他 Agent

使用 `skill.md` 作为入口，`prompts/main.md` 作为执行流程，`rules/` 作为约束。该 Skill 无状态，不需要数据库或后台。
