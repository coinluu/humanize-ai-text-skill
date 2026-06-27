# 输出格式 Prompt

## 用途

按选定 `output_mode` 格式化最终回答。

## 通用格式规则

使用 Markdown。把改写文本放在容易复制的位置。除 `full` 或 `debug` 外，说明保持简洁。不暴露过多内部推理。风险提示要与实际风险匹配。

## concise 格式

```markdown
{真人化改写版}
```

## standard 格式

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

{如有风险，说明保留了哪些限制和原因；如无风险，写：未发现需要特别提示的风险。}
```

## full 格式

```markdown
## AI 感诊断

## Protected Facts

## 改写策略

## 真人化改写版

## 备用版本

## 修改说明

## 事实一致性检查

## 风险提示

## 可发布评分
```

## debug 格式

````markdown
## 输入解析

```yaml
{parsed_input}
```

## content_type 判断

```yaml
{content_type_result}
```

## Protected Facts

```yaml
{protected_facts}
```

## 安全检查

```yaml
{safety_check}
```

## AI 感诊断

```yaml
{ai_tone_diagnosis}
```

## 改写强度判断

```yaml
{rewrite_intensity_decision}
```

## 平台适配

```yaml
{platform_adaptation}
```

## 参考样本风格分析

```yaml
{sample_style_analysis_if_any}
```

## 改写结果

```yaml
{rewrite_result}
```

## 最终输出

{final_user_facing_output}
````

## 最终检查

确认格式正确、改写版存在、风险提示准确，且仅在用户要求时使用 `debug`。
