# Task 10 — Private file management

## Objective
Implement secure customer attachments and completion-file foundations.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Private disks
- metadata
- MIME/size/count validation
- authorized downloads
- quarantine/scan adapter
- audit
- purge hooks

## Non-goals
- No public request uploads
- No SVG/HTML/executable customer uploads

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Unauthorized download fails
- mismatched MIME rejected
- stored name is generated
- original name safe in metadata
- private files not web-addressable

## Validation
- Upload/download authorization tests
- malicious fixture tests
- purge tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after file-security review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
