# Feature: API Validation

## Purpose
Provide reusable validation of API endpoints, request and response behavior, payload consistency, and integration expectations.

## User Value
Improve reliability and consistency across backend and client-side API usage.

## Scope
This feature covers:
- endpoint behavior review
- request validation
- response validation
- status code checks
- error handling checks
- auth and permission expectation checks
- backend and frontend API alignment

## Inputs
- endpoint definitions
- request and response examples
- backend code or route handlers
- API contracts or schemas when available

## Preconditions
- the target endpoint or contract is identified
- sufficient route or schema context exists
- implementation ownership boundaries are clear

## Expected Outputs
- validation findings
- contract consistency review
- identified risks or missing checks
- suggestions for tests or improvements

## Artifacts Produced
- validation reports
- review notes
- implementation recommendations scoped to the API contract

## Agents and Skills Involved
- django-agent
- python-agent
- fastapi skill
- api-validation skill
- flutter skill when client behavior is involved

## Execution Flow
1. Inspect the relevant endpoint or contract.
2. Separate implementation concerns from contract concerns.
3. Validate request and response behavior.
4. Validate status codes, error handling, and auth expectations.
5. Report findings and follow-up actions.

## Constraints
- must distinguish backend implementation concerns from contract-level review
- must not expose secrets or sensitive auth values

## Security Considerations
- treat authentication, authorization, and sensitive payload handling as explicit review areas
- do not print real credentials, secrets, or production tokens

## Failure Conditions
- stop if the contract target is too ambiguous to identify
- stop if assumptions about auth or payload shape would dominate the review

## Acceptance Criteria
- status codes are reviewed
- payload structure is reviewed
- error handling is checked
- auth expectations are considered
- integration relevance is explicit

## Verification
- confirm findings refer to the real endpoint or schema
- confirm contract-level issues are separated from broader implementation work

## Non-Goals
- full feature implementation
- unrelated UI generation
