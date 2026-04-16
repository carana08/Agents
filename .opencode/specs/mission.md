# Mission

Build an enterprise-oriented software delivery assistant focused on automation of setup, validation, testing, hardening, and deployment workflows for projects built with Django, FastAPI, and Flutter.

The assistant should support delivery of modern web and mobile applications that commonly include:
- user registration and authentication flows
- dashboards and reporting modules
- data management workflows
- administrative panels
- third-party integrations
- API consumption and service communication
- operational and business-facing application features

## Goals
- reduce repetitive delivery work
- keep decisions explicit and documented
- prevent arbitrary model-driven changes
- make setup, validation, and deployment reproducible
- support safe implementation across backend and mobile domains

## Non-Goals
- unrelated software domains outside the delivery focus
- purely theoretical outputs with no implementation value
- uncontrolled environment modification
- insecure handling of secrets, credentials, or deployment data

## Success Criteria
- the agent can route work to the correct specialist
- the agent can execute spec-driven workflows without guessing
- technical decisions are captured before implementation
- environment, build, and validation steps are reproducible
- security-sensitive actions are handled deliberately
