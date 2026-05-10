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

## When there are no findings

Replace the findings section and summary table with a single line:

```
✅ No findings — [scope] looks clean.
```

Keep the header (scope, file count) and add a one-sentence verdict if context warrants it.

## Principles

- Readable in under 30 seconds for verdict-only readers
- Group by severity (worst first) or by category
- If longer than one screen, add TL;DR after header
- Tables/bullets over prose walls
