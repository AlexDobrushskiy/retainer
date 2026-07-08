# Bootstrap interview

Goal: seed the vault with enough context that the next session can help effectively. NOT a census — the vault fills gaps later via passive learning. Target 20–40 minutes of the user's attention.

## Ground rules

- Conversational rounds of 3–5 questions. Use each round's answers to shape the next round's follow-ups. Free-form questions in chat; multiple-choice tools only for structural picks (modules, cadence).
- The first round starts immediately after the orientation message — no configuration questions before it.
- Anything may be skipped. Money and health are opt-in via the modules round at the end — never ask amounts or conditions before the user opts in.
- **Never invent.** Unanswered = `⚠️ to capture` marker in the file, listed in the first log entry.
- If the user handed you written answers instead (non-interactive), extract from those, flag everything else.

## Rounds

**1. Identity & daily shape** — name, age/life stage, household, location, languages. Fixed daily anchors (school runs, dog walks, standing commitments), typical day shape, sleep pattern and desired evening cutoff. → `context/bio.md`

**2. Work & capacity** — occupation, engagements/clients with hours and rates (rates only if finances module is on), how income works. Then, **as a separate question**: realistic focused hours per week. Don't derive it from the engagements — the gap between the two numbers is signal. → `context/bio.md`, Dashboard time budget

**3. Goals & projects** — this year's goals, this quarter's focus, active side projects, and dormant "someday" ideas (those go to a parking-lot section, not the active list). **Required cross-check:** map each goal to hours available; if a top goal has zero allocated hours, say so and record it as the vault's first open decision. → `context/goals.md`, Dashboard projects

**4. Self-knowledge** — "What do you already know goes wrong for you?" (overcommitting, novelty-jumping, procrastination flavors, energy dips). For each pattern, ask what counter-move works or should be tried — the counter-moves must be theirs, not imposed. Ask what past productivity systems failed and why (that failure mode is a design constraint for this vault). → `context/patterns.md`

**5. Working with the AI** — communication style (direct vs. gentle, pushback appetite, verbosity), how they capture thoughts today (voice memos, notes app — decides the inbox pipeline), planning cadence they'll actually sustain (full monthly/weekly/daily vs. weekly-only to start; when unsure, recommend starting weekly-only and tightening later), review cadence for goals. → `context/preferences.md`, kernel guard rails

Whenever an external source comes up in ANY round (a work calendar, health tracker, task app), ask how AI sessions should access it and record the answer as the source's access status. If there's no connection yet, the status is "not connected — ask {{NAME}} to read it out", written wherever the source is referenced. The vault must never instruct future sessions to consult a source it records no access path for.

**6. Optional modules** — now that the user has seen what the core covers, offer the extras, one line each: finances (income, invoices, runway), health/training (sleep, sport, events), travel (trip planning), people/CRM (contacts, conversation threads). Note that any can be added later. Then interview ONLY the chosen ones: finances — income streams, runway, what to track monthly; health/training — current activity, events, constraints/injuries; travel, people/CRM — analogous basics. → module files in `context/` or `active/`

## Writing the results

- Third person, factual, dated where relevant ("As of {{DATE}}...").
- Every `context/` file opens with `## TL;DR` — 3–6 lines a future session can triage from.
- The user's own phrasing for patterns and preferences beats paraphrase — quote them, but normalize obvious dictation/speech-to-text artifacts first (the meaning is theirs; the typo isn't).
- Numbers the user gave (hours, rates, cutoffs) go verbatim into the kernel's guard rails.
