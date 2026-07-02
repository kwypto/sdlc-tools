---
name: Velocity and Predictability Forecaster
description: Forecast sprint/release delivery using historical velocity, variability, and confidence bands.
---

# Velocity and Predictability Forecaster Skill

## Purpose
Use this skill when the user asks to forecast likely delivery capacity and predictability for upcoming sprints or releases in Scrum.

## Inputs to collect
Gather:
- Historical sprint data (recommended 6-12 sprints): committed points, completed points, spillover, unplanned work
- Sprint duration and team capacity changes (holidays, staffing changes)
- Current backlog size for the forecast horizon
- Known constraints (fixed release date, mandatory scope, dependency risks)
- Optional quality signals (escaped defects, major incidents) that could affect delivery stability

If fewer than 4 sprints are provided, return forecast with low confidence and state limitations.

## Core calculations
For historical sprints:
1. Velocity per sprint = completed points
2. Commitment reliability per sprint = completed / committed
3. Mean velocity, median velocity, standard deviation
4. Coefficient of variation (CV) = stddev / mean

For forecast horizon:
- Baseline forecast uses median velocity.
- Confidence bands are percentile-based from historical distribution (or simulation if data is sufficient):
  - **P50** (most likely)
  - **P80** (high-confidence planning band)
  - **P90** (conservative planning band)

## Output requirements
Produce this table in exact column order:

| Metric | Value | Interpretation |
|---|---:|---|

Then provide this forecast table:

| Horizon | Scope (Points) | P50 Sprints | P80 Sprints | P90 Sprints | Predicted Date Range |
|---|---:|---:|---:|---:|---|

Also provide:
1. `Predictability Score` (0-100)
2. `Confidence Level` (`High`, `Medium`, `Low`)
3. `Planning Recommendation` (which band to use and why)
4. `Top 3 Drivers of Variability`

## Predictability scoring
Default scoring model:
- Start at 100
- Subtract points for high variability:
  - CV > 0.35: -20
  - CV > 0.50: -35 total
- Subtract for low commitment reliability:
  - average completed/committed < 0.85: -15
  - < 0.70: -30 total
- Subtract for persistent spillover (>30% sprints): -15
- Floor at 0

Interpretation:
- 80-100: Stable
- 60-79: Moderately stable
- 40-59: Volatile
- 0-39: Highly volatile

## Decision rules
1. For fixed-date commitments, prefer P80 or P90 capacity for planning.
2. If predictability score < 60, recommend scope buffering and shorter re-forecast cycles.
3. If team composition changed materially, down-weight older sprint data and reduce confidence.
4. If outlier sprints exist, identify them and state whether excluded/included with rationale.

## Quality checks
Before returning:
1. Confirm all formulas are shown or implied clearly.
2. Confirm confidence bands are consistent (P50 <= P80 <= P90 in conservatism).
3. Confirm assumptions and exclusions are explicit.
4. Include an uncertainty note for missing or sparse data.
5. Ensure recommendation aligns with predictability score and constraints.

## Deliverables
Return:
1. Summary metrics table
2. Forecast table with confidence bands
3. Predictability score and confidence
4. Practical planning recommendations for next sprint/release cycle
