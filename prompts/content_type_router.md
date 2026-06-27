# Content Type Router Prompt

## Purpose

Classify the source text into one primary content type and set rewrite priorities.

## Routing Rule

Choose one primary type. If the text could fit multiple types, choose based on where the rewritten text will be used.

## Supported Types

### article

Judgment features:

- Multi-paragraph argument, essay, article, newsletter, or long-form post.
- Contains观点、解释、论证、案例或段落层次.

Rewrite priorities:

- Improve opening, paragraph flow, transitions, and conclusion.
- Reduce generic framing.
- Preserve logic and claims.

### social_note

Judgment features:

- Xiaohongshu-style note, lifestyle share, experience note, short social post.
- Often practical, personal-sounding, easy to scan.

Rewrite priorities:

- Make it specific, readable, and platform-native.
- Use short paragraphs.
- Avoid fake personal experience.

### short_video_script

Judgment features:

- Meant to be spoken in Douyin, video, livestream, course intro, or oral script.
- Needs pacing, hooks, and spoken rhythm.

Rewrite priorities:

- Use short, speakable sentences.
- Add natural pauses.
- Make the logic easy to hear once.

### sales_copy

Judgment features:

- Promotes a product, service, course, event, offer, or consultation.
- Contains value proposition, pain point, CTA, or benefit claims.

Rewrite priorities:

- Clarify who it is for and what value it offers.
- Strengthen credibility without adding unsupported proof.
- Avoid exaggerated outcomes.

### title

Judgment features:

- A headline, subject line, article title, video title, or post title.

Rewrite priorities:

- Make it clear, accurate, and attractive.
- Do not create false urgency, false scarcity, or misleading claims.

### caption

Judgment features:

- Short text attached to image, video, product, or social post.

Rewrite priorities:

- Keep concise.
- Match mood and context.
- Avoid over-explaining.

### comment_reply

Judgment features:

- Reply to a comment, review, objection, DM, or public interaction.

Rewrite priorities:

- Be relevant, warm, concise, and situation-aware.
- Avoid sounding scripted or defensive.

### private_message

Judgment features:

- One-to-one message, private domain message, outreach, follow-up, or chat copy.

Rewrite priorities:

- Make intent clear.
- Keep tone natural and respectful.
- Avoid pressure or excessive familiarity.

### email

Judgment features:

- Email subject, body, follow-up, request, apology, proposal, or work communication.

Rewrite priorities:

- Improve clarity, politeness, structure, and action items.
- Preserve formal boundaries.

### resume

Judgment features:

- Resume bullets, profile summary, project descriptions, cover letter, or job application content.

Rewrite priorities:

- Make achievements clear and role-relevant.
- Preserve truthfulness.
- Do not invent metrics, responsibilities, employers, or outcomes.

### business_doc

Judgment features:

- Report, proposal, memo, plan, meeting summary, announcement, SOP, or business explanation.

Rewrite priorities:

- Use precise, restrained, decision-friendly language.
- Preserve hierarchy, conditions, and scope.

### knowledge_explanation

Judgment features:

- Explains a concept, method, process, policy, tutorial, or educational content.

Rewrite priorities:

- Improve clarity and logical progression.
- Use examples only if provided or clearly hypothetical.
- Preserve accuracy.

### generic_text

Judgment features:

- Does not clearly match another category.

Rewrite priorities:

- Preserve meaning.
- Improve naturalness, rhythm, and readability.

## Output

```yaml
content_type_result:
  content_type: ""
  confidence: high|medium|low
  judgment_features: []
  rewrite_priorities: []
```

