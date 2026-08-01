# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A portable, agent-agnostic skill framework (plain Markdown, no code) that teaches AI coding agents to contribute to mature open-source repositories like experienced senior engineers. The framework prioritizes repository comprehension, minimal diffs, and maintainer-friendly output over code generation speed or volume.

Two installable skill folders live under `skills/`:
- `senior-open-source-engineer/` — the full framework
- `seo/` — a short alias that redirects to the full framework

There is no build system, test suite, linter, or package manager. All content is Markdown.

## Architecture

The main skill (`skills/senior-open-source-engineer/`) is organized by engineering phase:

- **`SKILL.md`** — primary entrypoint defining a 10-phase workflow: issue selection, intake/framing, repository adaptation, architecture learning, change planning, implementation, testing, self-review, PR/commit preparation, engineering journal
- **`CHECKLIST.md`** — per-contribution execution checklist covering issue selection, issue research, problem framing through git preparation
- **`ENGINEERING_LOG_TEMPLATE.md`** — template for append-only knowledge capture in a local file (`~/.claude/engineering-log/ENGINEERING_LOG.md`), never pushed to target repositories
- **`rules/`** — deep guidance split by concern: `issue-selection.md`, `issue-research.md`, `repository-adaptation.md`, `architecture.md`, `code-quality.md`, `testing.md`, `review.md`, `git.md`, `engineering-mindset.md`
- **`prompts/`** — reusable task prompts: `investigate.md`, `implement.md`, `testing.md`, `review.md`, `journal.md`
- **`templates/`** — output templates: `commit-message.md`, `issue-summary.md`, `resume-bullet.md`, `star-story.md`

The `seo/SKILL.md` contains frontmatter and a redirect list pointing at the sibling framework's files.

## Key design constraints for contributors

- Do not optimize for code volume — optimize for mergeable PRs and minimal diffs
- Do not dilute the repository-adaptation requirements (the 20-step "required first pass" in SKILL.md)
- Do not encourage generic PR boilerplate or broad refactoring
- Do not replace the minimal-diff bias with cleanup guidance
- Keep the phased structure (rules/, prompts/, templates/ as separate concerns) — the framework deliberately loads only what's needed per stage
- The `seo/` alias must remain a pure redirect with no independent logic

## File cross-references

SKILL.md links to rules/, prompts/, templates/, and CHECKLIST.md via relative paths. When renaming or moving files, update all `[text](path)` references in SKILL.md and seo/SKILL.md. The seo/SKILL.md uses `../senior-open-source-engineer/` relative paths to reach the main framework.
