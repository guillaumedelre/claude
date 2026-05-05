---
paths: ["**/*.php", "**/*.js", "**/*.ts", "**/*.py"]
---

When writing or proposing code:

- Solve the actual problem, not a hypothetical future one
- Don't add abstractions, interfaces, or patterns until a second use case exists
- Three similar lines are better than a premature helper function
- Don't add configurability, feature flags, or extension points "just in case"
- Prefer deleting code over adding backward-compatibility shims
- If simple if/else works, don't reach for a strategy pattern
- The right amount of code is the minimum that satisfies the requirement

When proposing changes:

- Weigh value against cost (complexity, maintenance, risk)
- If gain is marginal, mention it but flag as low-value so user decides
