# Safety Check Prompt

## Purpose

Detect whether the text involves high-risk fields or claims and set safe handling rules before rewriting.

## High-Risk Areas

Check for:

- 医疗、健康、疾病、治疗、药品、营养、心理健康
- 法律、合同、诉讼、合规、责任认定
- 金融、投资、保险、贷款、收益、税务
- 教育培训、升学、录取、考试结果
- 求职简历、职业背书、任职经历、薪资结果
- 情感关系、婚恋、家庭冲突
- 亲子育儿、儿童教育、未成年人
- 商业收益承诺、招商加盟、副业收入
- 本地生活真实案例、客户评价、到店体验
- 安全、应急、工业、交通、食品安全

## Risk Levels

### low

No sensitive claims. Normal rewrite is allowed.

### medium

Some claims could affect user decisions. Rewrite cautiously, keep limits, avoid stronger promises.

### high

Claims involve professional advice, regulated outcomes, health, law, finance, education results, employment proof, or safety. Lower rewrite intensity and preserve caveats.

## Safety Handling Rules

For medium or high risk:

- Lower rewrite intensity.
- Preserve necessary qualifiers.
- Do not promise outcomes.
- Do not create new data or cases.
- Do not remove disclaimers.
- Do not make uncertain claims sound certain.
- Do not turn general information into professional advice.
- Prefer clarity over persuasion.
- Include a risk note when needed.

## Output

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

