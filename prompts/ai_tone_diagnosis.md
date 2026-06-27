# AI Tone Diagnosis Prompt

## Purpose

Identify why the source text feels AI-generated, template-like, overly official, or unnatural.

## Diagnose These Issues

Check for:

- 宏大空泛开头: broad openings such as "在当今时代", "随着社会发展".
- 结构模板化: predictable intro-analysis-summary, repeated three-part lists, or rigid parallelism.
- 连接词过多: excessive "首先/其次/最后", "因此/同时/此外".
- 抽象词过多: vague terms such as "赋能", "打造", "提升效率", "实现价值" without concrete support.
- 缺少具体场景: no clear reader situation, action, object, or context.
- 缺少作者判断: neutral summary with no clear stance, selection, or emphasis.
- 句式过于平均: sentences of similar length and rhythm.
- 语气过度中立: safe but flat, distant, or official.
- 营销腔过重: inflated promises, excessive praise, or pressure-heavy CTA.
- 平台不匹配: style does not fit the target channel.

## Judgment Rules

- Output only the 3-6 most important issues.
- Focus on issues that should guide the rewrite.
- Do not overdiagnose normal formal writing.
- For high-risk content, prefer restrained diagnosis and do not push for stronger persuasion.

## Output

```yaml
ai_tone_diagnosis:
  main_issues:
    - issue: ""
      evidence: ""
      rewrite_direction: ""
  overall_summary: ""
```

