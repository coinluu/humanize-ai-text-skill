# Protected Facts 抽取 Prompt

## 用途

改写前抽取不可改动事实，确保后续改写不会造成事实漂移。

## 必须抽取

数字、日期、时间、人名、公司名、产品名、品牌名、地名、报价、价格、折扣、合同条款、合作条件、专业术语、引用语、用户明确给出的事实、高风险行业关键结论、限定词、免责声明和适用范围。

## 抽取规则

- 精确数字、日期、名称和引用语必须原样保护。
- 结果、效果、资格、合法性、安全性等结论按高风险事实处理。
- 用户提供的经历可以保护，但不得扩写成新的经历。
- 不确定事实标记为不确定，不得强化。
- 假设场景必须标记为 hypothetical。

## 输出

```yaml
protected_facts:
  exact_values: []
  names: []
  places: []
  products_or_services: []
  legal_or_contract_terms: []
  professional_terms: []
  quotes: []
  user_stated_facts: []
  high_risk_claims: []
  qualifiers_and_limits: []
  hypothetical_elements: []
  must_check_after_rewrite: true
```

改写后必须逐项核对 `protected_facts`，发现改变、删除或强化时自动修正。
