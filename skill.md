# Humanize AI Text Skill

## Purpose

Use this Skill to rewrite AI-generated or overly mechanical Chinese text into a version that feels more natural, credible, and appropriate for the target platform and content scenario.

The Skill must preserve the user's original meaning, protect factual information, avoid fabrication, and produce useful diagnostic notes, rewrite rationale, and risk warnings when needed.

The goal is editing quality: better rhythm, clearer expression, more natural structure, stronger platform fit, and higher publish readiness.

This is a stateless Agent Skill. It does not require a database, backend service, user system, or long-term memory. Reference samples are used only within the current request context. Do not store samples, build user profiles, or carry style preferences across unrelated requests.

## When to Use

Call this Skill when the user asks to:

- 去 AI 味
- 改得更自然
- 改得像真人写
- 改得自然一点
- 像小红书
- 像口播
- 降低模板感、官方感、机器感、营销感
- 把文本改成小红书、抖音、公众号、知乎、朋友圈、私域社群、销售文案、商务文档等风格
- 把 AI 初稿改成更适合发布的版本
- 优化文章、文案、口播稿、标题、评论回复、邮件、简历、商务材料等文本
- 根据参考样本学习风格并改写用户原文，例如"参考这个样本风格"
- 在保留事实的前提下改善表达节奏、语气、结构和可读性

## When Not to Use

Do not use this Skill, or use only to refuse and explain boundaries, when the user asks to:

- 伪造事实
- 虚构经历、案例、数据、客户结果或个人故事
- 冒充真实用户经历
- 制造虚假来源、误导性表达或不透明的内容归属
- 复用参考样本的具体内容、标题、原句、故事、案例或强识别性表达
- 在医疗、法律、金融、教育、求职等高风险行业中夸大结果
- 删除必要免责声明、限制条件、风险提示或合规表述
- 把不确定信息改成确定承诺

If the user request contains both allowed and disallowed parts, complete the allowed editing task while explicitly declining the unsafe part.

## Stateless Operation

- Treat every request independently.
- Use reference samples only for the current rewrite.
- Do not save reference samples.
- Do not infer or maintain a long-term user profile.
- Do not remember platform preferences beyond the active conversation unless the user repeats them.
- Do not require or assume any database, backend system, account system, or persistent storage.
- Keep all style transfer grounded in the current source text, current reference sample, and current user instructions.

## Supported Modes

### 1. basic_humanize

Use for general naturalization when no target platform or reference sample is required.

Typical tasks:

- Remove stiff AI wording.
- Improve sentence rhythm.
- Reduce generic structure.
- Make the text clearer and more human without changing substance.

Boundary:

- Do not add examples, data, stories, or stronger claims unless provided by the user.

### 2. platform_humanize

Use when the user names a platform, publishing channel, or communication scene.

Supported platform scenes include:

- 小红书
- 抖音
- 公众号
- 知乎
- 朋友圈
- 私域社群
- 销售沟通
- 商务邮件
- 简历和求职材料

Typical tasks:

- Adjust density, tone, structure, and phrasing for the platform.
- Make the text feel native to the channel without relying on stereotypes.
- Preserve factual accuracy and content purpose.

Boundary:

- Platform fit must not become clickbait, exaggeration, fake experience, or unsupported persuasion.

### 3. sample_guided_humanize

Use when the user provides one or more reference samples and asks to learn the style.

Typical tasks:

- Analyze the sample's structure, rhythm, tone, sentence tendency, argument style, and content organization.
- Transfer only general expression patterns.
- Rewrite the user's original text based on the user's own facts and meaning.

Boundary:

- Do not copy or adapt sample-specific stories, examples, titles, original sentences, unique metaphors, personal experiences, or strongly identifiable expressions.

## Supported Content Types

- `article`: Long-form article, essay, newsletter, or official account post. Prioritize structure, argument flow, paragraph rhythm, and readable transitions.
- `social_note`: Social platform note such as Xiaohongshu or community post. Prioritize directness, practical value, natural tone, and scannability.
- `short_video_script`: Spoken script for short video or livestream. Prioritize speakable rhythm, short sentences, hooks, pacing, and oral clarity.
- `sales_copy`: Product, service, or offer copy. Prioritize value clarity, audience fit, credible persuasion, and claim discipline.
- `title`: Headline or title. Prioritize clarity, accuracy, curiosity, and platform fit without clickbait or false claims.
- `caption`: Image, video, or post caption. Prioritize brevity, context, mood fit, and easy reading.
- `comment_reply`: Reply to comments, reviews, objections, or social interactions. Prioritize relevance, warmth, boundaries, and concise response.
- `private_message`: One-to-one message, DM, private domain message, or outreach. Prioritize natural conversational tone and clear intent.
- `email`: Work or business email. Prioritize clarity, politeness, actionability, and appropriate formality.
- `resume`: Resume bullet, profile summary, project experience, or cover letter text. Prioritize truthfulness, specificity, role relevance, and no fabricated achievements.
- `business_doc`: Report, proposal, memo, meeting summary, or business document. Prioritize precision, hierarchy, restraint, and decision usefulness.
- `knowledge_explanation`: Educational or explanatory content. Prioritize accuracy, plain explanation, examples only when supported, and logical progression.
- `generic_text`: Any text that does not fit the above categories. Prioritize meaning preservation, natural flow, and factual consistency.

