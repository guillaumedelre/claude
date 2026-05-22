# Claude Code Rules

Personal collection of [Claude Code](https://claude.com/code) behavioral rules — markdown files loaded automatically to enforce consistent tone, commit format, tool usage, and workflow guidelines across every project.

## Rules

| Rule | Trigger | Effect |
|------|---------|--------|
| `casual-tone` | All conversations | French replies, light tone; neutral in artifacts |
| `concise-comments` | Code editing | One-line comments max, no obvious or task-specific remarks |
| `context7-mcp` | Library/framework work | Fetch up-to-date docs via Context7 MCP before answering |
| `context7-usage` | Library/framework work | Prefer Context7 over web search; pick high-score entries |
| `conventional-commit` | Commit messages | Enforce Conventional Commits v1.0.0 format and types |
| `docker-compose-first` | Projects with `compose.yaml` | Run commands via `docker compose exec/run`, not on host |
| `dx-report-format` | Reviews, audits, reports | Structured format with severity icons and summary table |
| `git-commit-guard` | All git operations | Never commit without explicit confirmation; stage by name |
| `no-em-dash` | All text output | Replace em dash with colon, comma, or two sentences |
| `objective-analysis` | Code analysis, proposals | Facts and trade-offs only; no unsupported opinions |
| `oss-contribution` | OSS issue/PR work | Read issue fully, check CONTRIBUTING, no direct main commit |
| `pragmatic-design` | Code design decisions | No premature abstractions; match scope to actual needs |
| `precise-tech-terms` | Technical communication | Reserved words (push, merge, deploy) only for exact operations |
| `reliable-information` | Any factual claim | Verify before stating; flag uncertainty; no invented URLs |
| `sourced-docs` | Markdown documentation | Link to authoritative sources for standards and specs |

## File format

Each rule is a plain markdown file. Add frontmatter only when the rule should apply to specific paths:

```markdown
---
paths: ["**/*.md"]
---

When doing X:

- Do this
- Not that
```

Omit frontmatter for global rules.

## Adding a rule

1. Create a `kebab-case.md` file in `.claude/rules/`, named after the concern (not the solution)
2. Open with the trigger context: `"When writing commit messages:"`, `"When the project contains a docker-compose.yml:"`
3. Use bullet points or short sections — avoid prose walls
4. Include a concrete example (good vs bad) when the rule involves a format or style choice
5. Keep it focused: one concern per file

## Notes

- Rules are global: they apply to every project where this config is loaded
- This repo contains no code, no tests, no CI — rules only
- Context7 MCP is installed globally (user scope) and used by the context7 rules
