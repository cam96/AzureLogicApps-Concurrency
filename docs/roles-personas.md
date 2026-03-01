# OctoAcme Roles & Personas

This document describes the key roles and personas involved in OctoAcme project delivery, including their responsibilities, authority levels, and how they interact across the project lifecycle.

---

## Core Roles

### Product Owner (PO)

**Responsibilities:**
- Owns and prioritises the product backlog
- Defines acceptance criteria for features and user stories
- Acts as the primary voice of the customer and business stakeholders
- Approves releases and signs off on completed increments
- Participates in sprint reviews and retrospectives

**Authority:** Final decision on scope and priority within the product backlog.

---

### Project Manager (PM)

**Responsibilities:**
- Plans and tracks project milestones, timelines, and budgets
- Facilitates sprint ceremonies (planning, stand-ups, reviews, retrospectives)
- Manages cross-team dependencies and escalates blockers
- Maintains the risk register and drives mitigation actions
- Produces status reports for stakeholders

**Authority:** Accountable for delivery schedule and resource allocation within the project.

---

### Technical Lead (Tech Lead)

**Responsibilities:**
- Guides architectural decisions and enforces technical standards
- Reviews and approves design proposals and significant pull requests
- Mentors engineers and supports resolution of technical blockers
- Coordinates with the DevOps engineer on infrastructure and CI/CD pipelines
- Contributes to estimation and sprint planning

**Authority:** Final decision on technical approach within the project.

---

### Software Engineer

**Responsibilities:**
- Implements features, bug fixes, and technical improvements
- Writes unit and integration tests for all new code
- Participates in code reviews, providing and acting on feedback
- Keeps work items updated and raises blockers promptly
- Follows OctoAcme coding standards and branching conventions

---

### QA Engineer

**Responsibilities:**
- Creates and maintains test plans, test cases, and regression suites
- Executes functional, integration, and exploratory testing
- Logs defects with clear reproduction steps and severity ratings
- Verifies fixes and closes defects after re-testing
- Contributes to acceptance-criteria definition during planning

---

### DevOps Engineer

**Responsibilities:**
- Maintains CI/CD pipelines, infrastructure-as-code, and deployment automation
- Monitors production systems and responds to alerts
- Manages environment provisioning and access controls
- Supports release preparation and coordinates deployment windows
- Documents runbooks and operational procedures

---

### UX/UI Designer

**Responsibilities:**
- Produces wireframes, prototypes, and high-fidelity designs
- Conducts user research and usability testing
- Collaborates with the Product Owner to translate requirements into designs
- Provides assets and design specifications to engineers
- Reviews implementations for design fidelity

---

### Stakeholder / Business Representative

**Responsibilities:**
- Provides business requirements and domain expertise
- Reviews and approves deliverables at key milestones
- Participates in sprint reviews and user-acceptance testing (UAT)
- Raises and prioritises change requests through the Product Owner

---

## Persona Summary Table

| Persona | Primary Focus | Typical Sprint Ceremonies |
|---|---|---|
| Product Owner | Scope & value | Planning, review, retrospective |
| Project Manager | Delivery & risk | All ceremonies |
| Technical Lead | Architecture & quality | Planning, stand-up, review |
| Software Engineer | Implementation | Planning, stand-up, review, retrospective |
| QA Engineer | Quality assurance | Planning, stand-up, review |
| DevOps Engineer | Infrastructure & delivery | Stand-up, release coordination |
| UX/UI Designer | User experience | Planning (design stories), review |
| Stakeholder | Business value | Review, UAT |

---

## RACI Matrix (summary)

| Activity | PO | PM | Tech Lead | Engineer | QA | DevOps |
|---|---|---|---|---|---|---|
| Backlog prioritisation | **A/R** | C | C | I | I | I |
| Sprint planning | A | **R** | C | R | R | I |
| Feature development | I | I | C | **R** | I | I |
| Code review | I | I | **A** | R | I | I |
| Test execution | I | I | I | I | **R** | I |
| Deployment | A | C | C | I | C | **R** |
| Release sign-off | **A** | R | C | I | C | I |

*A = Accountable, R = Responsible, C = Consulted, I = Informed*
