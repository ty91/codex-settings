---
description: Create a detailed implementation plan
---

# Create Implementation Plan

You are tasked with creating detailed implementation plans through an interactive, iterative process. You should be skeptical, thorough, and work collaboratively with the user to produce high-quality technical specifications.

## Context

- Plan file: `.tasks/<git-branch-name>/plan.md`
- `git-branch-name` uses `-` instead of `/`

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

## Process Phases

### Phase 1 — Ground in Environment

- Explore first, ask second.
- Run at least one targeted non-mutating exploration pass.
- Resolve ambiguities via inspection when possible.
- Ask only what cannot be discovered.

### Phase 2 — Intent Chat

Clarify until you can state:
- Goal and success criteria
- Audience
- In-scope and out-of-scope
- Constraints
- Current state
- Preferences and tradeoffs

If any high-impact ambiguity remains, keep asking.

### Phase 3 — Implementation Chat

Make the spec **decision complete**:
- Approach and architecture
- Interfaces and schemas
- Data flow
- Edge cases and failure modes
- Testing and acceptance criteria
- Rollout, monitoring, migrations, compat
Ensure each phase is independently verifiable.

### Phase 4 — Detailed Plan Writing

Once research is complete:

1. Present a proposed structure to the user:
   ```
   Based on the research findings, here's my proposed plan structure:

   ## Overview
   [1-2 sentence summary]

   ## Implementation Phases:
   - [ ] 1. [Phase name] - [what it accomplishes]
   - [ ] 2. [Phase name] - [what it accomplishes]
   - [ ] 3. [Phase name] - [what it accomplishes]

   Does this phasing make sense? Would you like to adjust the scope or order?
   ```
2. Ask for user confirmation or adjustments
3. Iterate on structure until user confirms

**Before writing**, ensure:
- All research is complete and understood
- User has confirmed the plan structure

Write the plan file using the template below.

### Phase 5 — Review and Iterate

1. Save the plan and present location to user
2. Ask if any adjustments are needed
3. Iterate based on feedback until user is satisfied

## Questioning Guidance

### Asking Questions

- Ask only questions that materially affect the plan.
- Provide 2–4 meaningful options with a recommended default. Use the template below.
- If unavoidable and not representable, ask directly.

#### Question Format Template

Use this structure for one or more questions:
```
Questions:
1. [One specific question]
   Options:
   1. (Recommended) [Option + brief rationale]
   2. [Option + brief rationale]
   ...

2. [One specific question]
   Options:
   1. (Recommended) [Option + brief rationale]
   2. [Option + brief rationale]
   ...
...
```

### Two Kinds of Unknowns

**Discoverable facts**:
- Explore first.
- Ask only if multiple candidates or nothing found.

**Preferences/tradeoffs**:
- Ask early.
- If unanswered, proceed with recommended default and record assumption.

## Final Output

Only when decision complete, write the plan **without** any special wrapper tags.
Save it to the plan file.

### Writing Style

- Audience: software tech lead; prioritize report-style readability.
- Match content hierarchy with correct indentation.
- Use tables when they improve clarity.

### Rules
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
**Changes**:
- [Change item 1]
- [Change item 2]
- ...

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

## Important Guidelines

1. Question vague requirements; surface issues early.
2. Keep a visible planning checklist.
3. Research before design decisions, on unfamiliar areas, to find patterns, or when the approach is unclear.
4. Keep notes factual; cite file paths and line numbers.
5. Include file paths and measurable success criteria.
6. Use code blocks only for exact contracts.
7. Each phase must be independently verifiable with clear success criteria.
8. Resolve ambiguities before finalizing; no open questions in the plan.
9. List research notes and other sources in References.
10. Do not ask "should I proceed?" after the plan.
11. You are not in "Plan Mode" and may write the plan file at any time.
