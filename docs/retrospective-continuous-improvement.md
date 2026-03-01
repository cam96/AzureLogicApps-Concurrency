# OctoAcme Retrospective & Continuous Improvement

This document describes OctoAcme's retrospective practices and how the team uses them to drive continuous improvement across process, tooling, and culture.

---

## Purpose

Retrospectives are the engine of continuous improvement at OctoAcme. Held at the end of every sprint, they give the team a regular, structured opportunity to reflect on how they are working — not just what they are delivering — and to make concrete improvements.

---

## Sprint Retrospective

### Format

OctoAcme uses the **Start / Stop / Continue** format by default, though teams may choose alternatives (e.g., *4Ls*, *Mad-Sad-Glad*, *Sailboat*) when a fresh perspective is useful.

| Column | Prompt |
|---|---|
| **Start** | What should we begin doing that we currently don't? |
| **Stop** | What are we doing that isn't adding value or is causing friction? |
| **Continue** | What is working well that we should keep doing? |

### Process

1. **Set the stage** (5 min) — PM opens the session, reminds the team of the working agreement (psychological safety, no blame)
2. **Gather data** (10 min) — Team members add items to each column (anonymous if the team prefers)
3. **Generate insights** (15 min) — Dot-vote to surface the most important themes; discuss the top items
4. **Decide on actions** (15 min) — For each key insight, agree on a concrete, measurable action with an owner and due date
5. **Close** (5 min) — PM summarises actions; team rates the retrospective (1–5) for continuous improvement of the retro itself

### Output

- **Action items** recorded in the team's action log with owner and target completion date
- Actions are reviewed at the start of the next sprint retrospective

---

## Retrospective Action Log

The Project Manager maintains a **Retrospective Action Log** to track improvement commitments. Each entry includes:

| Field | Description |
|---|---|
| ID | Unique identifier (e.g., `RETRO-2024-S12-001`) |
| Action | Description of the improvement |
| Owner | Team member responsible |
| Sprint raised | Sprint in which the action was identified |
| Due date | Target completion date |
| Status | Open / In Progress / Done / Deferred |
| Outcome | What actually happened (completed on closure) |

---

## Beyond the Sprint Retrospective

### Release Retrospective

At the end of each release, the team holds a **Release Retrospective** with a broader focus, covering:

- What went well / what to improve across the entire release
- Key metrics (velocity trend, defect rates, deployment frequency, mean time to recovery)
- Process improvements to carry forward into the next release

Attendees: Full team, Product Owner, Project Manager; stakeholders may be invited for selected topics.

### Process Health Metrics

OctoAcme tracks the following metrics to objectively assess process health:

| Metric | Target |
|---|---|
| Sprint goal achievement rate | ≥ 80% |
| Defect escape rate (to production) | Trending down |
| Deployment frequency | ≥ 1 per sprint |
| Mean time to recovery (MTTR) | < 1 hour for P1 |
| Retrospective action completion rate | ≥ 70% per sprint |

The Project Manager reviews these metrics monthly and shares a summary with the team.

---

## Psychological Safety

Retrospectives only work if team members feel safe to speak honestly. OctoAcme's working agreement for retrospectives includes:

- **No blame** — focus on systems and processes, not individuals
- **Confidential** — what is said in the retro stays in the retro (unless the team agrees to share)
- **One voice** — respect turn-taking; avoid interrupting
- **Curiosity over criticism** — ask questions to understand before drawing conclusions

---

## Related Documents

- [Execution & Tracking](execution-tracking.md)
- [Release & Deployment](release-deployment.md)
- [Roles & Personas](roles-personas.md)
