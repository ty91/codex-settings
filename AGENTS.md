# AGENTS.md

## Agent Protocol
- Answers are in Korean.
- Comments in code are in English.
- Work style: telegraph; noun-phrases ok; drop grammar; min tokens.
- Do not write code until the user explicitly asks for it.
- Use the package manager for package file changes.
- Bugs: add regression test when it fits.
- Keep files <~500 LOC. Split/refactor as needed.
- Commits: Conventional Commits (`feat|fix|refactor|build|ci|chore|docs|style|perf|test`).
- Prefer end-to-end verify; if blocked, say what's missing.
- Web: search early. Quote exact errors. Prefer 2024-2025 sources. Fallback: Firecrawl (`pnpm mcp:*`) / `mcporter`.

## Build / Test
- Before handoff: run full gate (lint/typecheck/tests).

## Git
- Safe by default: `git status/diff/log`. Push only when user asks.
- If no explicit request, write the commit message yourself.
- `git checkout` ok for PR review / explicit request.
- Branch changes require user consent.
- Destructive ops forbidden unless explicit (`reset --hard`, `clean`, `restore`, `rm`, …).
- Don’t delete/rename unexpected stuff; stop + ask.
- No repo-wide S/R scripts; keep edits small/reviewable.
- If user types a command (“pull and push”), that’s consent for that command.
- Big review: `git --no-pager diff --color=never`.
- Multi-agent: check `git status/diff` before edits; ship small commits.
- For `git push` and `rm`, request escalated permissions before execution.

## Language/Stack Notes
- TypeScript: keep files small; follow existing patterns.

## Critical Thinking
- Fix root cause (not band-aid).
- Unsure: read more code; if still stuck, ask w/ short options.
- Conflicts: call out; pick safer path.
- Unrecognized changes: assume other agent; keep going; focus your changes. If it causes issues, stop + ask user.
- Leave breadcrumb notes in thread.

## Tools

### gh
- Use `gh` as the default interface for GitHub work (PRs, reviews, and CI status).

### uv
- Python deps: use `uv` only.

### pnpm
- JavaScript/TypeScript deps: use `pnpm` only.
