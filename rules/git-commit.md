When working with git:

- Never create a commit without explicit confirmation from the user
- Preparing a commit message or staging files is fine, but always pause and ask before running `git commit`
- This applies even when the user says "commit the changes" in passing - confirm the message and staged files first
- If the user has already approved the exact commit message and files in the same message, you may proceed directly
- Always add a `Signed-off-by` trailer to every commit: `Signed-off-by: Your Name <your@email.com>`
