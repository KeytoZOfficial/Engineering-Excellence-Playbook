[(Back to main)](../README.md)

## Jira task management guidelines

### In this page
- [Quick checklist](#quick-checklist)
- [Definitions of Ready and Done](#definitions-of-ready-and-done)
- [Backlog grooming (refinement)](#backlog-grooming-refinement)
- [Sprint planning](#sprint-planning)
- [Daily and weekly standups](#daily-and-weekly-standups)
- [Sprint demos](#sprint-demos)
- [Sprint retrospective](#sprint-retrospective)
- [Release management](#release-management)
- [Linking code and Jira](#linking-code-and-jira)
- [Tools and Jira features by phase](#tools-and-jira-features-by-phase)
- [Anti-patterns](#anti-patterns)

### Quick checklist
- Tickets follow a clear template: problem, acceptance criteria, test notes.
- Story points set; dependencies, risks, and owners identified.
- WIP limits respected; no mid-sprint scope creep without trade-off call.
- Daily standup time-boxed; blockers flagged and tracked.
- Demos map to “Done” tickets; retros capture actionable follow-ups.
- Releases have changelog, rollback, and communication plan.

### Definitions of Ready and Done
- Ready
  - Clear problem statement and acceptance criteria (Given/When/Then preferred).
  - Test notes provided; dependencies known; estimate assigned; owner identified.
  - Design/arch sign-off provided when needed.
- Done
  - Acceptance criteria met; tests added/updated; docs updated where applicable.
  - Deployed (as defined by your team’s policy); monitoring/alerts updated.
  - Linked PR(s) merged; feature flags configured for rollout if used.

### Backlog grooming (refinement)
- Objective: make upcoming work small, clear, and estimable.
- Practices
  - Break epics into stories sized to complete within a sprint.
  - Add acceptance criteria and test notes; attach designs and diagrams.
  - Estimate with story points; highlight risks and external dependencies.
  - Flag candidates for stacked PRs or multi-sprint delivery.

### Sprint planning
- Capacity first: consider holidays, on-call, meetings, carryover.
- Commit to a realistic sprint goal that aligns with roadmap.
- Pull “Ready” tickets until capacity is filled; respect WIP limits.
- Avoid adding scope mid-sprint; if necessary, explicitly trade off other work.

### Daily and weekly standups
- Daily standup (10–15 minutes, time-boxed)
  - What was done yesterday? What will be done today? Any blockers?
  - Keep it focused; deep dives move to follow-ups.
  - Provide async updates in a thread if you cannot attend.
- Weekly team sync (30–45 minutes)
  - Cross-team updates, risks, sequencing, and upcoming releases.
  - Review burndown, spillover risk, and adjust plans if needed.

### Sprint demos
- Purpose: show working software tied to “Done” tickets, not slides.
- Include: what problem, what changed, and how we validated it.
- Recordings/screenshots attached to relevant Jira tickets for traceability.

### Sprint retrospective
- Time-box: 45–60 minutes; involve the whole team.
- Structure: what went well, what didn’t, what to try next.
- Produce 1–3 concrete actions with owners and due dates; track to completion.

### Release management
- Prepare: changelog, migration notes, feature flags, and rollback plan.
- Validate: staging/preview sign-off; performance and error budgets checked.
- Communicate: stakeholders notified with impact and support instructions.
- Post-release: monitor, triage, and document learnings for future sprints.

### Linking code and Jira
- Branch names: `feature/JIRA-123-short-slug`, `fix/JIRA-456-brief-cause`.
- PR titles include the main Jira key; PR description links all related keys.
- Commits contain Jira keys (subject or footer) per the commit guidelines.
- Automation may transition tickets on PR merge; ensure states are accurate.

### Tools and Jira features by phase
- Backlog grooming (refinement)
  - Jira: Backlog view with Epics panel; estimation via Story points field.
  - Tooling: Planning Poker Online for collaborative estimation (Jira plugin available): `https://planningpokeronline.com/`
- Sprint planning
  - Jira: Scrum boards and Sprints; set sprint goals, assign issues, set initial estimates.
  - Jira reports: Capacity via assignee filters; review Velocity and Burndown from previous sprints.
- Daily standups
  - Jira: Active sprint board (“To Do/In Progress/Done”) and “Assigned to me” filters for quick status.
  - Dashboards: Saved filters, swimlanes by assignee, and quick filters for blockers/priority.
- Weekly team sync
  - Jira: Dashboards combining Burndown, Velocity, Cumulative Flow Diagram, and Control Chart.
  - Use filters to review spillover risk and dependency status across teams.
- Sprint demos
  - Jira: Demo only “Done” issues; attach screenshots or short recordings directly to tickets.
  - Link PRs and deployments in the Development panel for traceability.
- Sprint retrospective
  - Jira: Track retro action items as tickets in an improvement project with labels (e.g., `retro-action`).
  - Use dashboards to follow-through on owners and due dates.
- Release management
  - Jira: Versions/Releases; set Fix Version on issues, manage release notes, and track status.
  - Link CI/CD deployments to versions for status visibility where integrated.

### Anti-patterns
- Vague tickets with missing acceptance criteria or test notes.
- Carrying large epics into sprints without slicing.
- Overcommitting capacity; chronic mid-sprint scope changes.
- Standups that devolve into status meetings without action on blockers.

---

_Last updated: 2025-11-10_


