# Task 03 — Design system and application shell

## Objective
Implement original reusable design foundations for public and authenticated experiences.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Tokens/themes
- Typography fallback
- layout primitives
- navigation/footer
- component primitives
- dark/light persistence
- accessibility states
- motion/reduced motion
- storybook-like component showcase route in local/dev only

## Non-goals
- No page-specific full content
- No copying inspiration sites

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Both themes pass contrast review
- Keyboard/focus behavior works
- No theme flash
- Components are responsive
- Production build passes
- Dev showcase is unavailable in production

## Validation
- Component rendering tests
- Theme behavior test
- Accessibility manual checklist
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after design-system review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
