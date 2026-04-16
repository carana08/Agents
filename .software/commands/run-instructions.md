---
description: Read and execute a Markdown instruction file
agent: read-instructions-agent
---

Read the Markdown instruction file located at `$ARGUMENTS`.

Treat it as an operational procedure to execute, not as passive documentation.

Follow this workflow:
- inspect the project and the file contents first
- extract the goal, prerequisites, steps, and expected outputs
- delegate specialized work to the correct agent when needed
- require a local `.venv` before Python dependency or test execution
- validate each major step before moving on
- report blockers clearly if the instruction cannot be executed safely
