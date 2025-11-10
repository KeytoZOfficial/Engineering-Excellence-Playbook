[(Back to main)](../README.md)

## Pull request guidelines

### In this page
- [Quick checklist](#quick-checklist)
- [PR description structure](#pr-description-structure)
- [Readiness checklist](#readiness-checklist)
- [Stacked PRs](#stacked-prs)
- [Labels and CI](#labels-and-ci)
- [Anti-patterns](#anti-patterns)

### Quick checklist
- Scope is focused; avoid mixing refactors and features.
- Description explains the why, what, and how; includes testing and risk notes.
- Linked Jira issue(s); PR title contains the main KEY when applicable.
- CI green: lint, type checks, unit/integration tests, security scans.
- Screenshots or recordings for UI changes; API examples for backend changes.
- Request appropriate reviewers (domain owner + peer).

### PR description structure
Use this structure for clarity:
- What: summary in 1–2 sentences.
- Why: problem statement, context, or user impact.
- How: key changes, trade-offs, and alternative options considered.
- Scope: what’s included and explicitly out of scope.
- Testing: how you tested; cases covered; screenshots/logs as relevant.
- Impact: migrations, performance, security, rollout flags/steps, release notes.
- Related: Jira keys, dependent PRs, feature flags, follow-ups.

### Readiness checklist
- [ ] Linting, type checks, and tests pass locally and in CI
- [ ] Backwards compatibility considered or breaking changes documented
- [ ] New dependencies reviewed for size, license, and maintenance
- [ ] Docs and changelog updated if user-facing or operationally impactful
- [ ] Feature flags or migrations are staged safely and reversible

### Stacked PRs
Use stacked PRs to split large efforts into small, reviewable steps while keeping momentum.

Concept:
- Create a sequence of small PRs where each depends on the previous one.
- Each PR should compile/test and be independently reviewable.
- Merge from the bottom of the stack upward.

How to create:
- Start PR 1 from `main` (or trunk).
- Branch PR 2 from PR 1’s branch; PR 3 from PR 2, and so on.
- Set each PR’s base branch to its immediate predecessor.
- Keep each PR focused (e.g., types, scaffolding, then implementation).

Workflow:
- Mark upper PRs as draft until predecessors are approved.
- Rebase the stack regularly to keep diffs clean.
- Address feedback in the smallest PR where it applies.
- Merge in order: bottom → top. Update bases as predecessors merge.

Tooling:
- Use your team’s stacking tool (e.g., Job Town) to help manage dependency chains and CI.
- Ensure the PR titles and descriptions clearly indicate position/order in the stack.

### Labels and CI
- Labels: `ready-for-review`, `breaking-change`, `security-review`, `needs-design`, `blocked`.
- CI gates: unit tests, integration/e2e (as applicable), lint, types, security scan.
- Require approvals from code owners for protected areas.

### Anti-patterns
- Giant PRs with mixed concerns and unclear testing.
- Drive-by refactors that inflate diffs.
- Merging top-of-stack PRs before predecessors.
- Hiding breaking changes in “fix” or “chore” PRs.

---

_Last updated: 2025-11-10_


