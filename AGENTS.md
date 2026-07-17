# AGENTS.md

This repository is the active workspace for MeetCombo infrastructure, automation, and agent orchestration.

## Source of truth

- GitHub is the source of truth for code and operating documents.
- The active repository is compose-for-agents.
- Keep the main branch aligned with the GitHub remote before making changes.

## Working rules for coding agents

1. Preserve history first.
   - Review git status, branch, and remote state before editing.
   - Do not mix documentation-only work with infrastructure changes in the same commit unless it is clearly required.

2. Keep the workflow separated.
   - Use documentation commits for history, handoff, and task tracking updates.
   - Use infrastructure commits for Docker, n8n, and agent-stack work.
   - Keep Raise Outside work out of scope for this repository tonight.

3. Prefer small, reviewable changes.
   - Add one focused change at a time.
   - Favor explicit configuration files over ad-hoc shell scripts.

4. Verify before finishing.
   - Run relevant validation commands, such as `docker compose -f compose.n8n.yaml config`.
   - Check git status before stopping.
   - Leave a clear handoff note with the next action.

## Current focus

- Capture the latest session history and handoff notes.
- Establish a local n8n foundation with persistent storage.
- Add a new coding agent alongside the existing tools rather than replacing them.
- Keep shared conventions in this file so Claude Code, Codex, and any future agents follow the same rules.
