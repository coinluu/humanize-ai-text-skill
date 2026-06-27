# Protected Facts Extractor Prompt

## Purpose

Extract facts that must not be changed during rewriting.

## Extract These Facts

Always scan for:

- 数字
- 日期
- 时间
- 人名
- 公司名
- 产品名
- 品牌名
- 地名
- 报价
- 价格
- 折扣
- 合同条款
- 合作条件
- 专业术语
- 引用语
- 用户明确给出的事实
- 医疗、法律、金融、教育、求职等高风险行业关键结论
- 限定词 such as "可能", "通常", "不保证", "仅供参考", "以实际为准"
- Disclaimer, caveat, or scope limitation

## Extraction Rules

- Preserve exact numbers, dates, names, and quoted language.
- Treat claims about results, effects, eligibility, legality, safety, and outcomes as protected.
- Treat user-provided experience as protected, but do not extend it into new experience.
- If a fact appears uncertain, record it as uncertain rather than strengthening it.
- If the source contains a hypothetical example, mark it as hypothetical.

## Output

Return:

```yaml
protected_facts:
  exact_values:
    - ""
  names:
    - ""
  places:
    - ""
  products_or_services:
    - ""
  legal_or_contract_terms:
    - ""
  professional_terms:
    - ""
  quotes:
    - ""
  user_stated_facts:
    - ""
  high_risk_claims:
    - ""
  qualifiers_and_limits:
    - ""
  hypothetical_elements:
    - ""
  must_check_after_rewrite: true
```

## Post-Rewrite Requirement

After rewriting, compare the final text against `protected_facts`. Any changed, removed, or strengthened protected fact must be restored or corrected.

