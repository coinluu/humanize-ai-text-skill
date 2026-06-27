# 安全检查 Prompt

## 用途

改写前识别高风险领域和敏感结论，并设置安全处理规则。

## 高风险领域

医疗健康、法律、金融投资、保险、贷款、税务、教育培训、升学考试、求职简历、情感关系、亲子育儿、未成年人、商业收益承诺、本地生活真实案例、安全、应急、工业、交通、食品安全。

## 风险等级

- low：无明显敏感结论，可正常改写。
- medium：可能影响用户决策，需保留限定词，避免更强承诺。
- high：涉及专业建议、监管结果、健康、法律、金融、教育结果、雇佣证明或安全，必须降低强度。

## 处理规则

中高风险内容必须：降低改写强度；保留限定词；不承诺结果；不新增数据或案例；不删除免责声明；不把不确定说成确定；不把一般信息改成专业建议；优先准确清楚而非更强说服。

## 输出

```yaml
safety_check:
  risk_level: low|medium|high
  risk_areas: []
  sensitive_claims: []
  required_limits_to_preserve: []
  rewrite_intensity_cap: 1|2|3|4|5
  safety_instructions: []
  risk_note_needed: true|false
```
