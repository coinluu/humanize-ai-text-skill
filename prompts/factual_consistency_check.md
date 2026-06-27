# 事实一致性检查 Prompt

## 用途

改写后对照原文和 Protected Facts，检查并自动修正事实漂移。

## 检查项

数字、日期、时间、名称、公司名、产品名、地名、价格、引用语、条件、合同条款、专业术语、高风险结论、限定词、免责声明、核心意思和结论。

同时检查是否新增未经用户提供的事实、数据、案例、客户结果、个人经历；是否把假设场景写成真实案例；是否把参考样本内容当成事实。

## 修正规则

发现问题时：指出漂移，立即修正，再重新检查。用户明确允许假设场景时，也必须标注为假设，不得写成真实经历或证据。

## 输出

```yaml
factual_consistency_check:
  passed: true|false
  issues_found:
    - issue: ""
      source_value: ""
      rewritten_value: ""
      correction: ""
  corrected_rewrite: ""
  final_passed: true|false
```
