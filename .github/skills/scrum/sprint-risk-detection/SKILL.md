---
name: Sprint Risk Detection
description: Detect sprint delivery risks early using flow, scope, dependency, quality, and capacity signals, then recommend mitigations.
---

# Sprint Risk Detection Skill

## Purpose
Use this skill when the user asks to identify, score, and prioritize risks that could prevent a sprint from meeting its goal.

## Inputs to collect
Gather:
- Sprint goal and committed backlog items
- Team capacity and availability (planned vs actual)
- Current sprint board state (To Do/In Progress/Done/Blocked)
- Aging WIP, carryover, and scope change events
- Dependency map (internal/external) and blocker log
- Defect trend, build/test stability, and incident signals
- Historical sprint metrics (velocity, spillover, cycle time)

If key signals are missing, mark confidence lower and call out blind spots.

## Risk categories
Assess at least these categories:
1. Scope volatility risk
2. Capacity shortfall risk
3. Dependency/blocker risk
4. Flow congestion risk (WIP aging, bottlenecks)
5. Quality risk (defects, unstable tests/builds)
6. Requirement ambiguity risk
7. Operational/release risk
8. Stakeholder alignment risk

## Scoring model
Score each category for:
- **Likelihood (1-5)**
- **Impact (1-5)**

Risk Score = `Likelihood * Impact` (range 1-25)

Risk level bands:
- `Low`: 1-6
- `Medium`: 7-12
- `High`: 13-19
- `Critical`: 20-25

## Output requirements
Produce this table in exact column order:

| Risk Category | Likelihood (1-5) | Impact (1-5) | Risk Score | Risk Level | Signal/Evidence | Mitigation | Owner | Due Date |
|---|---:|---:|---:|---|---|---|---|---|

Then provide:
1. `Overall Sprint Risk` (`Low`, `Medium`, `High`, `Critical`)
2. `Sprint Goal Confidence` (0-100%)
3. `Top 3 Risks` by score
4. `Immediate Actions (48h)` for highest risks
5. `Escalations Needed` (if any)

## Decision logic
1. Any `Critical` risk requires immediate mitigation and explicit owner.
2. Two or more `High` risks in dependency/flow/capacity should reduce sprint confidence materially.
3. If scope changed significantly without capacity adjustment, raise scope volatility severity.
4. If blocker aging exceeds team norm, elevate dependency risk.
5. Recommendations must be concrete, time-bound, and owner-assigned when possible.

## Quality checks
Before returning:
1. Confirm every risk has evidence, not just opinion.
2. Confirm top risks include at least one mitigation action each.
3. Confirm overall risk aligns with highest category scores and concentration.
4. Include trend note (improving/stable/worsening) if prior sprint data exists.
5. Include confidence level (`High`, `Medium`, `Low`) based on signal completeness.

## Deliverables
Return:
1. Sprint risk radar table
2. Overall risk and sprint-goal confidence
3. Top risk mitigations with owners and near-term due dates
