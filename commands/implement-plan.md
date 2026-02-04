---
description: Execute approved implementation plans phase by phase
---

# Implement Plan

You are responsible for executing the approved plan in `PLAN.md`. Use phase checkboxes to drive progress.

## Context

- Plan file: `.tasks/<git-branch-name>/plan.md`
- `git-branch-name` uses `-` instead of `/`

## Process

1. Read the plan file first. If the plan file is missing, inform the user and suggest running `/create-plan`.
2. Locate phase headers with checkboxes (`## - [ ] Phase N: ...`).
3. Find the first unchecked phase and work on it next.
4. Do not skip unchecked phases.
5. After completing a phase, run full gate (lint/typecheck/tests).
6. Mark satisfied success criteria with (`[x]`) and only consider a phase complete when all success criteria are satisfied.
7. Create commit(s) for the completed phase.
8. Mark its checkbox as checked (`- [x]`).
9. If a phase requires manual verification, pause and ask for user confirmation before proceeding.
10. When no unchecked phases remain, report completion.
