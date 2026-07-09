<!-- TEMPLATE: becomes AGENTS.md at the vault root. Fill {{...}}, prune module
     sections the user declined, keep every standing-rule block. Also write a
     one-line CLAUDE.md next to it containing exactly: @AGENTS.md
     (Claude Code imports the kernel through it; Codex/Cursor/Gemini/OpenCode
     read AGENTS.md natively.) -->

# {{NAME}}'s Vault — operating manual for AI sessions

Personal knowledge vault, maintained across sessions by an AI assistant. Read this file first, every session. Plain markdown; no tool besides a text editor is required.

## Vault structure

```
AGENTS.md               This file — the kernel. Rules + routing; procedures live in prompt/.
CLAUDE.md               One line (@AGENTS.md) — Claude Code's import of the kernel. Don't edit; edit AGENTS.md.
index.md                Content catalog of the vault (file → one-line summary). Maintain on note creation/rename/archival.
log.md                  Append-only chronological log of decisions, ingests, structural changes.
context/                Stable personal context. Every file has a ## TL;DR at top — triage from it before deep-reading.
active/                 Current state. Dashboard.md is the SINGLE SOURCE OF TRUTH for priorities and time budget.
decisions/              Synthesized decisions filed back from chat sessions. See decisions/README.md.
inbox/                  Unprocessed captures (voice memos, quick thoughts). Processed → archive/.
archive/                Processed and completed items. Never delete history — archive it.
prompt/                 Procedure runbooks (planning-guide.md, ...). Kernel holds triggers; runbooks hold the how.
_templates/             Note templates (capture-note.md, ...).
```

## File routing — what to read for which questions

<!-- List ONLY files that exist. Extend as the vault grows. -->

| Question domain | Read (in order) |
|---|---|
| Priorities, "what should I work on" | active/Dashboard.md, current plans in active/ |
| Career / work / income decisions | active/Dashboard.md, context/goals.md, context/bio.md{{, context/finances.md}} |
| Life decisions, trade-offs | context/goals.md, context/patterns.md, active/Dashboard.md, decisions/ (recent) |
| Scheduling, plans | active/Dashboard.md, context/preferences.md, prompt/planning-guide.md |
| How to communicate / push back | context/preferences.md |
| {{MODULE_DOMAINS}} | {{MODULE_FILES}} |

For decision/advice questions, always read Dashboard.md plus the routed files. Questions that look like simple math usually aren't — weigh {{NAME}}'s patterns, capacity, and goals, not just the numbers.

## Guard rails (from {{NAME}}, always apply)

- **Capacity:** ~{{HOURS}} h/week of focused work. Any new commitment must name what it displaces — do the hours math out loud.
- **Sleep:** {{SLEEP_RULE}}. Plans must respect it.
- **Known patterns to counteract** (details in context/patterns.md): {{PATTERNS_ONE_LINE_EACH_WITH_COUNTER_MOVE}}.
- **Fixed anchors:** {{DAILY_ANCHORS}}.

## Passive learning — update the vault, don't ask

When {{NAME}} shares information that updates their context (new facts, status changes, preferences, corrections), update the relevant `context/` or `active/` file in the same session, without being asked. Fill `⚠️ to capture` markers opportunistically. If unsure where it goes, err on the side of storing it.

## Inbox processing

When processing captures from `inbox/`:
1. Read the raw capture; extract actionable content.
2. Write a first-pass reflection into the note; set frontmatter `status: processed`, `reviewed: true`.
3. **Give feedback — never file silently.** Check alignment with goals and Dashboard priorities; for reflective notes, respond with a take (agreement, pushback, or a question), in the note and in chat.
4. Route content to the relevant vault files.
5. Move the note to `archive/`. Inbox is empty after processing.

## Planning

Three levels: **monthly > weekly > daily**, each referencing the one above. Templates, retrospective guides, and archive rules: `prompt/planning-guide.md` — read it when creating or closing any plan.

- Only ONE daily and ONE weekly plan in `active/` at a time; superseded plans get a retrospective, then move to `archive/`.
- Plans reference Dashboard.md, never duplicate it (Dashboard = strategy, plans = tactics).
- Don't over-schedule: respect the {{HOURS}} h/week budget and fixed anchors.
- **Proactive:** at session start, if no current plan exists for the active cadence, offer to create one.

## Decisions — file reasoning back as pages

When a session produces a real synthesis (option weighed, trade-off resolved, direction set), **offer** to file it in `decisions/` — never file silently, never let it evaporate. Criteria, naming, and page format: `decisions/README.md`. On filing: append to `log.md`, cross-link from related files.

## Maintenance duties (every session)

- **index.md** — update the relevant section whenever a note is created, renamed, or archived (skip `inbox/` and `archive/` internals).
- **log.md** — append an entry for filed decisions, processed captures, and structural changes; format in the file header. Skip routine edits.
- **Cross-link** related notes with `[[wikilinks]]`.
- **This file** — when a new standing rule or procedure emerges, add it here (dated) or as a `prompt/` runbook with a pointer here. Keep the kernel lean.

## Conventions

- Verify the actual day of week before writing dates — never guess. Dates always absolute (`2026-09-30`), never "next week".
- Filenames kebab-case; decisions and captures prefixed `YYYY-MM-DD`.
- Unconfirmed facts are marked `⚠️ to capture` or `(assumed — verify)`; confirm before building on them.
- Communication with {{NAME}}: {{COMMUNICATION_STYLE}}.
