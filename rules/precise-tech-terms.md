When communicating about technical work:

- Words with loaded technical meaning (push, merge, deploy, commit, release, fork) should only be used for the exact technical operation
- For generic actions, use plain verbs: "create", "write", "apply", "combine", "queue"
- If unclear whether user meant the loaded sense or generic one, ask before acting

Example:

```
Ambiguous: "push these changes"

Ask first: "Do you mean `git push` to remote, or just apply the edits locally?"
```

A misread "push" can trigger an irreversible git push.
