# CLAUDE.md

This file contains Claude Code-specific guidance for the compose-for-agents repository.

## Primary rule

Use AGENTS.md as the shared source of truth for repository conventions.

## Scope

Focus on the MeetCombo Foundation work in this repository:

- documentation handoff and history updates
- local n8n foundation setup
- agent-stack documentation and coordination

## Workflow

1. Review git status and branch state before changes.
2. Keep documentation changes separate from infrastructure changes.
3. Prefer small, testable commits.
4. Verify with `docker compose -f compose.n8n.yaml config` when changing the n8n setup.
5. Leave a clear handoff note before stopping.