## Workflow

Follow this execution sequence:

1. Parse input
   - Identify source text, user goal, target platform, content type, audience, constraints, output mode, and rewrite intensity.
   - If source text is missing, ask the user to provide it.
   - If other information is missing but the task can proceed, infer conservatively and continue.

2. Determine mode
   - Use `sample_guided_humanize` when a reference sample is provided or requested.
   - Use `platform_humanize` when a platform, channel, or content scene is named.
   - Use `basic_humanize` for general naturalization requests.

3. Detect content type
   - Select the closest supported content type.
   - If the user did not specify content type, infer it automatically.
   - If multiple types apply, choose the primary publishing or usage context.

4. Extract protected facts
   - List information that must remain unchanged.
   - Treat uncertain or sensitive claims as protected until clarified.

5. Detect industry risk
   - Identify whether the text involves medical, legal, financial, education, employment, safety, compliance, or other high-risk claims.
   - Lower rewrite intensity when accuracy or compliance could be affected.

6. Diagnose AI-like tone
   - Detect generic openings, formulaic transitions, over-neat structure, vague claims, mechanical contrast, repeated rhythm, and platform mismatch.

7. Select rewrite intensity
   - Use the user's requested level if safe.
   - If unspecified, choose automatically based on platform, content type, AI-tone diagnosis, and industry risk.
   - Otherwise choose the lowest level that solves the writing problem.

8. Apply platform adaptation
   - Adjust structure, sentence rhythm, vocabulary, density, and directness for the target platform.
   - If no platform is specified, use `generic_text`.
   - Avoid platform caricatures.

9. Analyze reference samples if provided
   - Identify reusable style traits only.
   - Do not treat sample content as factual material.

10. Extract transferable style patterns if samples are provided
   - Extract structure, pacing, tone, sentence tendency, viewpoint style, and organization.
   - Exclude stories, cases, quotes, titles, unique metaphors, and identifiable expressions.

11. Rewrite text
    - Rebuild expression based on the user's source text and selected constraints.
    - Keep the rewrite natural, controlled, and publish-ready.

12. Check factual consistency
    - Compare rewrite against source.
    - Remove any added fact, changed number, strengthened claim, unsupported example, or altered conclusion.

13. Check anti-overhumanization
    - Remove forced slang, oily tone, vulgarity, fake emotion, exaggerated marketing language, and inappropriate familiarity.

14. Select output mode
    - Use the requested output mode.
    - Default to `standard` if the user does not specify.

15. Return final output
    - Provide the rewritten version and the required notes.
    - Include risk warnings only when relevant.

## Output Requirement

- The output must always be usable.
- Do not output analysis only.
- Unless the user did not provide source text, always include a rewritten version.
- If the user asks for diagnosis, provide diagnosis plus the rewrite.
- If the user requests an unsafe addition, decline that addition and still provide a safe rewrite based on the original text.
- If source text is missing, ask the user to provide the original text instead of inventing one.

## Protected Facts

The following information must be protected and preserved unless the user explicitly asks to change it and the change is safe:

- 数字
- 日期
- 人名
- 公司名
- 产品名
- 地名
- 报价
- 合同条款
- 专业术语
- 引用语
- 用户明确给出的事实
- 医疗、法律、金融、教育、求职等关键结论

Protected facts include both exact values and meaning. For example, changing "不保证录取" into "大幅提升录取概率" is not allowed even if no number changes.

If a fact is ambiguous, preserve the original wording or ask for clarification.

## Rewrite Intensity Levels

### Level 1: 轻度润色

Use for formal, high-risk, or already acceptable text.

Actions:

- Smooth awkward wording.
- Remove obvious AI phrases.
- Improve punctuation and sentence flow.
- Keep structure mostly unchanged.

Boundary:

- Do not reorganize arguments or change tone substantially.

### Level 2: 中度自然化

Use as the default for ordinary AI drafts.

Actions:

- Adjust sentence length and rhythm.
- Replace generic wording with clearer supported expression.
- Improve paragraph transitions.
- Reduce template-like structure.

Boundary:

- Do not add new examples, personal experience, or claims.

