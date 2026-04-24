# Keycloak SSO

Keycloak identity and access management server running with Docker Compose.

## Stack

- **Keycloak** (latest) — IAM server in dev mode
- **PostgreSQL 16** — persistent database

Both services use host networking.

## Quick Start

```bash
# Start
docker compose up -d

# Stop
docker compose down

# Stop and wipe data
docker compose down -v
```

## Access

| Service         | URL                           |
|-----------------|-------------------------------|
| Keycloak        | http://localhost:48080         |
| Admin Console   | http://localhost:48080/admin   |
| Health Check    | http://localhost:9000/health   |
| Metrics         | http://localhost:9000/metrics  |

**Admin credentials:** see `.env` (`KEYCLOAK_ADMIN` / `KEYCLOAK_ADMIN_PASSWORD`)

## Configuration

All settings are in `.env`:

| Variable                 | Default              | Description              |
|--------------------------|----------------------|--------------------------|
| `KEYCLOAK_ADMIN`         | `admin`              | Admin username           |
| `KEYCLOAK_ADMIN_PASSWORD`| `Admin123!`          | Admin password           |
| `KEYCLOAK_HOSTNAME`      | `localhost`          | Keycloak hostname        |
| `KEYCLOAK_HTTP_PORT`     | `48080`              | Keycloak HTTP port       |
| `POSTGRES_DB`            | `keycloak`           | Database name            |
| `POSTGRES_USER`          | `keycloak`           | Database user            |
| `POSTGRES_PASSWORD`      | `keycloak_secret_2024`| Database password       |
