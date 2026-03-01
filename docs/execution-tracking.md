# OctoAcme Execution & Tracking

This document describes how OctoAcme teams execute sprint work and track progress throughout delivery, ensuring transparency and timely resolution of issues.

---

## Sprint Ceremonies

### Daily Stand-up

- **Frequency:** Every working day, same time
- **Duration:** 15 minutes maximum
- **Format:** Each team member answers:
  1. What did I complete since yesterday?
  2. What will I work on today?
  3. Are there any blockers?
- **Owner:** Project Manager (facilitator); the team owns the conversation
- **Output:** Updated work-item statuses; blockers logged and assigned for resolution

### Sprint Review

- **Frequency:** End of each sprint
- **Duration:** 1 hour (per 2-week sprint)
- **Purpose:** Demonstrate completed work to stakeholders and collect feedback
- **Attendees:** Full team, Product Owner, relevant stakeholders
- **Output:** Accepted / not-accepted stories; updated backlog based on feedback

### Sprint Retrospective

- **Frequency:** End of each sprint (after the review)
- **Duration:** 45–60 minutes
- **Purpose:** Reflect on team process and agree on improvement actions
- **Format:** *What went well / what could be improved / actions*
- **Owner:** Project Manager (facilitator)
- **Output:** Action items with owners and due dates, tracked in the retrospective log

See [Retrospective & Continuous Improvement](retrospective-continuous-improvement.md) for more detail.

---

## Work Item Workflow

```
Backlog → Ready → In Progress → In Review → Testing → Done
```

| Status | Description |
|---|---|
| **Backlog** | Created but not yet refined or prioritised |
| **Ready** | Meets the Definition of Ready; ready to be pulled into a sprint |
| **In Progress** | Actively being worked on |
| **In Review** | Pull request opened; awaiting code review |
| **Testing** | Handed to QA for functional testing |
| **Done** | Meets the Definition of Done; accepted |

---

## Tracking & Reporting

### Sprint Burndown

The Project Manager maintains a **sprint burndown chart** showing remaining story points against the sprint timeline. The team reviews it daily during stand-up. A burndown that flattens early or fails to trend down is an early warning sign requiring attention.

### Release Burnup

A **release burnup chart** tracks cumulative completed scope against the release target. The Product Owner and Project Manager review it at each sprint review.

### Status Reports

The Project Manager distributes a concise **weekly status report** to stakeholders, covering:

- Work completed this week
- Work planned for next week
- RAG (Red / Amber / Green) status for scope, schedule, and budget
- Active risks and issues

### Escalation Path

| Issue Type | First Contact | Escalation |
|---|---|---|
| Technical blocker | Technical Lead | Project Manager |
| Scope change | Product Owner | Project Sponsor |
| Resource constraint | Project Manager | Department Lead |
| Risk materialising | Project Manager | Project Sponsor |

---

## Branching & Code Integration

OctoAcme follows a **trunk-based development** model with short-lived feature branches:

1. Create a feature branch from `main` (`feature/<ticket-id>-short-description`)
2. Make small, incremental commits
3. Open a pull request against `main` when ready for review
4. At least one peer review required; Technical Lead review required for architectural changes
5. Merge only when all checks pass and approvals are in place
6. Delete the feature branch after merging

CI pipelines run automatically on every pull request (build, lint, unit tests, integration tests).

---

## Related Documents

- [Planning](planning.md)
- [Risks & Communication](risks-communication.md)
- [Release & Deployment](release-deployment.md)
- [Retrospective & Continuous Improvement](retrospective-continuous-improvement.md)
