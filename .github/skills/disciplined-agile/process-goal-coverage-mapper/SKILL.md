---
name: Process-Goal Coverage Mapper
description: Map Disciplined Agile process goals to current practices, evidence, and gaps to improve governance and delivery effectiveness.
---

# Process-Goal Coverage Mapper Skill

## Purpose
Use this skill when the user asks to assess how well a team’s current way of working covers Disciplined Agile process goals and where coverage gaps remain.

## Inputs to collect
Gather:
- Team/process context (product type, lifecycle, constraints)
- Current practices by phase/flow (planning, build, test, deploy, operate)
- Documented policies, standards, and governance requirements
- Evidence artifacts (playbooks, checklists, tickets, reports, dashboards)
- Role ownership for each process area
- Known pain points, recurring incidents, and audit findings

If evidence is incomplete, mark coverage conservatively.

## Process goals to evaluate
Evaluate at least these goal areas:
1. Explore scope and prioritize work
2. Coordinate activities and dependencies
3. Evolve architecture and technical strategy
4. Produce and verify consumable solutions
5. Ensure quality, security, and compliance
6. Deploy and release reliably
7. Operate, support, and learn continuously
8. Govern delivery and decision-making
9. Improve way of working over time

## Coverage scale
Use this coverage scale:
- `0` = Not addressed
- `1` = Ad hoc/informal
- `2` = Partially defined
- `3` = Defined and repeatable
- `4` = Measured and controlled
- `5` = Optimized and continuously improved

Coverage status:
- `Strong` (4-5)
- `Moderate` (3)
- `Weak` (1-2)
- `Missing` (0)

## Output requirements
Produce this table in exact column order:

| Process Goal | Coverage Score (0-5) | Coverage Status | Current Practice | Evidence | Owner | Gap | Recommended Action |
|---|---:|---|---|---|---|---|---|

Then provide:
1. `Overall Coverage %`
2. `Weak/Missing Goal Count`
3. `Top 5 Gaps by Risk`
4. `90-Day Improvement Priorities`
5. `Audit Readiness Note`

## Calculation guidance
- Overall Coverage % = `(sum(scores) / (goal_count * 5)) * 100`
- Weight high-risk governance/compliance goals higher if user provides weighting.
- If evidence is missing, cap score at `2` unless explicitly justified.

## Decision rules
1. Any governance/compliance goal scored `0-1` must be flagged as priority gap.
2. Repeated operational failures should lower relevant goal coverage.
3. Missing ownership prevents a goal from being rated above `3`.
4. Recommendations must assign action owner and target milestone when possible.
5. Prioritize actions that improve both delivery flow and control assurance.

## Quality checks
Before returning:
1. Confirm all required process goals are assessed.
2. Confirm each score has concrete evidence or explicitly states missing evidence.
3. Confirm high-risk gaps are reflected in top priorities.
4. Include confidence level (`High`, `Medium`, `Low`) based on evidence completeness.
5. Ensure improvement priorities are time-bound and realistically scoped.

## Deliverables
Return:
1. Process-goal coverage matrix
2. Coverage summary metrics
3. Prioritized remediation roadmap for the next 90 days
