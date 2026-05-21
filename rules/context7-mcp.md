When working with external libraries, frameworks, or tools:

## When to use Context7

Call Context7 to fetch up-to-date documentation when:

- Writing code that uses a specific library API (methods, classes, options, config keys)
- The user asks about a library feature and your training data may be outdated
- Referencing a version-specific behavior or a recently released library
- Debugging an issue where incorrect API usage is a likely cause
- Comparing two libraries or explaining a library's behavior with confidence

Do **not** call Context7 for:

- Built-in language features (PHP arrays, JS promises, Python builtins...)
- General programming concepts not tied to a specific library
- Information clearly available in the current codebase (read the file instead)
- Libraries already covered by a loaded skill (prefer the skill's reference docs)

## How to use it

1. Call `resolve-library-id` with the library name to get the Context7 library ID
2. Call `query-docs` with that ID and a focused `topic` matching what you need
3. Use only what is relevant — do not dump the full output into the response

## Choosing the right library entry

`resolve-library-id` often returns several matches. Pick based on:

- **Benchmark score**: prefer higher scores (100 = best) — a score below 50 signals sparse coverage
- **Code snippets count**: more snippets = broader practical coverage
- **Source reputation**: prefer High or Medium
- **Scope**: a focused package entry (e.g. `/symfony/messenger`) can be thinner than the
  umbrella docs entry (e.g. `/symfony/symfony-docs`); for broad questions on a large
  framework, the umbrella entry is usually richer

## Principles

- One targeted call beats a broad call: pass a specific `topic` rather than fetching everything
- If Context7 has no entry for a library, fall back to the official docs URL (do not invent content)
- Treat fetched docs as authoritative for the version they describe; flag if the version differs from the project's
