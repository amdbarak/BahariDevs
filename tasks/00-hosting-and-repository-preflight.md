# Task 00 — Hosting and repository preflight

## Objective
Verify the deployment environment and existing repository before architectural bootstrap.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Inventory repository state and branches
- Verify host PHP, CLI PHP, extensions, MariaDB, Composer, Node/npm, cron, process support, web root, symlinks, storage, TLS, outbound APIs and staging
- Document build/deploy constraints
- Create an environment capability matrix and blockers

## Non-goals
- No product feature implementation
- No provider credential collection in source control

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- A completed capability matrix exists
- Every unverified capability is marked unknown rather than assumed
- Recommended PHP/MariaDB baseline is confirmed or adjusted through an ADR
- The next task has an executable setup path

## Validation
- Safe read-only environment/repository checks
- No secrets printed
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after reporting verified facts, blockers, and the recommended bootstrap configuration.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
