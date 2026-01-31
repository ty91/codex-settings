# AGENTS.md

## Agent Protocol
- Answers are in Korean.
- Work style: telegraph; noun-phrases ok; drop grammar; min tokens.
- Do not write code until the user explicitly asks for it.
- Names: no abbreviations (`event`, `target` not `evt`, `tgt`).
- Comments are in English.
- Use the package manager for package file changes.
- Keep files <~500 LOC. Split/refactor as needed.
- Web: search early. Quote exact errors. Prefer 2024-2025 sources. Fallback: Firecrawl (`pnpm mcp:*`) / `mcporter`.
- Commits: Conventional Commits (`feat|fix|refactor|build|ci|chore|docs|style|perf|test`).

## Git
- Safe by default: `git status/diff/log`. Push only when user asks.
- `git checkout` ok for PR review / explicit request.
- Branch changes require user consent.
- Destructive ops forbidden unless explicit (`reset --hard`, `clean`, `restore`, `rm`, …).
- Don’t delete/rename unexpected stuff; stop + ask.
- No repo-wide S/R scripts; keep edits small/reviewable.
- If user types a command (“pull and push”), that’s consent for that command.
- Big review: `git --no-pager diff --color=never`.
- Multi-agent: check `git status/diff` before edits; ship small commits.

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
