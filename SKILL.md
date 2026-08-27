---
name: digital-twin-runner-workspace
description: Maintain a runner-owned Git workspace for one digital-twin persona, including non-secret resource links and durable persona memory. Use when creating, reviewing, or editing the runner resources repository for a persona; never use for author page configuration or secrets.
---

# AI Persona Runner Workspace

Maintain one private runner workspace for one persona. This repository belongs to the runner, not the persona author and not the authored page configuration.

## Canonical files

- `/assets/runner-workspace.json` contains the workspace's non-secret resource links and editable non-secret settings.
- `/memory/persona-memory.json` contains durable runner memory for this persona.

Preserve `schemaVersion`, `workspaceId`, and `pageId`. Treat resource identifiers, provider state, and credentials as server-managed. Never commit API keys, tokens, passwords, OAuth credentials, or any secret.

Do not add `assets/chat-config.json` to this repository. The author-owned `digital-twin-page` repository remains the source of page profile and published chat configuration.

## Sync behavior

Use Push to write the server's current runner resources and memory to Git. Use Pull to restore the manifest and memory after validation. Git controls only the runner workspace; it never changes the author-owned persona configuration.
