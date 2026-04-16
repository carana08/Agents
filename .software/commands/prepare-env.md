---
description: Prepare a safe project environment
agent: deployment-agent
---

Inspect the current project and prepare its execution environment safely.

Rules:
- detect the real stack before choosing commands
- if the project uses Python, always create and use a local `.venv` in the project root
- never install Python packages globally
- use the project's real dependency files and lockfiles
- prefer reproducible install commands
- validate that the environment is usable at the end
