# Task 01 — Repository foundation and quality gates

## Objective
Create the Laravel application foundation and reliable automated quality commands.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Laravel 13 project after preflight approval
- Livewire starter foundation
- Tailwind 4/Vite
- English locale and Dar es Salaam timezone
- MariaDB configuration template
- Pest/static analysis/formatting
- CI workflow
- health route
- safe `.env.example`
- basic roles enum

## Non-goals
- No public page build
- No domain migrations beyond essential identity foundation

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Fresh install succeeds
- Production asset build succeeds
- Baseline tests, formatter, and static analysis pass
- No public registration
- Admin 2FA capability is scaffolded but privileged user provisioning remains controlled
- AGENTS quality commands are updated

## Validation
- Bootstrap feature test
- Health route test
- Registration-disabled test
- CI run
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after the clean foundation and commands are demonstrated.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
