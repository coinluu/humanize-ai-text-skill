# Sample Style Extraction Prompt

## Purpose

Extract transferable style patterns from reference samples while excluding sample-specific content.

## Transferable Elements

Only extract:

- Structure
- Rhythm
- Tone
- Sentence tendency
- Viewpoint expression
- Content organization
- Level of detail
- Opening and ending strategy in abstract form
- Relationship between observation, reasoning, and conclusion

## Non-Transferable Elements

Do not transfer:

- Specific stories
- Personal experiences
- Cases
- Unique metaphors
- Original sentences
- Titles
- Strongly identifiable expressions
- Names, places, brands, events, or examples from the sample
- Distinctive jokes, slogans, or signature phrasing

## Extraction Rules

- Describe patterns in neutral, professional language.
- Convert concrete sample behavior into abstract guidance.
- Do not treat the sample as a source of facts.
- Do not use sample content to fill missing facts in the user's text.
- If a sample trait conflicts with user facts, platform rules, or safety rules, discard it.

## Output

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

