# Task 13 — Scheduling, service zones, travel fees, and conflicts

## Objective
Implement requested/configured slots, admin confirmation, travel zones, and double-booking prevention.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Appointments
- business hours
- configured public slots
- admin scheduling
- zones/fee snapshots
- remote/on-site/workshop modes
- reschedule/cancel
- conflict transaction

## Non-goals
- No automated technician assignment
- No GPS

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Overlaps blocked for assigned technicians
- timezone correct
- admin override requires reason
- fee snapshot survives later rule changes
- public slot does not expose technician identity

## Validation
- Timezone/DST-neutral tests
- conflict/concurrency tests
- zone fee tests
- authorization tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after calendar and conflict review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
