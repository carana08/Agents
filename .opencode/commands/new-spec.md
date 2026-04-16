---
description: Create a new timestamped spec run and task assignment
agent: software-orchestrator
---

Create a new spec run for `$ARGUMENTS` using Spec-Driven Development.

Execution contract:
- parse `$ARGUMENTS` into a feature name and slug
- generate `run_id` as `YYYY-MM-DD-HHMM-<slug>`
- create `specs/runs/<run_id>/`
- create these files inside that run:
  - `spec.md`
  - `task.md`
  - `decisions.md`
  - `execution-log.md`
  - `status.md`

Before creating the run, validate against `specs/index.md`:
- detect active specs with overlapping `affected_paths`
- detect an already active run for the same `feature_id`
- detect incompatibility with `specs/constitution.md` or `specs/tech-stack.md`

Conflict behavior:
- if conflict exists, do not start implementation
- still register the run in `specs/index.md` with `status: Blocked`
- write conflict details in `specs/runs/<run_id>/status.md`

No-conflict behavior:
- register the run in `specs/index.md` with `status: In Progress`
- create `task.md` from `tasks/task.md` structure
- assign one primary subagent based on ownership rules (Django, FastAPI/Python, Flutter, deployment, security, documentation, architecture)
- keep implementation blocked until one option is selected per required roadmap gate

Required outputs:
1. run id and folder path
2. index update entry
3. selected primary subagent
4. initial checklist and blocker state

Do not install dependencies or modify runtime environments unless explicitly requested after spec creation.
