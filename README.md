# BahariDevs Codex Build Specification

This repository package is the authoritative build brief for the **BahariDevs Limited** public website and service-management platform.

It replaces the original single oversized prompt with:
- durable project rules for Codex;
- product, architecture, design, security, data, testing, and deployment specifications;
- a sequenced task backlog with acceptance criteria and stop points;
- a starter prompt for beginning work safely.

## Read in this order

1. `AGENTS.md`
2. `docs/00_MASTER_PROJECT_SPEC.md`
3. `docs/09_DECISIONS_AND_OPEN_ITEMS.md`
4. `docs/10_RELEASE_PLAN.md`
5. `.agent/PLANS.md`
6. `tasks/README.md`
7. the single active task file

## Critical execution rule

Codex must complete **one task at a time**. It must not begin the next task until the owner has reviewed and explicitly approved the current task.

Every task ends with:

`TASK COMPLETE — AWAITING REVIEW`

## Recommended first command to Codex

Use the content in `CODEX_START_PROMPT.md`.

## Release reality

The requested target of **20 June 2026** is treated as a marketing-release target, not a credible deadline for the complete production service-management platform. See `docs/10_RELEASE_PLAN.md`.

## Source documents

The original brief is preserved at `source/ORIGINAL_PROMPT.md`. The clarified product decisions are recorded in `source/CLARIFICATION_ANSWERS.md`.
