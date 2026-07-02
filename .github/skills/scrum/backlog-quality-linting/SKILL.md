---
name: Backlog Quality Linting
description: Lint backlog items for clarity, testability, readiness, and dependency quality, then report actionable fixes.
---

# Backlog Quality Linting Skill

## Purpose
Use this skill when the user asks to evaluate backlog quality for epics, features, or user stories and identify issues that reduce planning reliability.

## Inputs to collect
Gather:
- Backlog item list (ID, title, description)
- Acceptance criteria
- Priority, estimate, and target sprint/release (if available)
- Dependencies, assumptions, and blockers
- Definition of Ready (DoR) and team conventions
- Non-functional requirements and compliance/security needs

If data is missing, report the missing fields as lint findings.

## Lint checks
Run these checks for each item:
1. **Title clarity**: specific and outcome-oriented, not vague.
2. **Problem/value statement**: business/user value is explicit.
3. **Acceptance criteria quality**: testable, measurable, and complete.
4. **Scope sizing**: item appears deliverable within expected iteration window.
5. **Dependency clarity**: upstream/downstream dependencies are identified.
6. **Risk visibility**: technical/compliance/operational risks are noted.
7. **NFR coverage**: relevant performance/security/reliability criteria included.
8. **Readiness metadata**: priority, estimate, owner, and target are present.
9. **Duplication/conflict**: no overlapping or contradictory items.
10. **DoR compliance**: item meets team Definition of Ready.

## Severity model
- `Error`: Must fix before planning/commitment.
- `Warning`: Should fix soon; may proceed with caution.
- `Info`: Improvement suggestion.

## Output requirements
Produce this table in exact column order:

| Item ID | Lint Rule | Severity | Finding | Suggested Fix | Status |
|---|---|---|---|---|---|

`Status` values:
- `Fail` (Error present)
- `Needs Work` (Warnings only)
- `Pass` (No significant issues)

Then provide:
1. `Backlog Health Score` (0-100)
2. `Pass Rate` (% items with `Pass`)
3. `Top Recurring Issues` (up to 5)
4. `Ready for Sprint Planning?` (`Yes`, `Partially`, `No`) with rationale

## Scoring approach
Default per-item scoring:
- Start at 100
- Subtract 20 per `Error`
- Subtract 8 per `Warning`
- Subtract 2 per `Info`
- Floor at 0

Backlog Health Score = average of per-item scores.

## Quality checks
Before returning:
1. Ensure each item has at least one lint result entry.
2. Ensure every `Error` includes a concrete suggested fix.
3. Ensure recurring issues are evidence-based (frequency in findings).
4. Ensure readiness recommendation aligns with severity distribution.
5. Include confidence level (`High`, `Medium`, `Low`) based on completeness of input data.

## Deliverables
Return:
1. Item-level lint findings table
2. Summary metrics (health score, pass rate, recurring issues)
3. Prioritized remediation actions for next refinement session
