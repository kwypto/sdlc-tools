---
name: Change Control Impact Analyzer
description: Analyze proposed changes for scope, schedule, cost, risk, quality, and compliance impact to support change approval decisions.
---

# Change Control Impact Analyzer Skill

## Purpose
Use this skill when the user asks to assess a change request and determine its delivery, risk, and governance impact before approval.

## Inputs to collect
Gather these inputs first:
- Change request ID, title, and business rationale
- Current baseline (scope, schedule, budget, release target)
- Detailed change description (what is added/removed/modified)
- Affected requirements, systems, teams, vendors, and environments
- Dependencies and assumptions
- Impact evidence (estimates, architecture notes, test impact, risk/compliance inputs)
- Decision constraints (fixed date, budget ceiling, mandatory controls)

If key details are missing, mark as `Unknown` and reduce confidence.

## Impact dimensions
Score each dimension on a 1-5 impact scale:
- `1` = Negligible
- `2` = Low
- `3` = Moderate
- `4` = High
- `5` = Severe

Required dimensions:
1. Scope impact
2. Schedule impact
3. Cost impact
4. Resource/capacity impact
5. Technical/architecture impact
6. Quality/testing impact
7. Security/compliance impact
8. Operational/support impact
9. Vendor/third-party impact (if applicable)

## Output requirements
Produce this table in exact column order:

| Dimension | Impact Score (1-5) | Impact Summary | Evidence | Mitigation | Residual Risk |
|---|---:|---|---|---|---|

Then provide:
1. `Overall Impact Rating` (`Low`, `Medium`, `High`, `Critical`)
2. `Recommended Decision` (`Approve`, `Approve with Conditions`, `Defer`, `Reject`)
3. `Approval Conditions` (if any)
4. `Top 3 Risks` and owners
5. `Traceability Updates Required` (requirements/design/test/release artifacts)

## Decision logic
1. If security/compliance impact is `4` or `5` with no mitigation, cannot recommend `Approve`.
2. If schedule or cost impact breaches stated constraints, recommend `Defer` or `Reject` unless scope trade-offs are defined.
3. Use `Approve with Conditions` when major impacts are controllable with explicit actions and owners.
4. Flag any `Unknown` critical input as a decision blocker.
5. Keep recommendations evidence-based and explicit.

## Quality checks
Before returning:
1. Confirm all applicable dimensions are assessed.
2. Confirm every high/severe impact has mitigation and owner.
3. Confirm residual risks are stated after mitigation.
4. Include confidence level (`High`, `Medium`, `Low`) based on evidence completeness.
5. Ensure recommendation aligns with stated constraints and blockers.

## Deliverables
Return:
1. Dimension-by-dimension impact table
2. Overall rating and recommendation
3. Approval conditions/blockers
4. Required artifact updates for governance traceability
