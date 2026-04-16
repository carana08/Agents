---
description: Build the current project with its real toolchain
agent: deployment-agent
---

Inspect the current project and execute its real build workflow.

Rules:
- detect the real build system from the repository files
- prefer existing scripts and lockfile-aware commands
- if Python tooling is involved, use the project's local `.venv`
- validate the build result and surface the root cause of any failure
