<!-- TEMPLATE: becomes log.md at the vault root. Replace the first entry's
     date/details; delete this comment. -->

# Vault Log

Append-only chronological record of vault operations. Newest entries at the bottom. Never edit past entries.

## Format

Each entry starts with a parseable header:

```
## [YYYY-MM-DD] <type> | <short title>
```

Types:
- `decision` — a decision was filed in `decisions/` (link the page)
- `ingest` — a non-trivial inbox capture was processed (link source + destinations)
- `lint` — vault audit pass (summarize findings)
- `structure` — vault structural change (new folder, new convention, schema edit)

Skip routine tweaks (single-fact context updates, plan edits). The bar: "would I want to find this in 6 months?"

Quick query: `grep "^## \[" log.md | tail -20`

---

## [{{DATE}}] structure | vault bootstrapped

Vault created via vault-bootstrap skill. Initial interview seeded: {{FILES_CREATED_SUMMARY}}. Open items marked `⚠️ to capture`: {{OPEN_ITEMS_SUMMARY}}.
