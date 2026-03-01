# OctoAcme Project Management Processes

This README provides a brief overview of OctoAcme's project management practices and serves as the entry point for the process documentation in this folder.

---

## Overview

OctoAcme follows an **iterative, sprint-based delivery model** that emphasises transparency, continuous improvement, and close collaboration between delivery teams and business stakeholders. Projects move through a structured lifecycle — from initiation through planning, execution, and release — with clearly defined roles, communication rhythms, and quality gates at each stage.

### Key Workflows

OctoAcme organises delivery into short sprints (typically 2 weeks). Each sprint begins with planning (selecting and committing to a set of backlog items), progresses through daily stand-ups and continuous integration, and closes with a sprint review (demonstrating completed work to stakeholders) and a retrospective (reflecting on process and agreeing on improvements). At a higher level, releases bundle multiple sprints and go through a formal pipeline of automated CI checks, QA sign-off, user acceptance testing, and a production deployment with a documented rollback plan.

### Personas & Roles

Delivery involves a small set of well-defined roles. The **Product Owner** owns the backlog and represents business value. The **Project Manager** is accountable for schedule, risk, and stakeholder communication. The **Technical Lead** guides architectural decisions and quality standards. **Software Engineers** implement and test features. The **QA Engineer** owns test strategy and sign-off. The **DevOps Engineer** manages CI/CD pipelines, environments, and deployments. A **UX/UI Designer** shapes user-facing experiences, while **Stakeholders and Business Representatives** provide domain expertise and approve deliverables.

### Communication Strategies

OctoAcme uses a layered communication model: day-to-day coordination happens in team chat and the issue tracker; sprint ceremonies (planning, stand-up, review, retrospective) provide structured synchronisation points; weekly status reports keep stakeholders informed of progress, RAG status, and active risks; and monthly steering-committee reviews give senior stakeholders and sponsors visibility across the programme. All formal decisions and persistent knowledge are documented in the wiki or process docs — chat is treated as transient. Risks with a score of 6 or higher are escalated to the Project Sponsor within one business day.

### Quality Assurance Practices

Quality is built in throughout delivery, not bolted on at the end. Every user story must meet a **Definition of Ready** before entering a sprint and a **Definition of Done** before it can be considered complete — including peer code review, passing automated tests, and QA sign-off. CI pipelines run on every pull request, covering build, lint, unit tests, and integration tests. The QA Engineer maintains test plans and regression suites, and executes functional and exploratory testing each sprint. Defect escape rate and deployment frequency are tracked as process health metrics and reviewed in release retrospectives.

---

## Process Documents

| Document | Description |
|---|---|
| [Project Initiation](project-initiation.md) | How new projects are formally started: business case, charter, stakeholder analysis, kick-off |
| [Planning](planning.md) | Backlog management, sprint planning, estimation, and Definitions of Ready and Done |
| [Execution & Tracking](execution-tracking.md) | Sprint ceremonies, work item workflow, status reporting, branching, and escalation |
| [Risks & Communication](risks-communication.md) | Risk register, response strategies, communication plan, and stakeholder schedule |
| [Release & Deployment](release-deployment.md) | Release pipeline, deployment practices, release checklist, and post-deployment activities |
| [Retrospective & Continuous Improvement](retrospective-continuous-improvement.md) | Sprint and release retrospectives, action log, process health metrics |
| [Roles & Personas](roles-personas.md) | Descriptions, responsibilities, and RACI matrix for all project roles |
