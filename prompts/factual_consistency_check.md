# Factual Consistency Check Prompt

## Purpose

After rewriting, compare the rewritten text against the source text and protected facts. Automatically correct factual drift.

## Check Items

Verify:

- Numbers are unchanged.
- Dates and times are unchanged.
- Names, company names, product names, and places are unchanged.
- Prices, quotes, conditions, and contract terms are unchanged.
- Professional terms and high-risk conclusions are preserved.
- Necessary qualifiers and disclaimers remain.
- The core meaning and conclusion did not shift.
- No unsupported fact was added.
- No unsupported data was added.
- No unsupported case, customer result, or personal experience was added.
- No hypothetical scenario was written as a real case.
- No reference sample content was imported as source fact.

## Correction Rules

If any issue is found:

1. Identify the drift.
2. Revise the rewritten text immediately.
3. Re-run the check.
4. Keep the corrected version as final.

If a user explicitly allowed hypothetical scenarios:

- Mark them clearly as hypothetical.
- Do not present them as real experience or proof.

## Output

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

