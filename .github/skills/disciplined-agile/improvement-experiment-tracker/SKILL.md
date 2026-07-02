---
name: Improvement Experiment Tracker
description: Track continuous-improvement experiments from hypothesis to metric outcomes and adoption decisions.
---

# Improvement Experiment Tracker Skill

## Purpose
Use this skill when the user asks to design, track, evaluate, or report process improvement experiments using a hypothesis -> metric -> outcome flow.

## Inputs to collect
Gather:
- Experiment ID and title
- Problem statement and baseline condition
- Hypothesis statement (if/then/because format preferred)
- Change/intervention being tested
- Success metrics (leading and lagging), targets, and time window
- Data source and collection cadence
- Experiment owner and stakeholders
- Risks, dependencies, and guardrails

If baseline or target metrics are missing, mark confidence lower and flag as setup gap.

## Experiment lifecycle states
Use these states:
- `Proposed`
- `Planned`
- `Running`
- `Evaluating`
- `Adopt`
- `Iterate`
- `Stop`

## Output requirements
Produce this table in exact column order:

| Experiment ID | Hypothesis | Metric | Baseline | Target | Current | Outcome | Decision | Owner | Next Review |
|---|---|---|---:|---:|---:|---|---|---|---|

Outcome values:
- `Positive` (target met or exceeded)
- `Mixed` (partial movement)
- `Neutral` (no meaningful change)
- `Negative` (worse than baseline)
- `Inconclusive` (insufficient data)

Decision values:
- `Adopt`
- `Iterate`
- `Stop`
- `Continue Monitoring`

Then provide:
1. `Experiment Throughput` (active/completed this period)
2. `Success Rate` (% Positive outcomes)
3. `Learning Summary` (top insights)
4. `Next 3 Experiments` (prioritized)

## Evaluation rules
1. Compare current metric to baseline and target over the agreed time window.
2. If data quality is poor or sample size is too small, set outcome to `Inconclusive`.
3. Do not recommend `Adopt` without sustained improvement and no unacceptable side effects.
4. For `Negative` outcomes, include rollback or containment action.
5. Tie each decision to explicit evidence.

## Quality checks
Before returning:
1. Confirm every experiment has baseline, target, and current values (or explicit gap).
2. Confirm outcome and decision are consistent with metric movement.
3. Confirm each active experiment has a named owner and next review date.
4. Include confidence level (`High`, `Medium`, `Low`) based on data completeness.
5. Ensure learning summary includes at least one actionable insight.

## Deliverables
Return:
1. Experiment tracker table
2. Portfolio metrics (throughput, success rate)
3. Decision log and learning summary
4. Prioritized next-experiment recommendations
