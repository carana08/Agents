# Roadmap

## Purpose
Define a Spec-Driven Development (SDD) execution flow for OpenCode where each phase is evaluated through explicit decision gates, not arbitrary agent behavior.

## Phase 1: Align Specs and Scope
Goal: load and align project intent before any implementation activity.

### Decision Gate 1.1: specification readiness
Question: are core governing artifacts complete?
- [ ] Complete and accepted (`mission`, `constitution`, `tech-stack`, feature file exists)
- [ ] Partially complete (one or more missing sections)
- [ ] Not defined

Action:
- If `[x] Complete and accepted`: continue to Phase 2.
- If `[x] Partially complete`: block implementation and create missing spec sections.
- If `[x] Not defined`: stop and request specification definition before planning.

### Decision Gate 1.2: scope clarity
Question: is the requested work inside an approved feature?
- [ ] Yes, exactly one feature
- [ ] Yes, but crosses multiple features
- [ ] No approved feature found

Action:
- If `[x] Yes, exactly one feature`: continue with that feature as active scope.
- If `[x] Yes, but crosses multiple features`: split into sub-features and assign ownership boundaries.
- If `[x] No approved feature found`: create or refine feature definition first.

## Phase 2: Create Spec Run and Task Assignment
Goal: create an isolated timestamped spec run and map ownership before environment changes or coding.

### Decision Gate 2.1: run creation
Question: was a new run created under `specs/runs/YYYY-MM-DD-HHMM-<slug>/`?
- [ ] Yes
- [ ] Partial
- [ ] No

Action:
- If `[x] Yes`: continue to Gate 2.2.
- If `[x] Partial`: complete missing run artifacts before continuing.
- If `[x] No`: execute `/new-spec` and block implementation until run exists.

### Decision Gate 2.2: index and conflict validation
Question: is the run registered in `specs/index.md` and conflict-checked?
- [ ] Yes, registered and no conflict
- [ ] Registered but blocked by conflict
- [ ] Not registered

Action:
- If `[x] Yes, registered and no conflict`: continue to Phase 3.
- If `[x] Registered but blocked by conflict`: stop and resolve conflict before execution.
- If `[x] Not registered`: update `specs/index.md` before continuing.

### Decision Gate 2.3: subagent assignment
Question: does the run task define one primary subagent owner?
- [ ] Yes
- [ ] Partial
- [ ] No

Action:
- If `[x] Yes`: continue to Phase 3.
- If `[x] Partial`: resolve shared ownership and keep one primary owner.
- If `[x] No`: assign primary owner in `task.md` before continuing.

## Phase 3: Environment and Tooling Setup
Goal: prepare required tools and execution environment based on approved specs and stack policy.

### Decision Gate 3.1: tooling readiness
Question: are required tools and environments available and aligned with `tech-stack`?
- [ ] Yes, all required tooling is available and compatible
- [ ] Partially, some tools or environment pieces are missing
- [ ] No, critical tooling is missing

Action:
- If `[x] Yes, all required tooling is available and compatible`: continue to Phase 4.
- If `[x] Partially, some tools or environment pieces are missing`: configure missing tooling and document setup steps.
- If `[x] No, critical tooling is missing`: stop and request prerequisite installation or availability before continuing.

### Decision Gate 3.2: version compatibility
Question: are tool and framework versions compatible with repository manifests and lockfiles?
- [ ] Compatible
- [ ] Uncertain
- [ ] Incompatible

Action:
- If `[x] Compatible`: continue.
- If `[x] Uncertain`: consult `context7`, document findings, and resolve uncertainty.
- If `[x] Incompatible`: block setup and request explicit approval for version strategy.

## Phase 4: Implementation
Goal: execute approved feature work using the configured environment and routing ownership.

### Decision Gate 4.1: implementation readiness
Question: is implementation scope clear and mapped to accepted feature files?
- [ ] Yes, scope is clear and traceable
- [ ] Partially, some implementation details are ambiguous
- [ ] No, implementation scope is not ready

Action:
- If `[x] Yes, scope is clear and traceable`: continue implementation.
- If `[x] Partially, some implementation details are ambiguous`: resolve ambiguities against features and specs before coding.
- If `[x] No, implementation scope is not ready`: stop and refine feature definition first.

