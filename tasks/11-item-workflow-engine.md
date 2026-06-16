# Task 11 — Service-item workflow engine

## Objective
Implement the strict item lifecycle and parent aggregate status.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Enums
- transition service
- guards/reasons/evidence
- on hold/resume
- cancel/reject/reopen
- aggregate status
- optimistic concurrency
- events/audit

## Non-goals
- No arbitrary status dropdown writes
- No notification provider work

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- No state skipping
- actor rules enforced
- parent reflects mixed item states
- concurrent stale transition rejected
- full history preserved

## Validation
- Transition matrix tests
- actor authorization tests
- concurrency tests
- aggregate tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after workflow matrix review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
