# Task 12 — Technician specialties and assignments

## Objective
Implement lead/supporting technician assignment with history and least-privilege views.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Specialties
- lead/supporting assignments
- reassignment history
- technician assigned-items UI
- staff/admin assignment boundaries

## Non-goals
- No automated assignment
- No GPS
- No technician availability profile

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- One active lead per item
- supporting assignments work
- unassigned data hidden
- reassignment audited
- specialty warning behavior documented

## Validation
- Assignment constraint tests
- technician visibility tests
- reassignment tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after operational review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
