When writing commit messages:

## Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Types

| Type | Usage |
|------|-------|
| `feat` | New feature (correlates with MINOR in SemVer) |
| `fix` | Bug fix (correlates with PATCH in SemVer) |
| `docs` | Documentation only |
| `style` | Formatting, no logic change |
| `refactor` | Neither fix nor feature |
| `perf` | Performance improvement |
| `test` | Adding or updating tests |
| `build` | Build system or external dependencies |
| `ci` | CI configuration and scripts |
| `chore` | Other changes not modifying src or tests |
| `revert` | Reverts a previous commit |

## Rules (from [Conventional Commits v1.0.0][spec])

1. Description is mandatory, lowercase, imperative mood, no trailing period
2. Scope is optional: `feat(auth): add OAuth2 support`
3. Breaking change: append `!` after type/scope, and/or add `BREAKING CHANGE:` footer
4. Body and footers separated from description by a blank line
5. Footer format: `token: value` or `token #value` (e.g. `Fixes #42`)

## Breaking changes

```
feat(api)!: remove deprecated endpoint

BREAKING CHANGE: /v1/users endpoint removed, use /v2/users instead.
```

## Examples

```
feat(auth): add refresh token rotation
fix(cart): prevent duplicate item on double-click
docs: update installation steps for Docker
refactor(order): extract discount calculation to service
test(invoice): add edge cases for zero-amount invoices
chore: update composer dependencies
```

## Prohibitions

- Never mention "Claude Code", "Claude", or "Generated with Claude" in any commit message
- No co-authored-by lines referencing AI tools
- No trailing summaries like "this commit adds..."

[spec]: https://www.conventionalcommits.org/en/v1.0.0/#specification
