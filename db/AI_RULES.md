## AI editing rules for Postgres DB guidelines

Scope: governs edits to files in `playbook/db/`.

Structure and style
- Keep the Quick checklist and detailed sections in sync.
- Sections: Naming, Primary keys, Foreign keys and actions, Timestamps, RLS (Row Level Security), Views, Indexes, Data types, RPCs / Functions, Migrations, Mapping tables and relationships, Constants and enums, Auditing (pgAudit).
- Tone: concise, professional, actionable. US English; lower_snake_case for identifiers.
- Include: Rationale, Risks, Exceptions when changing or adding rules.

Conventions to preserve
- Singular table names; `<table>_id` identity PKs; FK naming; cascade/null semantics.
- RLS helpers/policies (`is_platform_admin()`, `is_member_of()`); no DB views; index naming `idx_<table>_<column_or_purpose>`; `timestamptz`, `citext` usage.
- Mapping table naming `<left>_<right>` without `_map` (use `_link` only to avoid collisions).
- pgAudit and app-level auditing guidance for user/IP capture with `application_name` and custom GUCs.
- Helper functions: `is_platform_admin()` and `is_member_of(tenant_id bigint)`.
- Policy naming: `<table>_select`, `<table>_admin_all`.
- Common trigger: `trigger_set_updated_at()` for `updated_at` maintenance.

Editing process
- Keep diffs minimal; avoid reflowing unrelated text.
- Validate SQL examples conceptually.
- Ensure Quick checklist items match detailed section content exactly.

AI self-review checklist
- [ ] Checklist and details updated together
- [ ] Naming/examples consistent
- [ ] Rationale/risks/exceptions included
- [ ] No views introduced
- [ ] Tone/formatting consistent
- [ ] RLS policies and helper functions properly documented
- [ ] Index naming conventions followed
- [ ] Timestamp and trigger patterns consistent


