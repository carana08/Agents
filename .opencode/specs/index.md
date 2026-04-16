# Specs Index

Purpose: maintain a single source of truth for spec runs, active ownership, and conflict control.

## Status Model
- `Proposed`
- `In Progress`
- `Blocked`
- `Completed`
- `Superseded`
- `Deprecated`

Rules:
- Only one `In Progress` run is allowed per `feature_id` unless explicitly approved.
- A new run with overlapping `affected_paths` must be checked before execution.
- New runs do not overwrite old runs; they create a new timestamped folder under `specs/runs/`.
- If a run replaces a previous one, record the previous run in `supersedes`.

## Runs

| run_id | feature_id | status | primary_subagent | affected_paths | supersedes | folder |
| --- | --- | --- | --- | --- | --- | --- |

## Active Runs

Use this section to quickly list currently active runs.

- None

## Notes

- Update this file whenever `/new-spec` is executed.
- If a run is blocked, keep the entry and document blocker details in that run's `status.md`.
