# Spec Runs

Each run is isolated in its own timestamped folder:

`specs/runs/YYYY-MM-DD-HHMM-<slug>/`

Minimum files per run:
- `spec.md`
- `task.md`
- `decisions.md`
- `execution-log.md`
- `status.md`

Why this exists:
- preserve history of each spec execution
- prevent accidental overwrite between consecutive specs
- allow blocker-first execution without losing traceability

A run is execution-ready only when:
- it is registered in `specs/index.md`
- it has one primary subagent assignment in `task.md`
- roadmap gates for current phase have an explicit `[x]` selection
