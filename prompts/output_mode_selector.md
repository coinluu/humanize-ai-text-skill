# output_mode 选择 Prompt

## 用途

根据用户要求和任务复杂度选择最终 `output_mode`。

## 模式

### concise

只输出改写文本。适合用户要求“只给改写版”“直接输出”，且文本低风险。

### standard

默认模式，输出：AI 感诊断、改写策略、真人化改写版、修改说明、风险提示。

### full

详细模式，输出：AI 感诊断、Protected Facts、改写策略、真人化改写版、备用版本、修改说明、事实一致性检查、风险提示、可发布评分。适合复杂、高风险或参考样本任务。

### debug

调试模式，输出完整中间结果：解析输入、内容类型、Protected Facts、安全检查、AI 感诊断、强度决策、平台适配、样本分析、改写结果、事实核对和最终输出。

## 默认规则

未指定输出模式时，选择 `standard`。

## 输出

```yaml
output_mode_selection:
  output_mode: concise|standard|full|debug
  reason: ""
  sections_to_include: []
```
