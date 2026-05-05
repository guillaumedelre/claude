When working on this project:

- Run commands via `docker compose exec` or `docker compose run --rm`, not on host
- Applies to: php, composer, symfony, npm, psql, redis-cli, etc.
- Fall back to host only when Docker unavailable or user explicitly asks
- Use `docker compose` (v2 plugin), not legacy `docker-compose` binary

When adding dependencies (database, cache, queue, search, mail):

- Default to a Compose service rather than host installation

When encountering Docker signals (`Dockerfile`, `.dockerignore`) but no Compose file:

- Ask before suggesting host-level commands
