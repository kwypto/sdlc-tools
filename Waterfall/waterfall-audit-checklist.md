# Classic Waterfall SDLC Audit Checklist

Use this checklist to assess process maturity, control effectiveness, and delivery reliability in a phase-gated Waterfall model.

## 1. Governance and Scope Control
- Confirm a formally approved project charter exists with objectives, constraints, budget, timeline, sponsors, and ownership.
- Verify scope is baselined early and protected through a documented change control process.
- Review how scope changes are submitted, analyzed for impact (cost/schedule/risk), approved/rejected, and communicated.
- Ensure key governance artifacts exist and are current: RACI, escalation paths, steering committee cadence, and decision log.
- Check that phase entry/exit criteria are defined and actually used as control points (not bypassed informally).

## 2. Requirements Management
- Verify Business Requirements Document (BRD) and Software Requirements Specification (SRS) are complete, versioned, and approved by business and technical stakeholders.
- Confirm requirements are specific, testable, and unambiguous, with acceptance criteria for each major requirement.
- Check requirements traceability from business goals to functional/non-functional requirements and downstream test cases.
- Assess requirement volatility: frequency of changes, root causes, and whether change control was followed.
- Validate stakeholder sign-off records and evidence that unresolved requirement conflicts were escalated and resolved.

## 3. Solution Design Quality
- Confirm architecture and detailed design documents are baselined and approved before implementation begins.
- Evaluate completeness of design artifacts: component diagrams, data models, interface/API contracts, and sequence/process flows.
- Verify non-functional requirements (performance, availability, security, scalability, maintainability) are addressed in design.
- Check completion of formal design reviews with documented findings, actions, and closure evidence.
- Ensure integration points, external dependencies, and assumptions are explicitly identified and risk-assessed.

## 4. Build and Implementation Controls
- Confirm coding standards, branching strategy, naming conventions, and review expectations are documented and followed.
- Verify source control practices support auditability: commit history quality, reviewer evidence, and protected branch policies.
- Check build process consistency and reproducibility across environments, including dependency and version management.
- Validate developer unit testing expectations and evidence (coverage reports, test logs, or equivalent artifacts).
- Review defect prevention controls during build (peer review rigor, static analysis, secure coding checks).

## 5. Verification and Validation (Testing)
- Confirm a master test strategy/plan exists with scope, environments, resource plan, entry/exit criteria, and defect severity model.
- Verify comprehensive test design: requirement-based test cases, integration/system/regression suites, and negative-path testing.
- Ensure test coverage is traceable to requirements and highlight any orphan requirements or untested scope.
- Review defect lifecycle discipline: triage process, SLAs by severity, root cause tracking, and retest/reopen handling.
- Validate User Acceptance Testing (UAT) execution and formal acceptance evidence aligned to agreed business criteria.

## 6. Deployment and Release Readiness
- Confirm release plans and runbooks are complete, rehearsed where required, and approved by relevant stakeholders.
- Verify go-live prerequisites are satisfied: environment readiness, access controls, data migration readiness, and support staffing.
- Check rollback/backout procedures are documented, tested, and linked to clear trigger criteria.
- Ensure production readiness reviews include operational, security, compliance, and business readiness checkpoints.
- Validate release communication plans for internal teams, users, and support channels before and after deployment.

## 7. Operations, Support, and Maintenance
- Confirm post-release ownership model (L1/L2/L3), support procedures, and on-call/escalation paths are defined.
- Verify monitoring and alerting coverage for critical services, interfaces, and business transactions.
- Check incident/problem management process adherence, including RCA completion and corrective/preventive actions.
- Assess patch, upgrade, and vulnerability remediation cadence against policy and risk posture.
- Validate operational documentation and knowledge transfer quality to ensure support continuity and resilience.

## 8. Quality Management and Stage-Gate Effectiveness
- Verify each Waterfall phase has explicit entry/exit quality gates with measurable acceptance criteria.
- Confirm required approvals are captured with timestamps and responsible approvers for full audit traceability.
- Review key quality metrics by phase (defect density, rework, schedule variance, milestone slippage, defect leakage).
- Assess whether gate failures trigger remediation plans and whether exceptions are formally approved and documented.
- Evaluate whether lessons learned from prior phases are incorporated before subsequent phase approvals.

## 9. Risk, Compliance, and Control Assurance
- Confirm a live risk register exists with owners, impact/probability ratings, mitigation plans, and due dates.
- Verify regulatory, contractual, and internal policy controls are mapped to project activities and deliverables.
- Check segregation of duties across development, testing, approvals, and production deployment activities.
- Validate evidence retention practices (artifacts, approvals, logs, test results) meet audit and legal requirements.
- Ensure periodic compliance/internal audit reviews are performed and findings are tracked to verified closure.
