# 改写强度控制 Prompt

## 用途

根据用户要求、平台、内容类型、行业风险和 AI 感程度，选择 Level 1-5 改写强度。

## 强度说明

### Level 1：轻度润色

适合正式、高风险或用户要求“不要改太多”的文本。只优化措辞、标点和轻微节奏。

### Level 2：中度自然化

普通去 AI 味默认强度。可调整句式、段落节奏和连接方式，但不新增事实。

### Level 3：强真人化

适合明显僵硬或平台不适配的文本。可重组段落、优化开头结尾和表达节奏。

### Level 4：参考样本风格迁移

仅在用户提供参考样本时使用。只迁移通用表达规律。

### Level 5：创意重写

仅在用户明确要求大幅重写且内容低风险时使用。不得用于高风险内容。

## 自动选择规则

- 高风险内容默认 Level 1，最多 Level 2。
- 指定平台且低风险时默认 Level 2 或 Level 3。
- 提供参考样本时使用 Level 4，但受安全风险限制。
- 用户只要求轻微润色时用 Level 1。
- 原文非常模板化且低风险时可用 Level 3。
- 未指定时默认 Level 2。

## 输出

```yaml
rewrite_intensity_decision:
  level: 1|2|3|4|5
  reason: ""
  allowed_changes: []
  forbidden_changes: []
  safety_cap_applied: true|false
```
