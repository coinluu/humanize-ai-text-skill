# Output Modes

`humanize-ai-text-skill` supports four output modes.

## concise

Use when the user wants the rewritten version only.

Output:

```markdown
{rewritten text}
```

Best for:

- Fast copy-and-paste usage.
- Low-risk text.
- Users who do not need explanation.

## standard

Default mode.

Output:

```markdown
## AI 感诊断

## 改写策略

## 真人化改写版

## 修改说明

## 风险提示
```

Best for:

- Most rewriting tasks.
- Users who want a useful rewrite plus brief reasoning.

## full

Detailed mode.

Output includes:

- AI-tone diagnosis.
- Protected facts.
- Rewrite strategy.
- Rewritten version.
- Alternate version when useful.
- Change notes.
- Factual consistency check.
- Risk notes.
- Publish-readiness score.

Best for:

- Complex text.
- High-risk content.
- Sample-guided rewriting.
- Review workflows.

## debug

Inspection mode.

Output includes:

- Parsed input.
- Content type decision.
- Protected facts.
- Safety check.
- AI-tone diagnosis.
- Rewrite intensity decision.
- Platform adaptation.
- Sample style extraction.
- Rewrite result.
- Factual consistency check.

Best for:

- Testing the skill.
- Updating prompts or rules.
- Auditing behavior.

