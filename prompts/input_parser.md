# Input Parser Prompt

## Purpose

Parse the user's request into structured fields that downstream modules can use.

## Inputs to Identify

Extract:

- `source_text`: the text to rewrite.
- `mode`: `basic_humanize`, `platform_humanize`, or `sample_guided_humanize`.
- `platform`: target platform or communication channel.
- `content_type`: requested or inferred content type.
- `target_reader`: intended reader or audience.
- `author_identity`: who the text should sound like, if provided.
- `reference_sample`: sample text provided for style guidance.
- `rewrite_intensity`: requested Level 1-5 or natural language equivalent.
- `output_mode`: `concise`, `standard`, `full`, or `debug`.
- `allow_hypothetical_scenarios`: whether the user explicitly allows hypothetical scenarios.
- `must_keep`: facts, phrases, tone, structure, or sections the user wants preserved.
- `must_avoid`: words, claims, tone, structure, or changes the user forbids.
- `language`: default to Chinese unless otherwise requested.

## Inference Rules

- If the user says "去 AI 味", "自然一点", or "像真人写", set `mode: basic_humanize`.
- If the user names a platform, set `mode: platform_humanize` and record the platform.
- If the user provides a reference sample, set `mode: sample_guided_humanize`.
- If multiple modes apply, prefer the most specific mode: sample-guided over platform over basic.
- If no content type is given, infer it from the source text and user goal.
- If no rewrite intensity is given, leave it as `auto` for the controller.
- If no output mode is given, set `output_mode: standard`.
- If hypothetical scenarios are not explicitly allowed, set `allow_hypothetical_scenarios: false`.

## Clarification Rules

Do not ask questions for ordinary missing preferences. Infer conservatively.

Ask one concise question only when:

- No source text is provided.
- The target platform is essential and ambiguous.
- The text involves high-risk claims and the requested change could alter meaning.
- The user asks to add cases, data, or personal experience without providing real material.

## Output

Return a structured result:

```yaml
parsed_input:
  source_text: ""
  mode: ""
  platform: ""
  content_type: ""
  target_reader: ""
  author_identity: ""
  reference_sample: ""
  rewrite_intensity: auto
  output_mode: standard
  allow_hypothetical_scenarios: false
  must_keep: []
  must_avoid: []
  language: zh
  assumptions: []
  clarification_needed: false
  clarification_question: ""
```

