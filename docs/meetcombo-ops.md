# MeetCombo operations (Raised Outside)

This note captures the operational setup for the MeetCombo Foundation automation work in the Compose for Agents repository.

## Source of truth

- GitHub remains the source of truth for code and operating documents.
- Repository: compose-for-agents
- Branch: main
- Remote: origin -> caleb6000-ship-it/compose-for-agents

## Verified runtime state

- Docker Desktop or Docker Engine is available locally.
- The n8n container is already running as `n8n`.
- n8n data is persisted in the `n8n_data` Docker volume.
- The local UI is available at http://localhost:5678.

## Local n8n stack

Use [compose.n8n.yaml](../compose.n8n.yaml) to start n8n locally:

1. `docker compose -f compose.n8n.yaml up -d`
2. Open http://localhost:5678
3. Set a strong encryption key via the `N8N_ENCRYPTION_KEY` environment variable before using the instance for real work.

### Persistence

The workflow data and credentials live in the Docker named volume `n8n_data` mounted at `/home/node/.n8n`. Restarting the container keeps that data intact as long as the volume remains present.

## Connecting n8n to MeetAgent

A simple local integration path is:

1. Use a Webhook or Schedule trigger in n8n.
2. Add an HTTP Request node that posts to the MeetAgent endpoint, for example `http://host.docker.internal:<port>/agents/meetagent/execute`.
3. Keep the endpoint URL and credentials in n8n's Credential Manager.
4. Return the agent output to the next workflow step or to a downstream notification.

If the MeetAgent service is running locally, `host.docker.internal` allows the n8n container to reach it from Docker Desktop.

## Adding Claude Code to the stack

Claude Code is being added as an additional coding agent alongside the existing GitHub, VS Code, Docker, and n8n workflow. It is not meant to replace those tools; it adds another authoring and orchestration path for repository tasks.

## Brand note

The correct brand name is Raised Outside. Raised Wild was used earlier but is not the active brand.
