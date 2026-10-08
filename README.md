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
