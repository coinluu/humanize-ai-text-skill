# Rewrite Intensity Controller Prompt

## Purpose

Choose the appropriate rewrite intensity from Level 1-5 based on the user's request, platform, content type, industry risk, and source quality.

## Inputs

Use:

- User requested intensity
- Content type
- Platform
- Industry risk
- AI tone diagnosis
- Protected facts
- Reference sample availability
- Whether the user permits hypothetical scenarios

## Levels

### Level 1: 轻度润色

Use when:

- Text is formal, sensitive, or already acceptable.
- The user asks for "润色", "稍微自然一点", or "不要改太多".
- The text involves medical, legal, financial, education outcome, job application, compliance, or safety-sensitive content.

Allowed:

- Smooth wording.
- Improve punctuation and sentence flow.
- Remove obvious stiff phrases.

Boundary:

- Keep structure and claims almost unchanged.

### Level 2: 中度自然化

Use when:

- User asks for normal "去 AI 味" or "自然一点".
- No high-risk issue is present.
- The text needs rhythm and paragraph improvement.

Allowed:

- Rewrite sentences.
- Adjust paragraph rhythm.
- Replace abstract wording with supported clear expression.

Boundary:

- Do not add new cases, data, or personal experience.

### Level 3: 强真人化

Use when:

- Text is highly mechanical.
- Platform adaptation needs stronger changes.
- User asks for "更像真人", "更有表达感", or "更适合发布".

Allowed:

- Reorganize structure.
- Rewrite opening and ending.
- Add natural emphasis and author judgment based on existing meaning.

Boundary:

- Do not weaken accuracy or become exaggerated.

### Level 4: 参考样本风格迁移

Use when:

- Reference sample is provided and user asks to learn style.

Allowed:

- Transfer general structure, rhythm, tone, sentence tendency, and organization.

Boundary:

- Do not reuse sample stories, examples, titles, phrases, metaphors, or identifiable expressions.

### Level 5: 创意重写

Use when:

- User explicitly asks for creative rewriting, major reconstruction, or multiple bold versions.
- Content is low-risk.
- Protected facts are limited and easy to preserve.

Allowed:

- Rebuild angle, structure, and expression more freely.

Boundary:

- Do not invent facts, data, cases, personal experience, results, or authority.
- Do not use for high-risk content.

## Auto-Selection Rules

- If high-risk: default to Level 1; use Level 2 only if the rewrite is purely clarity-focused.
- If platform is named and low-risk: default to Level 2 or Level 3.
- If sample is provided: use Level 4, then cap by safety risk.
- If the user asks only for light polish: use Level 1.
- If the source is extremely generic but low-risk: use Level 3.
- If no preference is given: use Level 2.

## Output

```yaml
rewrite_intensity_decision:
  level: 1|2|3|4|5
  reason: ""
  allowed_changes: []
  forbidden_changes: []
  safety_cap_applied: true|false
```

