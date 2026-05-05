---
paths: ["**/*.md"]
---

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
