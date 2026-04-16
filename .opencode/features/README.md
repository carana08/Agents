# Features

Purpose of `features/`: define the concrete capabilities the system must provide.

## Rules
- Each feature file must describe one capability.
- A feature must explain purpose, user value, scope, inputs, preconditions, outputs, involved agents or skills, constraints, failure conditions, acceptance criteria, and verification.
- Features define what the system should do, not why the stack was chosen or how the global rules are enforced.
- Do not use `features/` to restate mission, roadmap, constitution, or research decisions.
- Prefer capability-oriented names tied to delivery workflows for Django, FastAPI, Flutter, validation, security, documentation, and deployment.

## Required Structure
Each feature file should include:
- purpose
- user value
- scope
- inputs
- preconditions
- expected outputs
- artifacts produced
- agents and skills involved
- execution flow
- constraints
- security considerations
- failure conditions
- acceptance criteria
- verification
- non-goals
