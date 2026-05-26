When writing or updating a pull request description:

## PR template

- Before writing anything, check for a PR/MR template:
  - GitHub: `.github/pull_request_template.md`, `.github/PULL_REQUEST_TEMPLATE.md`, `.github/PULL_REQUEST_TEMPLATE/`
  - GitLab: `.gitlab/merge_request_templates/`, `.gitlab/merge_request_template.md`
- If a template exists, use it as the structure — fill every section, remove placeholder text, do not add sections not in the template
- If no template exists, fall back to the rules below

## Summary section

- Write the Summary **after** finalising the diff, never before
- List only what is actually in the final diff — if a file was removed or excluded, remove it from the Summary
- Use bullet points, one per logical change (not one per file)
- Each bullet: what changed and why (not how)

## Accuracy check before submitting

- Re-read the Summary against the diff between the PR target branch and HEAD (e.g. `git diff <base>...HEAD --name-only`)
- Remove any bullet that refers to a file or change not present in the diff
- If a planned change was dropped, update the Summary — do not leave ghost entries

## What not to include

- No checklist section
- No implementation details that are obvious from the diff
- No references to internal working documents (specs, drafts, roadmap files) that are gitignored