### Decision Gate 4.2: routing and ownership
Question: is each implementation step assigned to the most specific owner?
- [ ] Yes (Django/FastAPI/Flutter/deployment/security ownership is explicit)
- [ ] Partially (some shared ambiguity)
- [ ] No

Action:
- If `[x] Yes`: continue coding and integration.
- If `[x] Partially`: resolve overlaps and define single ownership per task.
- If `[x] No`: stop and reroute before coding.

## Phase 5: Build and Deployment Readiness
Goal: ensure the implemented solution is buildable and deployable across required surfaces.

### Decision Gate 5.1: prerequisite readiness
Question: are build and deployment prerequisites available (Python, `.venv`, Docker, DB, SDKs, required binaries)?
- [ ] All available
- [ ] Partially available
- [ ] Missing critical prerequisites

Action:
- If `[x] All available`: continue build and deployment validation.
- If `[x] Partially available`: validate available surfaces and mark blocked surfaces explicitly.
- If `[x] Missing critical prerequisites`: stop dependent execution and report blocker.

### Decision Gate 5.2: dependency policy
Question: does build or deployment require a new or replacement dependency?
- [ ] No new dependency needed
- [ ] Maybe needed
- [ ] Definitely needed

Action:
- If `[x] No new dependency needed`: continue.
- If `[x] Maybe needed`: pause and evaluate against `tech-stack` and accepted `research`.
- If `[x] Definitely needed`: request explicit approval before installing or replacing dependencies.

## Phase 6: Testing and Security Validation
Goal: validate behavior, contracts, quality, and security expectations before release.

### Decision Gate 6.1: verification completeness
Question: were required tests and security checks executed for all affected stack surfaces?
- [ ] Yes
- [ ] Partial
- [ ] No

Action:
- If `[x] Yes`: continue to delivery.
- If `[x] Partial`: list missing checks and keep status as partial.
- If `[x] No`: no completion claim allowed.

### Decision Gate 6.2: result status
Question: what is the validation outcome?
- [ ] Passed
- [ ] Blocked by environment or external dependency
- [ ] Failed by implementation defect

Action:
- If `[x] Passed`: deliver with evidence.
- If `[x] Blocked by environment or external dependency`: deliver blocker report with next required action.
- If `[x] Failed by implementation defect`: open fix loop with targeted defect tasks.

## Phase 7: Documentation and Diagrams
Goal: finalize project knowledge artifacts after validated implementation.

### Decision Gate 7.1: documentation completeness
Question: are required technical and user-facing docs updated?
- [ ] Yes
- [ ] Partial
- [ ] No

Action:
- If `[x] Yes`: continue to diagram and final delivery.
- If `[x] Partial`: complete missing documentation sections before final close.
- If `[x] No`: block final close and generate required docs.

### Decision Gate 7.2: architecture and flow diagrams
Question: are required architecture and flow diagrams generated and aligned with final implementation?
- [ ] Yes
- [ ] Partial
- [ ] No

Action:
- If `[x] Yes`: finalize delivery package.
- If `[x] Partial`: generate missing diagrams and link them to docs.
- If `[x] No`: block final close and create required diagrams.

## OpenCode Automation Contract
For each execution cycle, produce these artifacts in order:
1. Active feature reference and scope statement.
2. `run_id` and run folder path under `specs/runs/`.
3. `specs/index.md` entry and conflict status.
4. Decision-gate responses by phase with one selected checkbox per gate.
5. Agent ownership map by task and stack surface.
6. Implementation, build, and deployment log.
7. Test and security validation evidence.
8. Documentation and diagram evidence.
9. Final status with pass or blocker outcome.

The agent must not skip gates, silently broaden scope, or claim completion without a final gate status.

## Definition of Done
- Governing specs exist and are consistent.
- Active feature is implemented within approved scope.
- A timestamped run exists and is registered in `specs/index.md`.
- All required gates are resolved with explicit outcomes.
- Build and deployment readiness is validated or blockers are documented.
- Testing and security validation is passed or blockers are documented.
- Required documentation and diagrams are delivered.
- No unapproved dependency, hidden behavior, or secret exposure was introduced.

## Task Artifact Contract
Before implementation starts, create or update a task artifact under `tasks/` using `tasks/task.md`.

Required for each task:
- one active feature link
- one primary subagent assignment
- explicit execution checklist
- explicit validation checklist
- blocker and evidence sections

A task is execution-ready only when one option is selected in each applicable gate and subagent ownership is explicit.