### Level 3: 强真人化

Use when the text is clearly stiff, generic, or unsuitable for the target scene.

Actions:

- Reorganize paragraphs.
- Make expression more direct and scene-aware.
- Improve the opening, transitions, and ending.
- Increase natural variation in rhythm and emphasis.

Boundary:

- Do not sacrifice factual precision or professional appropriateness.

### Level 4: 参考样本风格迁移

Use only when a reference sample is provided.

Actions:

- Extract transferable style patterns from the sample.
- Rebuild the user's text using those general patterns.
- Preserve the user's own facts and meaning.

Boundary:

- Do not reuse sample-specific content, stories, titles, lines, metaphors, or identifiable phrasing.

### Level 5: 创意重写

Use only when the user explicitly asks for a major rewrite and the content is not high-risk.

Actions:

- Rebuild structure, rhythm, angle, and expression more freely.
- Produce a more polished and distinctive version.
- Keep the same factual base and user intent.

Boundary:

- Do not invent facts, examples, authority, data, personal experience, results, or claims.
- Avoid Level 5 for medical, legal, financial, education outcome, employment, compliance, or safety-sensitive content.

## Reference Sample Rules

When the user provides reference samples, use them only to extract general expression patterns, such as:

- Structure
- Rhythm
- Tone
- Sentence tendency
- Viewpoint expression
- Content organization

The following sample elements are not transferable:

- Specific stories
- Personal experiences
- Cases
- Unique metaphors
- Original sentences
- Titles
- Strongly identifiable expressions

The Skill must reorganize and rewrite based on the user's original text. It must not reuse the sample's specific content.

## Safety Rules

Always follow these safety rules:

- Do not fabricate facts.
- Do not fabricate data.
- Do not fabricate cases.
- Do not fabricate personal experience.
- Do not fabricate authority, endorsement, certification, award, or expert backing.
- Do not exaggerate revenue, investment return, medical effect, legal result, admission result, hiring result, or product outcome.
- Reduce rewrite intensity for high-risk industries.
- Preserve necessary qualifiers, limitations, warnings, disclaimers, and uncertainty markers.
- Do not turn general information into professional advice.
- Do not remove legally or commercially important caveats.

## Anti-Overhumanization Rules

Do not create "human feeling" by making the text:

- Too slangy
- Too wordy
- Oily or ingratiating
- Vulgar
- Clickbait-like
- Overly emotional
- Overly familiar
- Fake casual
- Like a low-quality marketing account
- Dependent on forced jokes or fake vulnerability

Humanized text should sound like a real person writing appropriately for the context, not like a performance of being human.

## Output Modes

### concise

Return only the rewritten version.

Use when:

- The user asks for direct output.
- The text is low-risk.
- No diagnostic explanation is needed.

### standard

Return the default structured output:

- AI 感诊断
- 改写策略
- 真人化改写版
- 修改说明
- 风险提示

Use when:

- The user does not specify an output mode.
- The user needs a usable rewrite plus brief reasoning.

### full

Return a more detailed version:

- Input interpretation
- Content type
- Protected facts
- AI-like tone diagnosis
- Rewrite strategy
- Rewritten version
- Factual consistency notes
- Safety notes
- Optional alternate version if useful

Use when:

- The task is complex.
- The text is high-risk.
- The user asks for explanation or review.

### debug

Return internal-style execution details for testing the Skill:

- Parsed fields
- Content type decision
- Protected facts list
- Industry risk level
- AI tone diagnosis
- Rewrite intensity
- Platform adaptation choices
- Reference sample extraction, if any
- Final rewrite
- Check results

Use when:

- Testing prompts, rules, or examples.
- The user explicitly asks to inspect how the Skill made decisions.

## Default Output Format

Use this structure for `standard` mode:

```markdown
## AI 感诊断

- ...

## 改写策略

- ...

## 真人化改写版

...

## 修改说明

- ...

## 风险提示

- ...
```

If there is no meaningful risk, write:

```text
未发现需要特别提示的风险。
```

Keep explanations concise. The rewritten text is the primary deliverable.

## Quality Criteria

Evaluate every output against these criteria:

- 自然度：表达像真实写作者，而不是模板生成。
- 原意保留：核心观点、目的和信息不偏移。
- 事实保真：数字、名称、结论、限制和关键事实不被改变。
- 平台适配：语气、节奏、结构符合目标平台。
- 内容类型适配：文章、口播、销售、商务、邮件、简历等各自成立。
- 无虚构：不添加未经用户提供的事实、案例、数据、经历或背书。
- 不过度真人化：不口水化、不低俗化、不油腻化、不营销号化。
- 可发布：文本干净、清楚、可直接使用或接近可直接使用。
- 可解释：关键修改有理由，风险和边界可说明。
