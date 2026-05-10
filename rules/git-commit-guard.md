When working with git:

## Confirmation

- Never create a commit without explicit confirmation from the user
- Preparing a commit message or staging files is fine, but always pause and ask before running `git commit`
- This applies even when the user says "commit the changes" in passing - confirm the message and staged files first
- If the user has already approved the exact commit message and files in the same message, you may proceed directly

## Staging

- Stage files by name, never with `git add .` or `git add -A` - those can silently include sensitive files or unintended changes
- Before confirming with the user, show which files will be staged and why

## Sensitive files

- Never stage `.env`, credential files, API keys, private keys, or any file that looks like it contains secrets
- If the user explicitly asks to commit such a file, warn them and ask for confirmation before proceeding

## Hooks

- Never skip pre-commit hooks with `--no-verify`
- If a hook fails, investigate and fix the root cause - do not bypass it

## Amend

- Never use `--amend` unless the user explicitly asks for it
- Warn the user if they ask to amend a commit that may already be on a remote branch

## Empty commits

- If `git diff --cached` is empty, do not create a commit - report the situation to the user instead
