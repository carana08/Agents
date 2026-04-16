# Feature: Deployment Preparation

## Purpose
Prepare and validate install, build, runtime, and deployment workflows for software projects built with Django, FastAPI, Flutter, and mixed web/mobile stacks.

## User Value
Reduce deployment friction and avoid failures caused by missing dependencies, invalid environment setup, broken runtimes, or inconsistent build steps.

## Scope
This feature covers:
- environment validation
- dependency installation guidance
- Python `.venv`-aware workflows
- Node and Flutter dependency workflows when applicable
- build readiness checks
- runtime readiness checks
- migration and static asset preparation guidance when relevant
- failure diagnosis by stage

## Inputs
- project repository
- dependency files
- package manager files
- environment assumptions
- requested build, run, or deploy goal

## Preconditions
- the repository root is identified
- required dependency files or project markers exist
- required interpreters or runtimes can be checked safely

## Expected Outputs
- validated install and build sequence
- identified required tools
- warnings about missing dependencies or configuration
- deployment-oriented command guidance
- safe sequencing of actions

## Artifacts Produced
- environment readiness notes
- build or deploy guidance
- blocker reports

## Agents and Skills Involved
- deployment-agent
- python-agent when Python execution details are needed
- django-agent when migrations or Django management steps are required
- dart-agent for Flutter-specific build or run context

## Execution Flow
1. Inspect the real project structure and stack markers.
2. Validate interpreters, runtimes, and local environment expectations.
3. Determine the correct package manager and build path.
4. Sequence setup, build, runtime, and migration steps safely.
5. Stop at the first hard prerequisite blocker.
6. Report the validated path or blocker state clearly.

## Constraints
- must inspect the real project structure first
- must prefer local isolated environments
- must not introduce unapproved dependencies or invent build steps

## Security Considerations
- must not expose secrets or real environment values
- must avoid global Python package installation
- must stop when prerequisite failures would make further execution unsafe

## Failure Conditions
- stop if the required runtime or interpreter is missing
- stop if Docker, database access, or required binaries are unavailable for dependent steps
- stop if the repository does not provide enough information to choose the correct build path safely

## Acceptance Criteria
- build and install workflow is reproducible
- stack assumptions are validated
- missing tools are identified clearly
- commands match the actual project structure
- hard blockers stop dependent execution

## Verification
- confirm the proposed workflow aligns with real project files and scripts
- confirm environment isolation rules are respected

## Non-Goals
- infrastructure architecture design
- unrelated feature implementation
