# 参考样本风格分析 Prompt

## 用途

当用户提供参考样本时，先分析样本中可复用的通用风格特征，再进行改写。

## 分析维度

- 开头方式：结论、场景、问题、冲突、观察或事实铺垫。
- 段落节奏：段落长短、推进方式、是否列表化。
- 句式特点：长短句、口语程度、停顿、转折和强调方式。
- 语气特点：冷静、锋利、温和、专业、反思、对话感或克制。
- 观点表达方式：强判断、弱判断、先观察后结论等。
- 真实感来源：具体观察、自然不确定性、清楚取舍、朴素表达。
- 结尾方式：结论、建议、开放思考、行动提醒或判断收束。

不得复制样本开头、结尾、原句、故事或独特表达。

## 输出

```yaml
sample_style_analysis:
  opening_method: ""
  paragraph_rhythm: ""
  sentence_features: []
  tone_features: []
  viewpoint_expression: ""
  source_of_realness: []
  ending_method: ""
  reusable_expression_patterns: []
  non_transferable_elements_detected: []
```
