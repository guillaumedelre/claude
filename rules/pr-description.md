When writing or updating a pull request description:

## Summary section

- Write the Summary **after** finalising the diff, never before
- List only what is actually in the final diff — if a file was removed or excluded, remove it from the Summary
- Use bullet points, one per logical change (not one per file)
- Each bullet: what changed and why (not how)

## Accuracy check before submitting

- Re-read the Summary against `git diff main...HEAD --name-only`
- Remove any bullet that refers to a file or change not present in the diff
- If a planned change was dropped, update the Summary — do not leave ghost entries

## What not to include

- No checklist section
- No implementation details that are obvious from the diff
- No references to internal working documents (specs, drafts, roadmap files) that are gitignored
