| Control ID | Control Description | Status | Evidence | Risk if Missing | Owner | Remediation |
|---|---|---|---|---|---|---|
| SA-001 | Tool access is least-privilege and allowlisted | Missing |  | Unauthorized actions | Platform Owner | Restrict tool scopes and add denylist tests |
| SA-002 | Prompt/tool injection defenses are in place | Partial |  | Data exfiltration or unsafe execution | Security Lead | Add injection test suite and policy filters |
| SA-003 | Secrets are redacted and never exposed to agents | Missing |  | Credential leakage | DevOps Lead | Add vault-backed secret access and log redaction |
| SA-004 | Release gate blocks high-risk agent changes | Partial |  | Unsafe agent reaches production | Release Manager | Add mandatory security gate in CI |
| SA-005 | Runtime monitoring and incident playbooks exist | Missing |  | Delayed detection and response | SRE Lead | Add alerts, dashboards, and response runbook |

**Readiness Score:** TBD  
**Decision:** Fail  
**Top 5 Risks:** TBD  
**Release Gate Actions:** TBD  
**Reassessment Date:** TBD  
**Confidence:** Low
