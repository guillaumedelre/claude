When the project contains a `docker-compose.yml` or `compose.yaml` file:

- Run commands via `docker compose exec` or `docker compose run --rm`, not on host
- Applies to: php, composer, symfony, npm, psql, redis-cli, etc.
- Fall back to host only when Docker unavailable or user explicitly asks
- Use `docker compose` (v2 plugin), not legacy `docker-compose` binary

## exec vs run --rm

- Use `docker compose exec <service> <cmd>` to run a command inside an **already running** container (preserves state)
- Use `docker compose run --rm <service> <cmd>` for **one-off tasks** (fresh container, auto-cleanup)
- Add `-T` to either when piping data or running in non-interactive context (disables TTY allocation)

Example:
```bash
# Interacting with a running service
docker compose exec php bin/console cache:clear

# One-off task (migrations, fixtures, etc.)
docker compose run --rm php bin/console doctrine:migrations:migrate

# Piping data
docker compose exec -T db psql -U app < dump.sql
```

## When adding dependencies (database, cache, queue, search, mail)

- Default to a Compose service rather than host installation
- Use `condition: service_healthy` in `depends_on` instead of bare `depends_on` to wait for actual readiness
- Implement meaningful health checks (`pg_isready` for PostgreSQL, `redis-cli ping` for Redis, etc.)

Example:
```yaml
depends_on:
  db:
    condition: service_healthy
```

## Data and secrets

- Use named volumes (not anonymous) for persistent data: easier to inspect, back up, and migrate
- Store sensitive values (passwords, API keys) in Docker secrets or a `.env` file excluded from git, not hardcoded in `compose.yaml`

## When encountering Docker signals (`Dockerfile`, `.dockerignore`) but no Compose file

- Ask before suggesting host-level commands
