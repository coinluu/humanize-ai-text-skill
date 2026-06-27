# Rewrite Engine Prompt

## Purpose

Execute the humanized rewrite using the parsed input, content type, protected facts, safety rules, platform adaptation, rewrite intensity, and optional sample style patterns.

## Inputs

Use:

- `source_text`
- `content_type`
- `platform_adaptation`
- `protected_facts`
- `industry_risk`
- `ai_tone_diagnosis`
- `rewrite_intensity`
- `sample_style_patterns`
- `must_keep`
- `must_avoid`
- `allow_hypothetical_scenarios`

## Rewrite Rules

Do:

- Preserve the original core meaning.
- Preserve protected facts exactly.
- Delete or replace AI-like stock phrases.
- Break mechanical structure when needed.
- Add natural pauses and paragraph rhythm.
- Use a mix of long and short sentences.
- Replace empty abstract terms with clearer supported expression.
- Strengthen author judgment when the source supports it.
- Adjust tone for the target platform and content type.
- Keep the output clean and publishable.

Do not:

- Fabricate personal experience.
- Fabricate cases.
- Fabricate data.
- Fabricate customer results.
- Fabricate authority, certification, endorsement, or credentials.
- Exaggerate product effect, income, admission, hiring, treatment, legal, or investment outcomes.
- Turn hypothetical scenarios into real events.
- Copy reference sample sentences or unique expressions.
- Over-humanize the text with forced slang, oily tone, vulgar jokes, exaggerated emotion, fake familiarity, or low-quality marketing-account language.

## Intensity Application

- Level 1: Keep structure; polish wording.
- Level 2: Rewrite sentence flow and paragraph rhythm.
- Level 3: Reorganize and make stronger platform fit.
- Level 4: Apply abstract sample patterns without reusing content.
- Level 5: Rebuild angle and expression, but keep the same factual base.

## Platform and Content Application

- For social content, improve scannability and naturalness.
- For scripts, make it speakable.
- For business writing, preserve hierarchy and precision.
- For resumes, keep truthfulness and avoid invented metrics.
- For sales copy, improve value clarity without unsupported proof.
- For knowledge explanations, improve clarity without oversimplifying important caveats.

## Anti-Overhumanization Check

Before finalizing the rewrite, remove:

- Forced phrases such as "姐妹们", "说真的", "我真的服了" when they do not fit the scene.
- Overly casual wording in business, legal, medical, financial, resume, or professional content.
- Clickbait-style exaggeration.
- Fake personal emotion or fake closeness.
- Excessive complaints, teasing, or performative human tone.

The final rewrite should be natural, restrained, and scene-appropriate.

## Output

Return:

```yaml
rewrite_result:
  rewritten_text: ""
  major_changes:
    - ""
  preserved_facts:
    - ""
  notes_for_checker:
    - ""
```
