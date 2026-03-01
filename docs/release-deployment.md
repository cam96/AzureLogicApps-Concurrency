# OctoAcme Release & Deployment

This document describes the OctoAcme release and deployment process — how software is prepared, validated, and shipped to production safely and repeatably.

---

## Release Philosophy

OctoAcme aims for **frequent, small releases** that reduce deployment risk and provide rapid feedback. All releases go through a defined pipeline of automated checks and manual gates before reaching production.

---

## Release Types

| Type | Cadence | Description |
|---|---|---|
| **Patch / Hotfix** | As needed | Critical bug fixes; fast-tracked through the pipeline with expedited review |
| **Minor release** | Every 2–4 sprints | Feature updates and non-breaking improvements |
| **Major release** | Planned; varies | Significant new functionality or breaking changes; requires full regression |

---

## Release Pipeline

```
Feature branch → PR → CI checks → Merge to main → Deploy to Dev → Deploy to Test → QA sign-off → Deploy to Staging → UAT → Release approval → Deploy to Production
```

### Stage Descriptions

| Stage | Owner | Gate to Proceed |
|---|---|---|
| **PR / CI checks** | Engineer, CI | All checks pass; minimum 1 approval |
| **Deploy to Dev** | DevOps (automated) | CI pipeline green |
| **Deploy to Test** | DevOps (automated) | Test environment healthy |
| **QA sign-off** | QA Engineer | Test plan executed; no open P1/P2 defects |
| **Deploy to Staging** | DevOps | QA sign-off received |
| **UAT** | Product Owner, Stakeholders | Acceptance criteria met; business sign-off |
| **Release approval** | Product Owner + Project Manager | UAT passed; change request approved (if required) |
| **Deploy to Production** | DevOps | Release approval in place; deployment window agreed |

---

## Deployment Practices

### Infrastructure as Code

All environments are provisioned and managed using infrastructure-as-code (IaC). Manual changes to production infrastructure are prohibited.

### Zero-Downtime Deployments

Where possible, deployments use blue-green or rolling update strategies to avoid service interruptions.

### Deployment Windows

Production deployments are scheduled during agreed **maintenance windows** (typically off-peak hours) unless the release is a critical hotfix. The Project Manager communicates the deployment window to stakeholders at least 48 hours in advance.

### Rollback Plan

Every deployment must have a documented **rollback plan**. Before deploying to production, the DevOps Engineer confirms:

- The rollback procedure is documented in the runbook
- The previous version artefacts are available
- The team is available to execute a rollback if required

---

## Release Checklist

- [ ] All planned stories meet the Definition of Done
- [ ] No open P1 or P2 defects
- [ ] QA sign-off received
- [ ] UAT completed and signed off by Product Owner
- [ ] Release notes drafted and reviewed
- [ ] Runbook updated (deployment steps, rollback procedure)
- [ ] Stakeholders notified of deployment window
- [ ] Change request raised and approved (if required by governance process)
- [ ] Monitoring and alerting confirmed operational
- [ ] Post-deployment smoke test plan ready

---

## Post-Deployment Activities

1. **Smoke testing** — the QA Engineer runs a smoke test immediately after deployment to confirm core functionality is working in production
2. **Monitoring** — the DevOps Engineer monitors dashboards and alerts for at least 30 minutes after deployment
3. **Stakeholder notification** — the Project Manager notifies stakeholders that the release is live
4. **Release notes published** — final release notes are published to the project wiki

---

## Related Documents

- [Execution & Tracking](execution-tracking.md)
- [Risks & Communication](risks-communication.md)
- [Retrospective & Continuous Improvement](retrospective-continuous-improvement.md)
- [Roles & Personas](roles-personas.md)
