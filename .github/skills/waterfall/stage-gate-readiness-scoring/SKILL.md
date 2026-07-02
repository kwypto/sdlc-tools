---
name: Stage-Gate Readiness Scoring
description: Assess and score phase-gate readiness using weighted criteria, evidence quality, and go/no-go thresholds.
---

# Stage-Gate Readiness Scoring Skill

## Purpose
Use this skill when the user asks to evaluate readiness for a Waterfall phase gate (or equivalent governance checkpoint), generate a readiness score, and recommend a go/no-go decision.

## Inputs to collect
Gather these inputs before scoring:
- Target gate name (for example: Requirements Sign-off, Design Freeze, Test Exit, Release Readiness)
- Criteria list with optional weights (default evenly weighted if none provided)
- Evidence per criterion (documents, links, IDs, approvals, test reports, risk logs)
- Open risks/issues and severity
- Mandatory controls (must-pass items such as security approval or compliance sign-off)
- Decision threshold (default: Go >= 85, Conditional Go 70-84, No-Go < 70)

If data is incomplete, score conservatively and mark missing evidence explicitly.

## Scoring model
Use this 0-5 scale for each criterion:
- `0` = No evidence
- `1` = Minimal/informal evidence
- `2` = Partial evidence, major gaps
- `3` = Adequate evidence, some gaps
- `4` = Strong evidence, minor gaps
- `5` = Complete and verified evidence

Weighted score formula:
- Criterion Score % = `(score / 5) * 100`
- Weighted Contribution = `Criterion Score % * weight`
- Overall Readiness % = `sum(weighted contributions) / sum(weights)`

## Output requirements
Produce a markdown table using this exact column order:

| Criterion | Weight | Score (0-5) | Score % | Evidence | Risk Level | Mandatory Control | Gap/Action |
|---|---:|---:|---:|---|---|---|---|

Then provide:
1. `Overall Readiness %`
2. `Decision` (`Go`, `Conditional Go`, `No-Go`)
3. `Blocking Items` (mandatory controls not met or critical risks)
4. `Top 3 Actions` to improve readiness fastest

## Decision rules
1. If any mandatory control is unmet, decision cannot be `Go`.
2. If any criterion has score `0` and is high criticality, mark as blocking.
3. Apply threshold defaults unless user provides custom thresholds.
4. If evidence is missing, treat as lower confidence and reduce score accordingly.
5. Keep rationale concise and evidence-based.

## Quality checks
Before returning:
1. Confirm all provided criteria are scored exactly once.
2. Confirm all weights are numeric and total is shown.
3. Confirm every score has cited evidence or `Missing`.
4. Confirm blocking items align with decision outcome.
5. Include a short confidence note (`High`, `Medium`, `Low`) based on evidence completeness.

## Deliverables
Return:
1. Criterion-level readiness score table
2. Overall readiness score and decision
3. Blocking items list
4. Top 3 remediation actions with owners/due dates if available
