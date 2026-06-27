# Sample Style Analysis Prompt

## Purpose

When a reference sample is provided, analyze its reusable style traits before rewriting the user's text.

## Analyze

### Opening Method

Identify whether the sample opens with:

- A direct conclusion
- A concrete scene
- A question
- A tension or contrast
- A personal observation
- A factual setup
- A concise problem statement

Do not copy the sample opening.

### Paragraph Rhythm

Identify:

- Average paragraph length
- Whether paragraphs are compact or developed
- How ideas move from one paragraph to the next
- Whether the sample uses lists, short turns, or continuous prose

### Sentence Features

Identify:

- Long or short sentence tendency
- Degree of oral expression
- Use of pauses, contrast, questions, or emphasis
- Whether the syntax is simple or layered

### Tone Features

Identify:

- Calm, sharp, warm, professional, reflective, conversational, restrained, or persuasive tone
- Degree of emotional expression
- Degree of directness

### Viewpoint Expression

Identify:

- How the sample states opinions
- Whether it uses strong judgment or cautious framing
- How it balances observation and conclusion

### Source of Realness

Identify general methods that create realness:

- Specific observation style
- Natural uncertainty
- Clear judgment
- Scene-level detail
- Plain wording
- Imperfect but controlled rhythm

Do not transfer any specific personal story, case, or unique detail.

### Ending Method

Identify whether the sample ends with:

- A concise conclusion
- A practical suggestion
- An open thought
- A call to action
- A summary of the main judgment

### Reusable Expression Patterns

List only general patterns that can guide the rewrite.

## Output

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

