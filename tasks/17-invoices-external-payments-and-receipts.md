# Task 17 — Invoices, external payment records, and receipts

## Objective
Implement invoices and receipt issuance without online payment processing.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Invoice lifecycle
- line snapshots
- manual external payment record
- receipt generation
- void/overdue behavior
- document numbering

## Non-goals
- No gateway
- No claim of TRA/EFD integration

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Issued documents immutable
- duplicate numbering prevented
- receipt requires recorded external payment
- tax wording configurable and legally gated
- audit complete

## Validation
- Numbering/concurrency tests
- document lifecycle tests
- money tests
- authorization tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop pending accounting/legal document review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
