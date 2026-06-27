# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows semantic versioning.

## [1.0.0] - 2026-06-27

### Added

- Agent-ready skill structure for AI-text humanization.
- `basic_humanize` mode for general AI-tone reduction and natural rewriting.
- `platform_humanize` mode for platform-aware adaptation.
- `sample_guided_humanize` mode for reference sample style extraction.
- Platform adaptation workflow for Xiaohongshu, Douyin scripts, WeChat articles, Moments, private groups, sales copy, business documents, and generic text.
- Content type routing for articles, social notes, short-video scripts, sales copy, titles, captions, comment replies, private messages, emails, resumes, business documents, knowledge explanations, and generic text.
- Protected facts preservation before and after rewriting.
- Reference sample style extraction rules that transfer general expression patterns only.
- Safety checks for high-risk domains.
- Anti-overhumanization rules to prevent forced slang, exaggerated emotion, oily tone, and low-quality marketing style.
- Before/after examples for major usage scenarios.
- Test specifications for basic rewriting, platform adaptation, content type routing, sample-guided rewriting, safety, protected facts, no fabrication, and anti-overhumanization.

