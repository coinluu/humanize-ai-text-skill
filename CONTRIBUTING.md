# Contributing

Thanks for helping improve `humanize-ai-text-skill`. This project is an Agent-ready skill for humanizing AI-generated Chinese text while preserving facts, platform fit, and safety boundaries.

## How to Submit Issues

Open an issue when you find:

- A prompt module that gives unclear execution guidance.
- A rule that is too broad, too narrow, or unsafe.
- A before/after example that adds unsupported facts.
- A test case that does not match the skill behavior.
- Documentation that is confusing or incomplete.

Please include:

- The file or module involved.
- The input text or test prompt.
- The expected behavior.
- The actual behavior or concern.
- Any safety or factual-consistency risk.

## How to Propose New Platform Rules

Platform rules live in `rules/platform_rules.md` and are reflected in `prompts/platform_adaptation.md`.

A good platform rule proposal should include:

- Platform name or communication channel.
- Language goal.
- Paragraph rules.
- Tone rules.
- Opening and ending rules.
- Recommended expressions.
- Expressions to avoid.
- One realistic before/after example.

Do not propose platform rules that depend on fake personal experience, exaggerated results, or misleading claims.

## How to Propose New Content Type Rules

Content type rules live in `rules/content_type_rules.md` and are routed by `prompts/content_type_router.md`.

Include:

- Content type name.
- Judgment features.
- Rewrite priorities.
- Recommended rewrite intensity.
- Safety notes.
- Example input and expected rewrite direction.

## How to Add Before/After Examples

Examples live in `examples/`.

Each example should include:

- Scenario.
- Input metadata.
- `Before`.
- AI-tone diagnosis.
- Rewrite strategy.
- `After`.
- Change notes.
- Risk note.

Examples must not invent real customers, income results, medical/legal/financial outcomes, or personal experience.

## How to Add Tests

Tests live in `tests/`.

Each test file should include:

- Test objective.
- Test inputs.
- Expected behavior.
- Pass criteria.

Tests should cover both quality and safety. Prefer realistic prompts that a user might actually send.

## Pull Request Process

1. Keep changes scoped to one topic.
2. Update related prompts, rules, examples, and tests together when behavior changes.
3. Run a consistency scan for sensitive wording and outdated names.
4. Explain the behavior change in the PR description.
5. Add or update tests for new rules.
6. Do not remove safety boundaries to make text more persuasive.

## Documentation Style

- Use clear English.
- Keep Chinese examples when they clarify Chinese rewrite behavior.
- Prefer executable guidance over abstract explanation.
- Use consistent names: `basic_humanize`, `platform_humanize`, `sample_guided_humanize`.
- Use consistent file names: `sample_style_analysis`, `sample_style_extraction`, `sample_style_rules`.

## Safety Boundaries

All contributions must preserve:

- No fabricated facts.
- No fabricated data.
- No fabricated cases.
- No fabricated personal experience.
- No fabricated authority or endorsement.
- Lower rewrite intensity for high-risk domains.
- Protected facts must be extracted before rewriting and checked after rewriting.

## Reference Sample Style Extraction Rules

Reference samples may guide:

- Structure.
- Rhythm.
- Tone.
- Sentence tendency.
- Viewpoint expression.
- Content organization.

Reference samples must not provide reusable concrete content:

- Specific stories.
- Personal experiences.
- Cases.
- Unique metaphors.
- Original sentences.
- Titles.
- Strongly identifiable expressions.

The final rewrite must be based on the user's source text, not on reusable sample content.

