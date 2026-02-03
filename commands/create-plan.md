---
description: Create a detailed implementation plan
---

# Create Implementation Plan

Your job is to collaborate on a *decision-complete* plan, not to execute it.

## Mode Rules (Strict)

- If user asks to execute, treat it as a request to **plan** execution.
- Do not perform **mutating** actions.

## Allowed vs Not Allowed

**Allowed (non-mutating, plan-improving)**:
- Read/search files, configs, schemas, docs
- Static analysis and inspection
- Dry-run commands that do not edit repo-tracked files
- Tests/builds that only write caches or artifacts

**Not allowed (mutating, plan-executing)**:
- Edit/write files
- Apply patches, formatters, codegen, migrations
- Any action whose purpose is “doing the work”

## Initial Response

When this command is invoked, respond with:
```
I'll help you create a detailed implementation plan. Let me start by understanding what we're building.

Please provide:
1. The task description or requirements
2. Any relevant context, constraints, or specific requirements
3. Links to related research or previous implementations

I'll analyze this information and work with you to create a comprehensive plan.
```

Then wait for the user's input.

## Phase 1 — Ground in Environment

- Explore first, ask second.
- Run at least one targeted non-mutating exploration pass.
- Resolve ambiguities via inspection when possible.
- Ask only what cannot be discovered.

## Phase 2 — Intent Chat

Clarify until you can state:
- Goal and success criteria
- Audience
- In-scope and out-of-scope
- Constraints
- Current state
- Preferences and tradeoffs

If any high-impact ambiguity remains, keep asking.

## Phase 3 — Implementation Chat

Make the spec **decision complete**:
- Approach and architecture
- Interfaces and schemas
- Data flow
- Edge cases and failure modes
- Testing and acceptance criteria
- Rollout, monitoring, migrations, compat
Ensure each phase is independently verifiable.

## Asking Questions

- Ask only questions that materially affect the plan.
- List question topics first, then ask one question at a time.
- Provide 2–4 meaningful options with a recommended default.
- If unavoidable and not representable, ask directly.

## Two Kinds of Unknowns

**Discoverable facts**:
- Explore first.
- Ask only if multiple candidates or nothing found.

**Preferences/tradeoffs**:
- Ask early.
- If unanswered, proceed with recommended default and record assumption.

## Final Output

Only when decision complete, write the plan **without** any special wrapper tags.
Save it to `PLAN.md` at the project root.

Rules:
- Use Markdown.
- Minimize code blocks. Use only when exact contracts/interfaces are required or text is insufficient.
- Headings in English, body in Korean. Code/paths/commands stay in English.
- Follow the template structure and placeholders below.
- When referencing existing code, include file paths and line numbers.
- Do not ask “should I proceed?” after the plan.

```
# [Feature/Task Name] Implementation Plan

## Overview
[Brief description of what we're implementing and why]

## Current State Analysis
[What exists now, what's missing, key constraints discovered]

## Desired End State
[Specification of the desired end state and how to verify it]

## What We're NOT Doing
[Explicitly list out-of-scope items]

## Assumptions / Defaults
[Decisions made due to missing input]

## Implementation Approach
[High-level strategy and reasoning]

## Public API / Interface Changes
[User-facing or integrator-facing changes]

---

## - [ ] Phase 1: [Descriptive Name]

### Overview
[What this phase accomplishes]

### Changes Required:

#### 1. [Component/File Group]
**File**: [path/to/file.ext]
**Changes**: [Summary of changes]

### Success Criteria:
- [ ] [Concrete, testable success criterion]
- [ ] [Another criterion]

---

## - [ ] Phase 2: [Descriptive Name]
[Repeat the same structure for additional phases]

...

---

## Testing Strategy

### Unit Tests:
- [What to test]
- [Key edge cases]

### Integration Tests:
- [End-to-end scenarios]

### Manual Testing Steps:
1. [Specific verification step]
2. [Another verification step]

## Performance Considerations
[Any performance implications or optimizations needed]

## Migration Notes
[If applicable, how to handle existing data/systems]

## References

### Research Findings
- [List findings files with brief descriptions]

### Other Sources
- [List additional files read during planning]
- [Documentation consulted]
- [External resources referenced]
- [Related issues/PRs]
```
