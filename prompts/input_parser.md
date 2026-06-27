# 输入解析 Prompt

## 用途

把用户请求解析成结构化字段，供后续模块使用。

## 需要识别

- `source_text`：待改写原文。
- `mode`：`basic_humanize`、`platform_humanize` 或 `sample_guided_humanize`。
- `platform`：目标平台或沟通场景。
- `content_type`：用户指定或自动推断的内容类型。
- `target_reader`：目标读者。
- `author_identity`：作者身份或口吻。
- `reference_sample`：参考样本。
- `rewrite_intensity`：Level 1-5 或 `auto`。
- `output_mode`：`concise`、`standard`、`full`、`debug`。
- `allow_hypothetical_scenarios`：是否允许明确标识的假设场景。
- `must_keep`：必须保留内容。
- `must_avoid`：必须避免内容。
- `language`：默认中文。

## 推断规则

- 用户说“去 AI 味”“自然一点”“像真人写”：`mode: basic_humanize`。
- 用户指定平台：`mode: platform_humanize`。
- 用户提供参考样本：`mode: sample_guided_humanize`。
- 多个模式同时出现时，优先级：sample-guided > platform > basic。
- 未指定内容类型时，自动推断。
- 未指定输出模式时，使用 `standard`。
- 未明确允许假设场景时，设为 `false`。

## 追问规则

不要频繁追问。只有以下情况才问：缺少原文；用户要求添加未提供的事实、案例、数据或经历；高风险内容无法保守处理。

## 输出

```yaml
parsed_input:
  source_text: ""
  mode: ""
  platform: ""
  content_type: ""
  target_reader: ""
  author_identity: ""
  reference_sample: ""
  rewrite_intensity: auto
  output_mode: standard
  allow_hypothetical_scenarios: false
  must_keep: []
  must_avoid: []
  language: zh
  assumptions: []
  clarification_needed: false
  clarification_question: ""
```
