# Output Format Prompt

## Purpose

Format the final response according to the selected output mode.

## General Formatting Rules

- Use Markdown.
- Put the rewritten text where the user can easily copy it.
- Keep notes concise unless `full` or `debug` is selected.
- Do not expose excessive internal reasoning.
- Include risk notes only when relevant, except in `standard`, where the risk section may say no special risk was found.

## concise Format

```markdown
{真人化改写版}
```

Use no headings unless needed for multi-version output.

## standard Format

```markdown
## AI 感诊断

- {主要问题 1}
- {主要问题 2}
- {主要问题 3}

## 改写策略

- {策略 1}
- {策略 2}
- {策略 3}

## 真人化改写版

{最终改写文本}

## 修改说明

- {说明 1}
- {说明 2}
- {说明 3}

## 风险提示

{如有风险，说明保留了哪些限制和为什么；如无风险，写：未发现需要特别提示的风险。}
```

Requirements:

- Diagnosis should be 3-6 bullets.
- Strategy should directly match the diagnosis.
- Rewrite must be the main deliverable.
- Risk warning must not be alarmist.

## full Format

```markdown
## AI 感诊断

- {主要问题}

## Protected Facts

- {必须保留的事实}

## 改写策略

- {策略}

## 真人化改写版

{最终改写文本}

## 备用版本

{另一种可用版本；如不适合提供，写：本次不提供备用版本，避免引入不必要的表达漂移。}

## 修改说明

- {具体修改说明}

## 事实一致性检查

- {数字、名称、日期、结论、限定词是否保留}

## 风险提示

{风险或无风险说明}

## 可发布评分

{1-10 分} / 10

理由：{一句话说明评分依据}
```

## debug Format

````markdown
## Parsed Input

```yaml
{parsed_input}
```

## Content Type Decision

```yaml
{content_type_result}
```

## Protected Facts

```yaml
{protected_facts}
```

## Safety Check

```yaml
{safety_check}
```

## AI Tone Diagnosis

```yaml
{ai_tone_diagnosis}
```

## Rewrite Intensity Decision

```yaml
{rewrite_intensity_decision}
```

## Platform Adaptation

```yaml
{platform_adaptation}
```

## Sample Style Analysis

```yaml
{sample_style_analysis_if_any}
```

## Sample Style Patterns

```yaml
{sample_style_patterns_if_any}
```

## Rewrite Result

```yaml
{rewrite_result}
```

## Factual Consistency Check

```yaml
{factual_consistency_check}
```

## Final Output

{final_user_facing_output}
````

## Final Check

Before returning, confirm:

- The selected format is followed.
- The rewritten version is present.
- Risk notes match the actual risk level.
- Debug output is only used when requested.
