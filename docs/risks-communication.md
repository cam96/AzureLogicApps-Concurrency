# OctoAcme Risks & Communication

This document describes how OctoAcme identifies, tracks, and mitigates project risks, and defines the communication practices that keep all stakeholders informed throughout the project lifecycle.

---

## Risk Management

### Risk Identification

Risk identification is an ongoing activity. Risks are first captured during project initiation (see [Project Initiation](project-initiation.md)) and continuously reviewed throughout delivery.

Sources of risk include:
- Sprint retrospectives and daily stand-ups
- Dependency reviews
- Technical spikes and proof-of-concept outcomes
- Stakeholder feedback and market changes

### Risk Register

All identified risks are recorded in the **Risk Register**, maintained by the Project Manager. Each entry contains:

| Field | Description |
|---|---|
| ID | Unique identifier (e.g., `RISK-001`) |
| Title | Short description of the risk |
| Category | Technical / Schedule / Resource / External / Quality |
| Likelihood | Low / Medium / High |
| Impact | Low / Medium / High |
| Risk Score | Likelihood × Impact (1–9 scale) |
| Owner | Person responsible for mitigation |
| Mitigation | Actions to reduce likelihood or impact |
| Contingency | Actions to take if the risk materialises |
| Status | Open / Mitigated / Closed / Materialised |

The Risk Register is reviewed at every sprint planning session and updated accordingly.

### Risk Response Strategies

| Strategy | When to Use |
|---|---|
| **Avoid** | Eliminate the cause of the risk |
| **Mitigate** | Reduce likelihood or impact |
| **Transfer** | Shift responsibility (e.g., insurance, contracts) |
| **Accept** | Acknowledge and monitor; no action required |

### Escalation

Risks with a score of **6 or higher** (High × Medium or above) must be escalated to the Project Sponsor within one business day of identification.

---

## Communication Plan

Clear, consistent communication is critical to project success. The following plan defines the standard communication cadences and channels for OctoAcme projects.

### Communication Channels

| Channel | Purpose |
|---|---|
| **Team chat (e.g., Teams/Slack)** | Day-to-day team communication, quick questions, informal updates |
| **Issue tracker** | Work item updates, defect tracking, decision records |
| **Email** | Formal communications, status reports, stakeholder updates |
| **Video calls / meetings** | Sprint ceremonies, design sessions, stakeholder reviews |
| **Wiki / Docs** | Persistent documentation, runbooks, process guides |

### Stakeholder Communication Schedule

| Audience | Communication Type | Frequency | Owner | Channel |
|---|---|---|---|---|
| Project team | Daily stand-up | Daily | PM | Video call / chat |
| Product Owner | Backlog refinement | Every sprint (mid) | PM | Video call |
| Project team + PO | Sprint review | End of sprint | PM | Video call |
| Project team | Retrospective | End of sprint | PM | Video call |
| Stakeholders | Status report | Weekly | PM | Email |
| Sponsor + senior stakeholders | Steering committee | Monthly | PM | Video call |

### Communication Principles

- **Transparency:** Share progress, blockers, and risks openly and promptly
- **Single source of truth:** Key decisions and artefacts live in the wiki / docs; chat is transient
- **Appropriate channel:** Match the communication type to the right channel (e.g., avoid making formal decisions in chat)
- **Timely escalation:** Do not delay raising blockers or risks — surface them at the earliest opportunity

---

## Issue Management

Issues (risks that have materialised) are logged separately in the **Issue Log** using the same format as the Risk Register, with the addition of:

- **Date raised**
- **Resolution** and date closed

Issues are reviewed at every sprint planning session alongside the Risk Register.

---

## Related Documents

- [Project Initiation](project-initiation.md)
- [Execution & Tracking](execution-tracking.md)
- [Roles & Personas](roles-personas.md)
