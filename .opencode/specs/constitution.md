# Constitution

## Purpose
Establish the non-negotiable operating rules for this repository so that agents do not make arbitrary technical, dependency, environment, or execution decisions outside the defined spec-driven process.

## Constitutional Principles
1. Specification before implementation.
2. Explicit decisions before arbitrary execution.
3. Reproducibility before convenience.
4. Isolation before global modification.
5. Verification before completion claims.
6. Security before automation speed.
7. Specialist routing before generic execution.

## Artifact Hierarchy
When there is a conflict, prefer the highest-level artifact first:
1. `specs/constitution.md`
2. `specs/mission.md`
3. `specs/tech-stack.md`
4. `features/*.md`
5. `research/*.md`
6. `agents/AGENTS.md`
7. `commands/*.md`
8. `agent-memory/*.md`
9. implementation under `src/`

## Non-Negotiables
1. No implementation without an active spec or feature.
2. No feature without a clear goal, scope, and acceptance criteria.
3. No new dependency without explicit authorization in the active spec, feature, or accepted research.
4. No replacement of an approved tool or library with a similar one unless the change is explicitly justified and accepted.
5. No global installation when a local isolated environment is possible.
6. No hidden behavior that is not reflected in the governing spec artifacts.
7. No progress past a hard prerequisite failure.
8. No exposure of secrets, credentials, tokens, or `.env` values.
9. No silent broadening of scope by agents, skills, or commands.
10. No completion claim without verification or an explicit blocker report.

## Delivery Order
1. Mission
2. Constitution
3. Tech stack
4. Feature specification
5. Research and evidence
6. Task breakdown
7. Implementation
8. Verification
9. Delivery summary

## Decision Rules
- If documentation and repository state conflict, the repository state wins and the mismatch must be reported.
- If version-sensitive guidance is needed, use `context7` and align with the project's declared versions.
- If Python is required but missing, request Python installation before any `.venv` setup.
- If Docker, database access, or required binaries are missing, stop dependent work and report the blocker.
- If a capability crosses multiple domains, route ownership to the most specific agent for each step.
- If an assumption would materially affect implementation, report it instead of guessing through it.

## Dependency Rules
- Prefer the dependency manifests and lockfiles declared by the target project.
- Do not add packages because they are convenient unless the active spec or accepted research authorizes them.
- Do not use unpinned or open-ended versions when the project expects reproducibility.
- Do not install Python packages into the system interpreter for project work.

## Environment Rules
- Prefer project-local isolated environments.
- For Python work, prefer a local `.venv`.
- Validate interpreters, required tools, and service prerequisites before dependency installation or execution.
- If the local environment is corrupted, recreate the isolated environment rather than mutating the host setup.

## Routing Rules
- The orchestrator routes; it should not absorb specialist work by default.
- Specialists own their framework or delivery boundary.
- Skills provide reusable capabilities; they do not replace framework ownership.
- Commands must remain aligned with the governing specs and accepted research.

## Research Rules
- `research/` exists to justify technical decisions, not to redefine mission, roadmap, or constitution.
- Accepted research informs planning and implementation.
- Research may be superseded only with explicit justification and a new accepted decision.

## Feature Rules
- `features/` defines capabilities the system must provide.
- A feature must define scope, inputs, preconditions, outputs, constraints, failure conditions, acceptance criteria, and verification.
- Implementation must remain traceable to one or more feature files.

## Security Rules
- Never print or persist secrets in generated outputs, logs, examples, or documentation.
- Treat auth, permissions, secrets, validation, and unsafe configuration as explicit risk areas.
- Prefer practical remediation guidance over vague security commentary.

## Verification Rules
- A step is not complete until it is verified or explicitly blocked.
- Verification should use the real project structure, commands, tests, and runtime checks when available.
- If verification cannot run, the reason must be stated clearly.

## Definition of Done
Work is done only when:
- the governing spec exists
- the implementation matches the relevant spec and feature
- no unapproved dependency or hidden behavior was introduced
- the required verification passed, or the blocker is documented clearly
- the result can be explained without ambiguity against the project artifacts

## Quality Rules
- Prefer reproducible commands.
- Prefer clear acceptance criteria.
- Prefer explicit boundaries over implied behavior.
- Prefer small, testable tasks over broad, ambiguous instructions.
- Prefer blocker reporting over speculative continuation.
