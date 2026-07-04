| Layer | Control ID | Control Description | Critical | Status | Evidence | Risk if Missing | Owner | Remediation |
|---|---|---|---|---|---|---|---|---|
| Developer Workstation | DW-001 | Endpoint disk encryption and patching enforced | Yes | Partial | MDM report shows 80% compliance | Data loss on lost/stolen device | IT Security | Enforce MDM compliance policy, block non-compliant devices from VPN |
| Developer Workstation | DW-002 | Local secrets never stored in plaintext env files | No | Missing |  | Credential leakage from dev machine | Eng Lead | Roll out vault-backed CLI for local secret access |
| Tools & AI Agents | TA-001 | SSO + MFA enforced for all developer tooling | Yes | Implemented | Okta admin console export | N/A | IT Security |  |
| Tools & AI Agents | TA-002 | AI coding agents have a documented data-handling policy | Yes | Missing |  | Sensitive code/data sent to external model without policy | Platform Owner | Adopt data-handling policy; run Secure Agent Readiness Auditor for deep scoring |
| DevOps/CI-CD | CD-001 | Pipeline secrets use short-lived OIDC tokens, not static keys | Yes | Partial | Pipeline YAML shows mixed usage | Long-lived credential compromise | DevOps Lead | Migrate remaining pipelines to OIDC federation |
| DevOps/CI-CD | CD-002 | Branch protection requires review + passing checks before merge | Yes | Implemented | GitHub branch protection settings | N/A | Release Manager |  |
| Cloud Staging/QA | SQ-001 | Staging environment uses masked/synthetic data, not prod PII | Yes | Missing |  | PII exposure in lower environment | Data Owner | Implement data masking pipeline for staging refresh |
| Cloud Staging/QA | SQ-002 | Ephemeral environments are torn down after use | No | Partial | IaC teardown script exists but not automated on schedule | Unnecessary cost and attack surface | DevOps Lead | Automate scheduled teardown via IaC pipeline |
| Production | PR-001 | Deployment changes require documented approval and rollback plan | Yes | Implemented | Change record template + CAB log | N/A | Release Manager |  |
| Production | PR-002 | Backup and disaster recovery tested within last quarter | Yes | Missing |  | Extended outage / data loss on failure | SRE Lead | Schedule and execute DR test, document results |

**Per-Layer Readiness:**
- Developer Workstation: Score: TBD — Decision: TBD — Confidence: TBD
- Tools & AI Agents: Score: TBD — Decision: TBD — Confidence: TBD (see Secure Agent Readiness Auditor for AI agent depth)
- DevOps/CI-CD: Score: TBD — Decision: TBD — Confidence: TBD
- Cloud Staging/QA: Score: TBD — Decision: TBD — Confidence: TBD
- Production: Score: TBD — Decision: TBD — Confidence: TBD

**Overall Readiness Score:** TBD
**Overall Decision:** TBD
**Top 5 Cross-Layer Risks:** TBD
**Remediation Roadmap:** TBD
**Cross-References:** Run Secure Agent Readiness Auditor (`static-code-analysis/secure-agent-readiness-auditor`) for AI agent findings flagged above.
**Reassessment Date:** TBD
**Overall Confidence:** TBD
