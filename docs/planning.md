# OctoAcme Project Planning

This document describes the planning process at OctoAcme — how work is structured, estimated, and scheduled to deliver projects predictably and transparently.

---

## Overview

OctoAcme follows an **iterative, sprint-based delivery model**. Planning happens at multiple levels:

- **Release planning** — defines the scope and milestones for an entire release
- **Sprint planning** — defines what will be delivered in the next sprint (typically 2 weeks)
- **Daily planning** — lightweight daily stand-up to sync on progress and blockers

---

## Backlog Management

The **Product Owner** is responsible for maintaining a prioritised product backlog. All work items (epics, user stories, tasks, bugs) are tracked in the project's issue tracker.

### Work Item Hierarchy

```
Epic
└── Feature
    └── User Story / Task
        └── Sub-task (optional)
```

### Backlog Refinement

A **Backlog Refinement** session is held at least once per sprint (mid-sprint is recommended). The goal is to ensure the top items are:

- Well-defined with clear acceptance criteria
- Estimated (using story points or t-shirt sizing)
- Free of unresolved dependencies

Attendees: Product Owner, Technical Lead, representative engineers, QA Engineer.

---

## Sprint Planning

Sprint planning takes place at the start of each sprint. The team:

1. Reviews the sprint goal proposed by the Product Owner
2. Selects user stories from the top of the backlog
3. Breaks stories into tasks and assigns effort estimates
4. Confirms each story has clear acceptance criteria and that the Definition of Ready (DoR) is met
5. Commits to the sprint backlog as a team

### Definition of Ready (DoR)

A user story is ready for sprint planning when:

- [ ] It has a clear description and acceptance criteria
- [ ] Dependencies are identified and resolved (or a plan exists)
- [ ] It has been estimated
- [ ] Required designs or technical spikes are complete
- [ ] The QA Engineer understands how it will be tested

---

## Estimation

OctoAcme uses **story points** (Fibonacci scale: 1, 2, 3, 5, 8, 13) to estimate relative effort. Estimation is a team activity, typically using planning poker to reach consensus.

Guidelines:
- A 1-point story is trivial (e.g., a config change)
- An 8-point story is large and should be considered for splitting
- Stories larger than 13 points **must** be split before entering a sprint

---

## Release Planning

At the start of each release cycle, the Project Manager facilitates a **Release Planning** session to:

- Define the release scope and target date
- Map epics and features to sprints
- Identify cross-team dependencies
- Agree on release milestones and review gates

The output is a high-level **Release Plan** that is maintained and updated throughout the release cycle.

---

## Definition of Done (DoD)

A user story is **Done** when:

- [ ] All acceptance criteria are met
- [ ] Code has been reviewed and approved (minimum 1 reviewer; 2 for critical paths)
- [ ] Unit and integration tests written and passing
- [ ] QA sign-off received
- [ ] Documentation updated (where applicable)
- [ ] Code merged to the main branch
- [ ] Deployed to the staging environment

---

## Related Documents

- [Project Initiation](project-initiation.md)
- [Execution & Tracking](execution-tracking.md)
- [Roles & Personas](roles-personas.md)
