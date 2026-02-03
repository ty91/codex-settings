---
description: Create a GitHub PR
---

## Instructions

### Step 1 - Context Gathering
- Run: `git status`, `git diff HEAD`, `git branch --show-current`, `git log --oneline -10`.

### Step 2 - Remote Branch Check/Create
- Check whether current branch is pushed to remote.
- If not pushed, create remote branch and push.

### Step 3 - PR Creation
- Create PR with `gh` and assign to `@me`.
- Use Conventional Commits style for PR title.
- PR body must have exactly three level-2 sections: Summary, Changes, Test plan.
- Write body content in Korean; keep only PR title and section headings in English.
- If branch name looks like an issue number, mention it in Summary.
- In Test plan, list reviewer-run checks as task list items; if none, leave it empty.
