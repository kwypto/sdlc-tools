---
name: Secure Agent Readiness Auditor
description: Assess AI agent workflows against OWASP Secure Agent Playbook controls and produce a risk-scored readiness decision.
---

# Secure Agent Readiness Auditor Skill

## Purpose
Use this skill to evaluate whether an AI agent setup (prompts, tools, policies, CI/CD, runtime controls) is safe enough to release based on OWASP Secure Agent Playbook guidance.

## Inputs to collect
- Agent inventory (name, purpose, scope, owners)
- Prompt/system instruction set and policy guardrails
- Tool permissions and allow/deny lists
- Secrets and data handling controls
- CI/CD checks and release gates
- Runtime monitoring, logging, and incident response controls
- Human approval points and rollback mechanisms
- Evidence artifacts (configs, workflow files, logs, test outputs)

## Control domains
Assess at least:
1. Identity, authn/authz, and least privilege *(critical)*
2. Prompt and tool injection resistance *(critical)*
3. Data protection and secret hygiene *(critical)*
4. Change control and deployment safety
5. Monitoring, alerting, and forensics
6. Human oversight and fail-safe behavior

Controls 1–3 are designated **critical**: a `Missing` status on any of these prevents a `Pass` decision regardless of overall score.

## Scoring model
Per control:
- `Implemented` = 2
- `Partial` = 1
- `Missing` = 0

Overall Readiness %:
`sum(control scores) / (2 * total controls) * 100`

Decision thresholds:
- `Pass` >= 85%
- `Conditional` 70-84%
- `Fail` < 70%

If any control marked `Critical` (Controls 1–3) is `Missing`, decision cannot be `Pass`.

## Output requirements
Produce this table:

| Control ID | Control Description | Critical | Status | Evidence | Risk if Missing | Owner | Remediation |
|---|---|---|---|---|---|---|---|

Then provide:
1. `Readiness Score`
2. `Decision` (`Pass`, `Conditional`, `Fail`)
3. `Top 5 Risks`
4. `Release Gate Actions`
5. `Reassessment Date`

## Quality checks
1. Every control has evidence or explicit `Missing`.
2. Critical gaps have an owner and due date (if available).
3. Decision matches score and critical-gap rule.
4. Include confidence level (`High`, `Medium`, `Low`) based on evidence completeness.

## Deliverables
1. Control coverage matrix
2. Risk-ranked finding summary
3. Actionable remediation plan
4. Release decision recommendation
