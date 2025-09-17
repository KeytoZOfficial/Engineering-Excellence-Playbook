[(Back to main)](../README.md)

## Documentation guidelines

### In this page
- [Goals](#goals)
- [Document skeleton](#document-skeleton)
- [Writing style](#writing-style)
- [Headings and anchors](#headings-and-anchors)
- [Checklists](#checklists)
- [Cross-linking](#cross-linking)
- [Naming and terminology](#naming-and-terminology)
- [Examples](#examples)
- [Maintenance](#maintenance)
- [Review checklist (for PRs touching docs)](#review-checklist-for-prs-touching-docs)

These standards keep our playbook readable, consistent, and easy to navigate.

### Goals
- Consistency across sections and repos
- Scannability with clear headings, bullets, and checklists
- Linkability with stable anchors and cross-references

### Document skeleton
Every guidelines README should follow this shape:

1. Top nav: `[(Back to main)](../README.md)` (or root if at repo root)
2. H2 title: concise, noun-phrase (e.g., `## Engineering standards`)
3. Mini TOC: `### In this page` with major anchors
4. Checklist: short, actionable items
5. Sections: detailed guidance grouped by topic
6. Horizontal rule `---`
7. Footer: `_Last updated: YYYY-MM-DD_`

### Writing style
- Prefer short sentences and active voice
- Use bullets and numbered lists over long paragraphs
- Start sections with a brief “why”, then give rules and examples
- Use consistent casing for headings; avoid renaming headings often
- Avoid fluff; favor specific, testable guidance

### Headings and anchors
- Use H2 for the page title (`##`), H3 for major sections, H4 for subsections
- Keep headings stable to preserve anchor links in cross-references
- If you rename a heading, update inbound links in the repo

### Checklists
- Each item should be actionable
- Mirror checklists with the detailed rules below them
- Use `[ ]` for unchecked items in templates; avoid mixing `[x]`

### Cross-linking
- Link to related rules in other domains (e.g., naming in engineering and db)
- Always add a back-link to the main `README.md` at the top

### Naming and terminology
- Use precise, unambiguous terms; avoid plurals in naming guidance
- Prefer descriptive postfixes for collections: `List`, `Map`, `Set`, `Array`, `Collection`

### Examples
- Provide at least one good/bad example for non-trivial rules
- Format examples with fenced code blocks and language tags

### Maintenance
- Update the “Last updated” footer on substantive changes
- Keep mini TOCs in sync when adding headings
- When adding a new section, add it to the root README quick navigation if top-level

### Review checklist (for PRs touching docs)
- [ ] Follows the skeleton and style rules above
- [ ] Headings and anchors are stable or updated references provided
- [ ] Checklists mirror the detailed content
- [ ] Back-to-main link exists and is correct
- [ ] Mini TOC present and accurate
- [ ] Last updated footer set to today’s date


---

_Last updated: 2025-09-16_


