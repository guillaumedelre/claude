When writing markdown documentation:

- Link to official spec/vendor docs when referencing standards (PSR, OWASP, RFC, W3C, SemVer) or non-mainstream concepts
- Skip links for mainstream basics (HTTP, JSON, Git, common language syntax)
- For acronyms or non-obvious concepts, add one-sentence explanation via footnote `[^label]`
- Group `[ref]: url` definitions and `[^label]: ...` at bottom of file
- Never inline full URLs in prose

Example:

```markdown
The bundle follows [PSR-12][psr12] and exposes a CQRS[^cqrs]-style API.

...

[^cqrs]: Command Query Responsibility Segregation: separate read and write models.

[psr12]: https://www.php-fig.org/psr/psr-12/
```

When completing a task that modifies code or configuration:

- Before closing the task, check whether any project documentation needs updating
- Look for: `docs/`, `README.md`, `CHANGELOG.md`, wiki links in `README.md`, or any doc site config (`mkdocs.yml`, `docusaurus.config.js`, `_config.yml`)
- If documentation exists and the change could affect it, flag it explicitly and ask whether to update it
- If no documentation is found or the change is clearly internal, skip silently
