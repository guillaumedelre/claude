# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a collection of **Claude Code rules** that define behavioral guidelines for Claude when working on any project.

Rules are markdown files loaded automatically by Claude Code. Each rule enforces a specific behavior: tone, commit format, tool usage, reporting style, etc.

## Repository Structure

```
.claude/
└── rules/                  # Behavioral rules loaded by Claude Code
    ├── casual-tone.md
    ├── concise-comments.md
    ├── context7-mcp.md
    ├── conventional-commit.md
    ├── docker-compose-first.md
    ├── dx-report-format.md
    ├── git-commit-guard.md
    ├── no-em-dash.md
    ├── objective-analysis.md
    ├── oss-contribution.md
    ├── pragmatic-design.md
    ├── precise-tech-terms.md
    ├── reliable-information.md
    └── sourced-docs.md
```

## Creating or Modifying Rules

### File format

Each rule is a plain markdown file with an optional frontmatter to restrict the rule to specific file paths:

```markdown
---
paths: ["**/*.md"]
---

When doing X:

- Do this
- Not that
```

Omit the frontmatter if the rule applies globally.

### Content guidelines

- Lead with the trigger context ("When writing commit messages:", "When the project contains a docker-compose.yml:")
- Use bullet points or short sections, not prose walls
- Include concrete examples (good vs bad) when the rule involves a format or style choice
- Keep rules focused: one concern per file

### Naming convention

Use `kebab-case.md`, named after the concern, not the solution. Examples: `git-commit-guard.md`, `docker-compose-first.md`.

## Tooling

The **Context7 MCP** is installed globally (user scope) and provides up-to-date library documentation. See `rules/context7-mcp.md` for usage guidelines.

## Important Notes

- This is a **rules-only repository**: no code, no tests, no CI
- Rules are global: they apply to every project where this config is loaded
- Keep rules short and actionable — a rule that requires reading to understand will be ignored
