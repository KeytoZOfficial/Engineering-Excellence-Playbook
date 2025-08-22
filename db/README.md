[(Back to main)](../README.md)

## Database standards

### In this page
- [Common rules](#common-rules)
- [Engines](#engines)

### Common rules
- Use singular table names; consistent identifier casing per engine conventions.
- Prefer explicit primary keys; avoid natural keys unless justified.
- Define foreign keys with clear on update/delete actions.
- Audit critical changes; ensure timestamp columns are maintained.
- Index for query patterns; validate with actual plans.
- Document migrations with rollback paths.

### Engines
- Postgres: see [Postgres guidelines](./postgres/README.md)
- MySQL: add `db/mysql/README.md` when applicable
- MongoDB: add `db/mongodb/README.md` when applicable

---

_Last updated: 2025-09-17_
