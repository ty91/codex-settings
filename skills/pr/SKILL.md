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
- PR body: use the template below verbatim (keep headings and checklist items).
- Body text in Korean; keep only title and section headings in English (emojis ok).
- If branch name looks like an issue number, mention it in `Related Issue` (e.g., `Fixes TN-123`).

Template:
```
## 📋 Summary
<!-- 이 PR이 무엇을 하는지 간단히 설명해주세요 -->


## 🔗 Related Issue
<!-- 관련 이슈 링크 (예: Fixes TN-123, Closes TN-456) -->


## 🔄 Type of Change
- [ ] 🐛 Bug fix
- [ ] ✨ New feature
- [ ] 💥 Breaking change
- [ ] 📝 Documentation update
- [ ] ♻️ Refactoring
- [ ] 🧪 Test update

## 📝 Changes
<!-- 주요 변경 사항을 나열해주세요 -->
- 
- 

## 🧪 How to Test
<!-- 테스트 방법을 설명해주세요 -->
1. 
2. 

## ✅ Checklist
- [ ] 코드가 프로젝트 스타일 가이드를 따름
- [ ] Self-review 완료
- [ ] 필요한 문서 업데이트 완료
- [ ] 테스트 추가/수정 완료
- [ ] 로컬에서 테스트 통과 확인
```
