# Task 22 — Security hardening

## Objective
Perform focused application security hardening and close launch risks.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Authorization matrix
- CSP/headers
- rate limits
- session/cookie settings
- dependency audit
- upload tests
- webhook tests
- logging review
- admin override review

## Non-goals
- No feature expansion

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- No known critical/high findings
- debug/secrets absent
- security headers verified
- guest/private boundaries reviewed
- remediation evidence recorded

## Validation
- Full test suite
- security regression tests
- manual attack checklist
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop at security approval gate.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
