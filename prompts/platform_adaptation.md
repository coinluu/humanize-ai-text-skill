# Platform Adaptation Prompt

## Purpose

Adapt expression to the target platform or communication channel without changing facts or creating platform stereotypes.

## General Rules

- Match the platform's reading rhythm and expected density.
- Keep the user's core meaning and protected facts.
- Do not invent personal experience, data, cases, or results.
- Avoid clickbait, exaggerated emotion, and unsupported claims.

## Platform Rules

### 小红书

Language goal:

- Practical, readable, lightly personal, and easy to scan.

Suitable:

- Short paragraphs.
- Concrete observations.
- Gentle evaluation.
- "适合谁/不适合谁" if supported by source.

Not suitable:

- Fake personal experience.
- Overstated product effects.
- Too many slogans or hard-sell phrases.

Paragraph rules:

- Use 1-3 sentence paragraphs.
- Keep each point visually clear.

Tone rules:

- Natural, specific, restrained, not performative.

### 抖音口播

Language goal:

- Speakable, direct, paced, and easy to understand on first listen.

Suitable:

- Short sentences.
- Clear turns.
- Natural pauses.
- Direct opening.

Not suitable:

- Long nested sentences.
- Dense written-language paragraphs.
- Abstract claims without a spoken anchor.

Paragraph rules:

- Break by breath or idea.
- Each paragraph should be easy to say aloud.

Tone rules:

- Conversational but not loud or exaggerated unless the brand voice requires it.

### 公众号

Language goal:

- Thoughtful, structured, readable, and credible.

Suitable:

- Clear opening problem or observation.
- Smooth transitions.
- Paragraph-level logic.
- Moderate author judgment.

Not suitable:

- Grand empty opening.
- Mechanical summary ending.
- Excessively casual slang.

Paragraph rules:

- Use medium-length paragraphs.
- Each paragraph should advance one idea.

Tone rules:

- Calm, clear, reflective, not overly official.

### 知乎

Language goal:

- Clear reasoning, grounded judgment, and answer-oriented structure.

Suitable:

- Direct answer first when appropriate.
- Explain reasoning.
- Distinguish fact, opinion, and condition.

Not suitable:

- Vague motivational language.
- Unsupported certainty.
- Marketing tone.

Paragraph rules:

- Use logic blocks.
- Add bullets only when they improve readability.

Tone rules:

- Rational, experienced, and precise.

### 朋友圈

Language goal:

- Natural, concise, low-pressure, and personal-feeling without fake experience.

Suitable:

- Short sentences.
- Light emotion.
- Everyday wording.

Not suitable:

- Long sales pitch.
- Forced intimacy.
- Overly polished article tone.

Paragraph rules:

- Keep compact.
- Avoid too many sections.

Tone rules:

- Relaxed and sincere.

### 私域社群

Language goal:

- Clear, useful, community-aware, and action-oriented.

Suitable:

- Direct value.
- Clear next step.
- Friendly but bounded tone.

Not suitable:

- Pressure-heavy sales language.
- Excessive emoji-like enthusiasm.
- Fake closeness.

Paragraph rules:

- Start with context or benefit.
- End with a clear action if needed.

Tone rules:

- Warm, practical, not pushy.

### 销售文案

Language goal:

- Credible persuasion with clear value and responsible claims.

Suitable:

- Audience pain points.
- Specific benefits supported by source.
- Clear CTA.

Not suitable:

- Guaranteed results.
- Fake scarcity.
- Unsupported social proof.

Paragraph rules:

- Problem, value, proof if provided, action.

Tone rules:

- Confident and restrained.

### 商务文档

Language goal:

- Precise, professional, structured, and decision-friendly.

Suitable:

- Clear conclusion.
- Conditions and scope.
- Action items.

Not suitable:

- Over-casual language.
- Emotional persuasion.
- Unsupported certainty.

Paragraph rules:

- Use headings or bullets when useful.
- Keep hierarchy clear.

Tone rules:

- Professional, concise, and accountable.

### 通用文本

Language goal:

- Natural, clear, and readable.

Suitable:

- Varied sentence rhythm.
- Concrete wording.
- Direct transitions.

Not suitable:

- Formulaic AI openings.
- Empty slogans.
- Excessive embellishment.

Paragraph rules:

- Organize by idea.

Tone rules:

- Match the user's original intent and audience.

## Output

```yaml
platform_adaptation:
  platform: ""
  language_goal: ""
  suitable_moves: []
  unsuitable_moves: []
  paragraph_rules: []
  tone_rules: []
```

