# Task 14 — Request communication threads

## Objective
Implement public messages, internal notes, technician notes, attachments, and timeline views.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Message types/visibility
- guest replies
- admin/staff/technician UI
- append-only/redaction rules
- timeline
- safe notifications events

## Non-goals
- No live provider inbound integration yet
- No internal note external delivery

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Visibility matrix enforced server-side
- internal notes never serialize to guest
- message corrections audited
- safe attachment rules reused

## Validation
- Visibility tests
- serialization tests
- redaction/audit tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after privacy review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
