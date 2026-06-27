[中文文档](./README.md)

# Humanize AI Text Skill

An agent-ready skill for rewriting AI-generated Chinese text into natural, human-like, platform-ready content.

一个 Agent 可调用的 AI 初稿真人化编辑 Skill。

![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Status: v1.0.0](https://img.shields.io/badge/Status-v1.0.0-blue.svg)
![Agent Ready](https://img.shields.io/badge/Agent-Ready-purple.svg)
![Language: Chinese](https://img.shields.io/badge/Language-Chinese-red.svg)
![No Database Required](https://img.shields.io/badge/No%20Database-Required-lightgrey.svg)

## Hero Value Proposition

`humanize-ai-text-skill` is an Agent Skill, not a SaaS product.

It helps agents turn AI-generated Chinese drafts into more natural, credible, and platform-ready content for Xiaohongshu, Douyin scripts, WeChat articles, Moments, sales copy, business documents, and more.

It preserves meaning and protected facts, avoids fabricated cases or data, and keeps high-risk content accurate and restrained.

## Before / After

### Before

```text
在当今 AI 快速发展的时代，越来越多企业开始关注 AI 工作流。AI 工作流不仅能够帮助企业提升效率，而且能够优化业务流程，推动企业实现智能化升级。因此，企业应该积极拥抱 AI 工作流，以便在未来竞争中获得更大的发展空间。
```

### After

```text
企业开始关注 AI 工作流，通常不是因为它听起来新，而是因为很多重复工作确实需要被重新处理。

比如信息整理、内容初稿、客户问题归类、内部流程提醒，这些环节如果一直靠人工来回确认，很容易耗时间。AI 工作流的价值，是把这些固定动作先串起来，让人把精力放到判断、沟通和决策上。

所以它不是一个简单的“智能化升级”口号，更像是一种重新整理工作方式的工具。用得好，效率会更稳；用不好，也只是多了一套复杂流程。
```

## Quick Start

```text
请调用 humanize-ai-text-skill，把下面这段 AI 文本改得更自然，更像真人表达，适合小红书发布。

【原文】
AI 工作流可以帮助个人和团队提升效率，优化重复性工作流程，并更好地管理日常任务。
```

## What It Does

- AI tone diagnosis
- Human-like rewriting
- Platform adaptation
- Content type routing
- Protected facts preservation
- Reference sample style extraction
- Safety checks
- Anti-overhumanization
- Multiple output modes

## Supported Modes

| Mode | Use case |
| --- | --- |
| `basic_humanize` | General AI-tone reduction and natural rewriting |
| `platform_humanize` | Platform-aware rewriting for specific channels |
| `sample_guided_humanize` | Style-guided rewriting using reference samples |

## Supported Platforms

| Platform | Rewrite goal |
| --- | --- |
| Xiaohongshu | Short paragraphs, practical tone, real-feeling but not fabricated |
| Douyin script | Spoken rhythm, short sentences, strong opening hook |
| WeChat article | Clear viewpoint, logical flow, readable structure |
| Zhihu | Reasoned answer, clear judgment, factual boundaries |
| Moments | Natural, concise, low-pressure sharing |
| Private group | Useful, friendly, action-oriented group message |
| Sales copy | Credible persuasion without exaggerated claims |
| Business document | Professional, restrained, decision-friendly language |
| Generic text | Natural rewriting without platform-specific styling |

## Supported Content Types

| Content type | Description |
| --- | --- |
| `article` | Long-form article, essay, newsletter, official account post |
| `social_note` | Xiaohongshu-style note or social platform post |
| `short_video_script` | Douyin, short video, livestream, or oral script |
| `sales_copy` | Product, service, offer, course, or consultation copy |
| `title` | Headline, subject line, article title, video title |
| `caption` | Image, video, product, or social post caption |
| `comment_reply` | Comment, review, objection, or public reply |
| `private_message` | DM, private group message, outreach, follow-up |
| `email` | Work or business email |
| `resume` | Resume bullet, profile summary, project experience |
| `business_doc` | Report, proposal, memo, plan, SOP |
| `knowledge_explanation` | Educational or explanatory content |
| `generic_text` | General text that does not fit another category |

## How It Works

```text
Input
  ↓
Parse
  ↓
Protected Facts
  ↓
AI Tone Diagnosis
  ↓
Rewrite Intensity
  ↓
Platform Adaptation
  ↓
Rewrite
  ↓
Fact Check
  ↓
Output
```

## Output Example

Default `standard` mode returns:

```markdown
## AI 感诊断

- 开头偏宏大，缺少具体问题。
- “不仅……而且……”结构模板化。
- “提升效率”“智能化升级”偏抽象。

## 改写策略

- 从具体工作场景切入。
- 保留原意，但减少口号化表达。
- 用长短句混合增强自然节奏。

## 真人化改写版

企业开始关注 AI 工作流，通常不是因为它听起来新，而是因为很多重复工作确实需要被重新处理。

## 修改说明

- 删除宏大背景开头。
- 将抽象表达改成更具体的工作动作。
- 保留 AI 工作流、效率和流程优化的核心意思。

## 风险提示

未发现需要特别提示的风险。
```

## Reference Sample Mode

Users may provide 1-3 reference samples.

The skill extracts only general expression patterns, such as:

- Structure
- Rhythm
- Tone
- Sentence tendency
- Viewpoint expression
- Content organization

The following reference-sample elements are not transferable:

- Specific stories
- Personal experiences
- Cases
- Unique metaphors
- Original sentences
- Titles
- Strongly identifiable expressions

The final rewrite must be based on the user's original text, not on concrete content from the reference samples.

## Safety Principles

- Not designed to bypass AI detectors
- Does not fabricate facts
- Does not invent cases, data, personal experiences, or endorsements
- Preserves numbers, dates, names, prices, and key claims
- High-risk domains use conservative rewriting
- Avoids overly emotional or low-quality rewriting

## Project Structure

```text
humanize-ai-text-skill/
├── README.md
├── skill.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── SECURITY.md
├── CODE_OF_CONDUCT.md
├── prompts/
│   ├── main.md
│   ├── input_parser.md
│   ├── content_type_router.md
│   ├── protected_facts_extractor.md
│   ├── ai_tone_diagnosis.md
│   ├── rewrite_intensity_controller.md
│   ├── platform_adaptation.md
│   ├── sample_style_analysis.md
│   ├── sample_style_extraction.md
│   ├── rewrite_engine.md
│   ├── safety_check.md
│   ├── factual_consistency_check.md
│   ├── output_mode_selector.md
│   └── output_format.md
├── rules/
│   ├── ai_phrase_blacklist.md
│   ├── ai_structure_blacklist.md
│   ├── human_style_rules.md
│   ├── anti_overhumanize_rules.md
│   ├── platform_rules.md
│   ├── content_type_rules.md
│   ├── industry_safety_rules.md
│   ├── no_fabrication_rules.md
│   ├── protected_facts_rules.md
│   └── sample_style_rules.md
├── examples/
├── tests/
└── .github/
```

## Examples

- [Basic humanize](examples/basic_humanize_example.md)
- [Xiaohongshu](examples/xiaohongshu_example.md)
- [Douyin script](examples/douyin_script_example.md)
- [WeChat article](examples/wechat_article_example.md)
- [Moments](examples/moments_example.md)
- [Sales copy](examples/sales_copy_example.md)
- [Business document](examples/business_doc_example.md)
- [Sample guided](examples/sample_guided_example.md)
- [Protected facts](examples/protected_facts_example.md)
- [Anti-overhumanize](examples/anti_overhumanize_example.md)
- [Usage examples](examples/usage_examples.md)

## Tests

The `tests/` directory covers:

- basic
- platform
- content type
- sample guided
- safety
- protected facts
- no fabrication
- anti-overhumanize

## Roadmap

- More platform style rules
- More industry safety rules
- English support
- More before/after examples
- Evaluation benchmark
- Agent integration examples

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening an issue or pull request.

## License

MIT License. See [LICENSE](LICENSE).

## Citation

If you use this skill in your agent workflow, please cite:

```text
Humanize AI Text Skill. An agent-ready skill for rewriting AI-generated Chinese text into natural, human-like, platform-ready content.
```
