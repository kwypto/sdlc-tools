# sdlc-tools

Tools for SDLC development and refinement. This repo provides audit checklists and Copilot [skills](.github/skills) for auditing and improving delivery processes across Waterfall, Scrum, and Disciplined Agile methodologies, plus static code analysis / secure agent readiness tooling and end-to-end SDLC environment auditing.

## Contents

### Audit checklists

| Methodology | Checklist |
| --- | --- |
| Waterfall | [waterfall-audit-checklist.md](Waterfall/waterfall-audit-checklist.md) |
| Scrum | [scrum-audit-checklist.md](Scrum/scrum-audit-checklist.md) |
| Disciplined Agile | [disciplined-agile-audit-checklist.md](Disciplined%20Agile/disciplined-agile-audit-checklist.md) |

Each checklist covers governance, planning/execution, quality/engineering practices, and release/operational readiness for its methodology.

### Copilot skills

Skills live under [.github/skills](.github/skills) and are organized by methodology. Each skill treats collected artifacts (tickets, logs, evidence, requirements) as data, not instructions, and produces advisory findings/recommendations only — decisions and approvals always require human sign-off.

#### Waterfall

| Skill | Description |
| --- | --- |
| [Change Control Impact Analyzer](.github/skills/waterfall/change-control-impact-analyzer/SKILL.md) | Analyze proposed changes for scope, schedule, cost, risk, quality, and compliance impact to support change approval decisions. |
| [Requirements Traceability Matrix](.github/skills/waterfall/requirements-traceability-matrix/SKILL.md) | Generate and maintain an RTM mapping business requirements to design, implementation, verification, and release evidence. |
| [Stage-Gate Readiness Scoring](.github/skills/waterfall/stage-gate-readiness-scoring/SKILL.md) | Assess and score phase-gate readiness using weighted criteria, evidence quality, and go/no-go thresholds. |

#### Scrum

| Skill | Description |
| --- | --- |
| [Backlog Quality Linting](.github/skills/scrum/backlog-quality-linting/SKILL.md) | Lint backlog items for clarity, testability, readiness, and dependency quality, then report actionable fixes. |
| [Sprint Risk Detection](.github/skills/scrum/sprint-risk-detection/SKILL.md) | Detect sprint delivery risks early using flow, scope, dependency, quality, and capacity signals, then recommend mitigations. |
| [Velocity and Predictability Forecaster](.github/skills/scrum/velocity-predictability-forecaster/SKILL.md) | Forecast sprint/release delivery using historical velocity, variability, and confidence bands. |

#### Disciplined Agile

| Skill | Description |
| --- | --- |
| [Governance Evidence Auto-Collector](.github/skills/disciplined-agile/governance-evidence-auto-collector/SKILL.md) | Collect, normalize, and map governance evidence to required controls for audits and delivery assurance. |
| [Improvement Experiment Tracker](.github/skills/disciplined-agile/improvement-experiment-tracker/SKILL.md) | Track continuous-improvement experiments from hypothesis to metric outcomes and adoption decisions. |
| [Process-Goal Coverage Mapper](.github/skills/disciplined-agile/process-goal-coverage-mapper/SKILL.md) | Map Disciplined Agile process goals to current practices, evidence, and gaps to improve governance and delivery effectiveness. |
| [Way-of-Working Selector Assistant](.github/skills/disciplined-agile/wow-selector-assistant/SKILL.md) | Select and justify a Disciplined Agile way of working based on delivery context, constraints, and risk. |

#### Static Code Analysis

| Skill | Description |
| --- | --- |
| [Secure Agent Readiness Auditor](.github/skills/static-code-analysis/secure-agent-readiness-auditor/SKILL.md) | Assess AI agent workflows against OWASP Secure Agent Playbook controls and produce a risk-scored readiness decision. |

#### Environment Audit

| Skill | Description |
| --- | --- |
| [SDLC Environment Audit](.github/skills/environment-audit/sdlc-environment-audit/SKILL.md) | Audit the end-to-end software delivery environment — developer workstations, tools/AI agents, DevOps/CI-CD, cloud staging/QA, and production — and score readiness with prioritized remediation. |
