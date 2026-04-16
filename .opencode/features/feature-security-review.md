# Feature: Security Review

## Purpose
Provide focused review of secrets exposure, unsafe configuration, validation gaps, SQL injection risk, and auth-sensitive areas across Django, FastAPI, Flutter-connected flows, and deployment workflows.

## User Value
Reduce security regressions before release and help teams detect high-risk issues earlier in the delivery lifecycle.

## Scope
This feature covers:
- secret exposure review
- insecure configuration review
- auth and permission review
- input validation review
- SQL injection risk awareness
- sensitive logging and error exposure review

## Inputs
- repository or module under review
- relevant settings, routes, models, services, or configs
- known sensitive workflows when available

## Preconditions
- the review scope is identified
- repository context exists for the sensitive area under review

## Expected Outputs
- security findings
- severity-aware risks
- practical remediation guidance
- blocked assumptions called out explicitly

## Artifacts Produced
- review findings
- remediation notes
- follow-up recommendations for tests or hardening

## Agents and Skills Involved
- security-agent
- django-agent or python-agent when framework-specific implementation context is required

## Execution Flow
1. Inspect the scoped target area.
2. Identify secret, auth, validation, and config-sensitive surfaces.
3. Evaluate likely risk categories.
4. Report concrete findings and practical fixes.
5. Flag unresolved assumptions or missing context.

## Constraints
- must stay focused on the scoped review target
- must not expose sensitive values
- should prioritize practical remediation over abstract theory

## Security Considerations
- this feature itself must never reveal the sensitive values it reviews
- placeholders and redactions should be used wherever needed

## Failure Conditions
- stop if the scope is too broad to review meaningfully
- stop if required files or context are missing and findings would become speculative

## Acceptance Criteria
- findings are concrete and scoped
- risk categories are explicit
- remediation guidance is practical
- no secrets are exposed during the review

## Verification
- confirm findings refer to the real files or flows under review
- confirm the output remains redacted and actionable

## Non-Goals
- full feature implementation
- general architecture redesign unrelated to the scoped security concern
