[(Back to main)](../README.md)

## Code review guidelines

### In this page
- [Quick checklist](#quick-checklist)
- [Select the right reviewers](#select-the-right-reviewers)
- [What to look for](#what-to-look-for)
- [Size and pace](#size-and-pace)
- [Feedback style](#feedback-style)
- [Ownership and SLAs](#ownership-and-slas)
- [Automate where possible](#automate-where-possible)
- [When to approve or block](#when-to-approve-or-block)
- [Anti-patterns](#anti-patterns)
- [References](#references)

### Quick checklist
- Ensure reviewer(s) with domain ownership are requested; add at least one peer and one owner.
- Confirm rebase/merge state is clean; no unintended diffs from outdated base.
- Run and verify linting/formatting (e.g., ESLint, Prettier) pass in CI.
- Avoid reinventing existing utilities/components; prefer reuse and refactors.
- Confirm tests exist and cover critical paths, edge cases, and regressions.
- Assess modularity and separation of concerns; avoid God objects and long functions.
- Validate architecture decisions align with approved designs/org standards.
- Keep reviews to 200–400 LOC per pass; ask for splits if larger.
- Leave constructive, actionable comments with rationale and examples.

### Select the right reviewers
- Include code owners for impacted areas; use OWNERS/CODEOWNERS if configured.
- Add one peer for readability and maintainability feedback.
- Add a security reviewer when touching auth, crypto, secrets, or data boundaries.
- Prefer continuity: if earlier PRs in a series were reviewed by Alice, keep Alice in the loop.

### What to look for
- Readability
  - Clear naming, small functions, minimal redundancy, no dead/commented-out code.
  - Comments explain non-obvious rationale, not what the code literally does.
- Correctness
  - Inputs validated; error paths handled; boundary conditions covered.
  - Idempotency, ordering, and concurrency considerations addressed where relevant.
- Security
  - No injection risks; safe parameterization; secrets not logged or committed.
  - Access controls enforced; least privilege maintained; dependency risks considered.
- Performance
  - Algorithmic complexity reasonable; hot paths measured or justified.
  - Avoid unnecessary allocations, synchronous I/O in request paths, N+1 queries.
- Architecture and modularity
  - Clear boundaries, encapsulation, and layering; no cross-layer leaks.
  - Feature flags and migrations handled safely; backwards compatibility when needed.
- Reuse over re-implement
  - Prefer existing helpers/components; extract shared pieces into libraries when general.
  - Remove duplication opportunistically when low-risk.
- Tests and coverage
  - Tests are meaningful and resilient (avoid over-mocking and implementation coupling).
  - Critical scenarios, error paths, and regressions included; flaky tests avoided.
- Dependencies and rebase/merge
  - PR is rebased on latest main (or appropriate base); no unrelated diffs.
  - New dependencies are scrutinized (size, license, maintenance, security posture).
- Linting and formatting
  - ESLint, type checks, and formatters pass locally and in CI.
  - No style-only diffs mixed with logical changes unless explicitly a formatting PR.

### Size and pace
- Don’t review more than 200–400 LOC per session to maintain quality.
- Ask authors to split large PRs into logical, reviewable chunks (consider stacked PRs).
- Avoid rushing approvals close to deadlines; negotiate scope if needed.

### Feedback style
- Be specific, constructive, and kind. Prefer suggestions over vague critiques.
- Explain the “why”; link to standards or examples when possible.
- Use blocking comments only for correctness, safety, or standards violations.
- Prefer “could” over “must” for non-critical nits; batch nits in a single comment.

### Ownership and SLAs
- Authors should respond within the team’s SLA (e.g., 1 business day for initial responses).
- Reviewers should aim to respond within the same SLA; acknowledge if delayed.
- Authors are responsible for driving the PR to completion and requesting re-reviews.

### Automate where possible
- Enforce linters/formatters, tests, type checks, security scans in CI.
- Use pre-commit hooks for faster local feedback.
- Use PR templates and checklists to standardize context and expectations.

### When to approve or block
- Approve when: scope is clear; tests pass; standards met; risks mitigated; no critical issues remain.
- Block when: correctness/security risks, architectural violations, or missing critical tests exist.
- Comment-only when: issues are minor or discretionary; do not block merge.

### Anti-patterns
- “Drive-by” approvals without reading the diff.
- Mixing large refactors with behavioral changes.
- Introducing new patterns/libraries without prior design review.
- Excessive bikeshedding on style that tools can enforce.

### References
- `https://blog.bitsrc.io/effective-code-review-practices-for-javascript-e627816dcf0b`
- `https://static1.smartbear.co/support/media/resources/cc/book/code-review-cisco-case-study.pdf`
- `https://storage.googleapis.com/gweb-research2023-media/pubtools/4476.pdf`
- `https://www.atlassian.com/blog/add-ons/code-review-best-practices`

---

_Last updated: 2025-11-10_


