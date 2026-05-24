When completing any task (code, configuration, or other):

## Required before moving to the next task

After every task, without exception, before proposing the next step:

1. Scan all Markdown files in the project root and any `docs/` directory.
2. Update every file whose content is affected by the completed task: roadmaps, changelogs, architecture docs, README, API references, etc.
3. If a file uses a checklist, tick every item that was delivered (`- [ ]` → `- [x]`).

## Rules

- Never propose the next task before this scan is done.
- Do not wait for the user to ask — do it proactively every time.
- Update files even if they are gitignored — local accuracy matters.
- If nothing needs updating, skip silently — do not mention it.
- If documentation exists and the change could affect a doc site config (`mkdocs.yml`, `docusaurus.config.js`, `_config.yml`), update it too.
