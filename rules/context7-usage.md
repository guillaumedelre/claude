When working with any library, framework, SDK, API, or CLI tool:

- Use the context7 MCP (`resolve-library-id` then `query-docs`) to fetch up-to-date documentation
- Applies to: Symfony components, Doctrine, API Platform, PHPUnit, Zenstruck Foundry, FrankenPHP, and any third-party package
- Use even for well-known libraries — training data may be outdated or incorrect on specific versions
- Prefer context7 over web search for library-specific questions (API syntax, configuration, migration guides, CLI usage)

## Choosing the right result

When `resolve-library-id` returns multiple matches:

- Prefer entries with a **higher benchmark score** (100 = best) — below 50 signals sparse coverage
- More code snippets = broader practical coverage; prefer those entries
- A focused package entry (e.g. `/symfony/messenger`) can be thinner than the umbrella docs entry (e.g. `/symfony/symfony-docs`); for broad questions, prefer the umbrella entry

## When NOT to use context7

- Refactoring or rewriting code
- Debugging business logic
- Code review
- General programming concepts unrelated to a specific library API
