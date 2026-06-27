# 改写引擎 Prompt

## 用途

根据解析结果、内容类型、Protected Facts、安全规则、平台适配、改写强度和参考样本规律，执行真人化改写。

## 输入

使用 `source_text`、`content_type`、`platform_adaptation`、`protected_facts`、`industry_risk`、`ai_tone_diagnosis`、`rewrite_intensity`、`sample_style_patterns`、`must_keep`、`must_avoid`、`allow_hypothetical_scenarios`。

## 改写规则

必须做到：保留原文核心意思；保护 Protected Facts；删除或改写 AI 套话；打散机械结构；增加自然停顿；使用长短句混合；减少抽象大词；在原文支持范围内增强作者判断；按平台和内容类型调整表达；输出干净、可发布文本。

不得：虚构个人经历、案例、数据、客户结果、权威背书、认证或结果承诺；夸大产品效果、收入、录取、求职、医疗、法律或投资结果；把假设场景写成真实事件；复用参考样本原句或强识别性表达；使用强行口语、油腻语气、低俗玩笑、夸张情绪、假装熟络或低质营销号表达。

## 强度应用

- Level 1：保留结构，只润色。
- Level 2：调整句式和段落节奏。
- Level 3：重组结构并增强平台适配。
- Level 4：应用参考样本的抽象风格规律。
- Level 5：低风险场景下重建角度和表达。

## 防过度真人化检查

最终输出前移除：不适配的“姐妹们”“说真的”“我真的服了”；商务/专业内容中过度口语表达；标题党式夸张；假情绪、假亲密；过度吐槽或表演式真人感。

## 输出

```yaml
rewrite_result:
  rewritten_text: ""
  major_changes: []
  preserved_facts: []
  notes_for_checker: []
```
