---
name: vault-bootstrap
description: Use when a user wants to create a personal AI-maintained knowledge vault ("life OS", second brain, personal memory) from scratch — setting up a markdown folder that AI sessions will read and maintain across conversations, seeded by interviewing the user.
---

# Vault Bootstrap

Build a personal markdown vault whose **agent is the runtime and files are the memory**. The mechanics live in a kernel file (AGENTS.md) that routes questions to files and obligates the agent to maintain its own memory. Editor/sync tooling (Obsidian, git, Dropbox) is the user's choice and not part of the mechanics.

**Non-negotiable outcome:** every file in `templates/` exists in the finished vault, personalized. They ARE the mechanics — omitting one breaks a loop (index = findability, log = history, decisions = compounding reasoning, planning-guide = rituals, capture template = inbox state machine).

## Phases

Announce each phase transition in one line so the user always knows where they are (e.g. "Interview done — writing your files now, ~2 min", "Vault built — let me walk you through it").

**0. Orient.** Check the target folder is empty (if not, ask before touching anything — silently). Open with a short orientation message, then flow straight into the interview's first questions. The orientation sells the outcome, not the storage — do NOT pitch it as a "memory system" (an overloaded commodity phrase). It states, in plain words: this folder is what lets an AI assistant genuinely work for you rather than give generic answers — advice weighed against your actual goals, constraints, and patterns; help planning your days and weeks; tracking of projects, decisions, and ongoing threads so nothing gets re-argued or re-explained from scratch. The AI reads it each session and keeps it current as you talk. It's plain markdown, readable anywhere, no special tools. The plan: an interview (~20–40 min, any question skippable), then building the vault, then a walkthrough; optional areas (finances, health, travel, people) get decided at the end of the interview. The orientation contains nothing else — tool mechanics, permissions, or file-access notes wait until the build phase. That includes being unable to read this skill's own reference/template files right now: the interview needs no files, so proceed and resolve access when you reach the build step — do not mention it before then. No configuration questions before the interview — the first thing asked is about the person.

**1. Interview.** Follow `references/interview.md`. Conversational rounds of 3–5 questions, adapt follow-ups, let the user skip anything. Seed, don't exhaust — the vault fills gaps later via passive learning. Never invent facts: mark unknowns `⚠️ to capture`. Required cross-check: goals vs. stated weekly capacity — surface any deficit as the vault's first open decision. The final round offers the optional modules (with one-line descriptions) and interviews only the ones chosen. Core is always: `context/ active/ decisions/ inbox/ archive/ prompt/ _templates/`.

**2. Scaffold.** Create folders. Instantiate `templates/log.md`, `templates/index.md`, `templates/decisions-README.md` (→ `decisions/README.md`), `templates/planning-guide.md` (→ `prompt/planning-guide.md`), `templates/capture-note.md` (→ `_templates/capture-note.md`). Fill `{{...}}` placeholders; prune sections for modules the user declined. You may adapt formatting and naming to fit the vault, but **every rule stated inside a template must appear in the generated file** — reformat rules, never drop them.

**3. Write memory.** From the interview, write `context/` files (`bio.md`, `goals.md`, `preferences.md`, `patterns.md`, plus opted-in modules). **Every context file starts with a `## TL;DR` block** — future sessions triage from it. Then fill `templates/dashboard.md` → `active/Dashboard.md`: the single source of truth for priorities and time budget.

**4. Generate kernel.** Fill `templates/kernel.md` → `AGENTS.md` (the cross-agent standard file — Codex, Cursor, Gemini CLI, OpenCode and most agents read it natively), plus a one-line `CLAUDE.md` next to it containing exactly `@AGENTS.md` (Claude Code imports the kernel through it). The routing table must list **only files that exist**, guard rails must quote the user's own numbers and named patterns. Keep every standing-rule block from the template.

**5. Handoff.** Populate `index.md` with every created file; write the first `log.md` entry (`structure | vault bootstrapped`). Walk the user through the loops in plain words: capture → inbox processing, planning cadence + retrospectives, decision filing, passive learning. Offer to create the first weekly plan now as a live demo.

## Verify before declaring done

- [ ] Kernel: routing table, passive learning, maintenance obligations, guard rails with user's numbers
- [ ] All template-derived files present and personalized; TL;DR atop every `context/` file
- [ ] Dashboard exists; one-daily+one-weekly plan invariant stated
- [ ] decisions/README has yes/no criteria + revisit conditions + supersedes chain + **offer-first rule** (AI proposes, user confirms — never file silently)
- [ ] index.md lists all files; log.md has first entry **and states what NOT to log** (the "would I want this in 6 months?" bar); inbox flow archives (never deletes)
- [ ] No invented facts — unknowns marked `⚠️ to capture`
