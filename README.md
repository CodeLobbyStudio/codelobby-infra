
## Lokalny PostgreSQL

Baza danych CodeLobby działa w Dockerze, niezależnie od innych projektów.

### Wymagania
- Docker Desktop
- Docker Compose

### Pierwsze uruchomienie

Skopiuj przykładową konfigurację:

    Copy-Item .env.example .env

W pliku `.env` ustaw własne hasło PostgreSQL.

Uruchom bazę:

    docker compose --env-file .env -f local/compose.yaml up -d

### Sprawdzenie statusu

    docker compose --env-file .env -f local/compose.yaml ps

Kontener powinien mieć status `healthy`.

### Połączenie z bazą

    docker compose --env-file .env -f local/compose.yaml exec postgres psql -U codelobby -d codelobby

### Zatrzymanie bazy

    docker compose --env-file .env -f local/compose.yaml stop

### Ponowne uruchomienie

    docker compose --env-file .env -f local/compose.yaml start

### Konfiguracja połączenia

Host: 127.0.0.1
Port: 55433
Database: codelobby
Username: codelobby
Password: wartość z lokalnego pliku .env

Dane PostgreSQL są przechowywane w osobnym wolumenie Dockera.

Nie używaj `docker compose down -v`, jeśli chcesz zachować dane.



# CodeLobby Infrastructure

Infrastructure and deployment configuration for **CodeLobby**.

## Responsibilities

This repository will contain configuration for running the CodeLobby services together, including:

- local development infrastructure
- container orchestration
- service networking
- database and queue configuration
- deployment configuration
- reverse proxy and TLS configuration
- monitoring and observability configuration
- runner infrastructure and resource limits

## Services

The target system consists of:

- `codelobby-web`
- `codelobby-backend`
- `codelobby-runner`
- PostgreSQL
- a submission queue / broker when introduced

## Security

Do **not** commit secrets to this repository.

Keep credentials such as database passwords, API keys, signing secrets and deployment keys in environment variables or GitHub Secrets. Commit only safe example configuration such as `.env.example`.

## Development workflow

Track infrastructure work in the **CodeLobby Development** GitHub Project. Use focused Issues, feature branches and reviewed Pull Requests targeting `main`.

> Early-stage project. Infrastructure will be introduced incrementally as the first end-to-end MVP is implemented.
