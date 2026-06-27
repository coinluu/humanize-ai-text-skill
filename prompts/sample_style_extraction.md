# 参考样本风格提炼 Prompt

## 用途

从参考样本中提炼可迁移的通用表达规律，同时排除样本具体内容。

## 可迁移

结构、节奏、语气、句式倾向、观点表达方式、内容组织方式、细节密度、抽象的开头/结尾策略、观察与结论的关系。

## 不可迁移

具体故事、个人经历、案例、独特比喻、原句、标题、强识别性表达、样本中的人物/品牌/地名/事件/数据、标志性口头禅或口号。

## 规则

- 用中性专业语言描述风格规律。
- 把具体样本行为转成抽象指导。
- 样本不是事实来源。
- 不用样本内容补足用户原文缺失信息。
- 样本风格与安全规则冲突时，放弃该风格特征。

## 输出

```yaml
sample_style_patterns:
  structure_pattern: ""
  rhythm_pattern: ""
  tone_pattern: ""
  sentence_pattern: ""
  viewpoint_pattern: ""
  organization_pattern: ""
  allowed_to_transfer: []
  must_not_transfer: []
  safety_notes: []
```
