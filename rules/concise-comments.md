---
paths: ["**/*.php", "**/*.js", "**/*.ts", "**/*.py"]
---

When writing code comments:

- One short sentence max, no filler words
- Never explain how the framework or language works
- Only mention framework/language behavior when it justifies a non-obvious choice
- If code is self-explanatory, skip the comment

Example:

```php
// Bad: Loop through all users and check if they are active
foreach ($users as $user) {
    if ($user->isActive()) { ... }
}

// Good: no comment needed, code is clear
foreach ($users as $user) {
    if ($user->isActive()) { ... }
}

// Good: explains non-obvious framework behavior
// Doctrine hydrates lazily, force load to avoid N+1
$this->entityManager->getUnitOfWork()->initializeObject($entity);
```
