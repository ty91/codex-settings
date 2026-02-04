---
name: pr
description: Create a GitHub PR
---

# GitHub PR

## Overview

Create a PR via `gh` with strict template requirements and preflight git context checks.

## Workflow

### 1. Gather Context

Run:
- `git status`
- `git diff HEAD`
- `git branch --show-current`
- `git log --oneline -10`

### 2. Ensure Remote Branch

Check whether the current branch has an upstream.
If missing, push and set upstream (e.g., `git push -u origin <branch>`).

### 3. Create PR

Create PR with `gh pr create` and assign to `@me`.

Enforce:
- PR title: Conventional Commits style.
- PR body: exactly three H2 sections: `Summary`, `Changes`, `Test plan`.
- Body text in Korean; keep only title and section headings in English.
- If branch name looks like an issue number, mention it in `Summary`.
- `Test plan`: list reviewer-run checks as task list items; if none, leave section empty.
