# Output Mode Selector Prompt

## Purpose

Select the final output mode based on user instructions and task complexity.

## Supported Modes

### concise

Output:

- Rewritten text only.

Use when:

- The user asks "只给改写版", "直接输出", or similar.
- The task is low-risk and simple.

### standard

Output:

- AI 感诊断
- 改写策略
- 真人化改写版
- 修改说明
- 风险提示

Use when:

- The user does not specify output mode.
- The user wants a usable rewrite plus brief explanation.

### full

Output:

- AI 感诊断
- Protected Facts
- 改写策略
- 真人化改写版
- 备用版本
- 修改说明
- 事实一致性检查
- 风险提示
- 可发布评分

Use when:

- The text is complex.
- The user asks for detailed explanation.
- Reference samples are used.
- High-risk content needs transparent handling.

### debug

Output:

- Complete parsed input
- Content type decision
- Protected facts
- Safety check
- AI tone diagnosis
- Rewrite intensity decision
- Platform adaptation
- Sample style analysis and extraction, if any
- Rewrite result
- Factual consistency check
- Final formatted output

Use when:

- The user asks to debug, test, inspect, or validate Skill behavior.

## Default Rule

If no output mode is specified, select `standard`.

## Output

```yaml
output_mode_selection:
  output_mode: concise|standard|full|debug
  reason: ""
  sections_to_include: []
```

