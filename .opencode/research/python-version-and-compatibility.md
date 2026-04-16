# Research: Python Version and Compatibility

## Context
The delivery assistant needs safe Python environment behavior. Missing or incompatible runtimes were already identified as a source of unsafe workarounds and unreliable setup flows.

## Question
How should Python runtime selection and environment isolation be handled across projects?

## Options Considered
- Option A: rely on whatever global Python is available
- Option B: require a compatible interpreter and always use a local `.venv`
- Option C: install dependencies globally when `.venv` is inconvenient

## Evaluation Criteria
- security
- compatibility
- reproducibility
- maintainability
- implementation complexity

## Findings
- Global Python usage increases contamination risk and makes reproducibility weaker.
- Installing dependencies globally to bypass environment issues is unsafe.
- Requiring a compatible interpreter first and then using a local `.venv` is the safest and most reproducible approach.

## Decision
Require a compatible Python interpreter and always prefer a project-local `.venv`.

## Rationale
This aligns with the repository's current deployment and Python agent rules and reduces system contamination risk.

## Constraints
- If Python is missing, execution must stop until the runtime is installed.
- The agent must not bootstrap project dependencies into the system interpreter.

## Implications
- `deployment-agent` must verify interpreter compatibility before `.venv` creation.
- `python-agent` must prefer `.venv/bin/python` or isolated runners.
- Runbooks should stop early if Python is unavailable.

## Validation
- Confirm that Python setup flows stop when the runtime is missing.
- Confirm that commands are executed through `.venv` when Python work proceeds.

## Status
Accepted
