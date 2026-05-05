When producing reports (review, audit, research, compatibility check):

## Severity indicators

| Icon | Level |
|------|-------|
| ❌ | Critical / Blocker |
| ⚠️ | High / Warning |
| 💡 | Medium / Suggestion |
| ℹ️ | Info / Low |
| ✅ | Positive / OK |

Map severity words automatically ("Critical" → ❌, "Warning" → ⚠️).

## Structure

**Header:**
```
# [Report Title]

**Scope:** `path/audited`  |  **Files:** 42  |  **Findings:** 2 ❌  3 ⚠️  1 💡
```

**Findings (2-3 lines each):**
```
❌ **SQL injection** - `src/Repository/UserRepository.php:42`
  Query built with string concatenation using `$username`.
  **Fix:** use bound parameter via QueryBuilder.
```

**Summary:**
```
## Summary

| Level | Count |
|-------|-------|
| ❌ Critical | 2 |
| ⚠️ Warning | 3 |

**Verdict:** [one sentence: status + top priority action]
```

## Principles

- Readable in under 30 seconds for verdict-only readers
- Group by severity (worst first) or by category
- If longer than one screen, add TL;DR after header
- Tables/bullets over prose walls
