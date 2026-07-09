<!-- TEMPLATE: becomes decisions/README.md verbatim (no placeholders). -->

# Decisions

Synthesized outputs from chat sessions that would otherwise evaporate. When a conversation produces a real analysis, file it back as a page so the reasoning compounds across sessions instead of dying in chat history.

## When to create a decision page

**Yes:**
- A choice was made between options and the reasoning matters.
- A non-trivial trade-off analysis was performed, even if the call is "wait".
- A direction-setting conversation produced a conclusion that should bind future decisions.
- A previous decision was revisited and reaffirmed or reversed.

**No:**
- A factual update — goes in the relevant `context/` file.
- A new task or schedule item — goes in `active/`.
- A capture / brain dump — goes through `inbox/` triage.
- A small tactical pick that won't matter in a month.

## File naming

`YYYY-MM-DD-<short-slug>.md`

If a decision is later revisited, create a NEW dated file linking back via `supersedes:`. Never rewrite the original — only add a `superseded_by:` pointer to it.

## Page format

```markdown
---
date: YYYY-MM-DD
status: decided | open | revisited | superseded
topic: short tag
relates_to: ["[[Dashboard]]", "[[relevant-context-file]]"]
supersedes: <optional prior decision file>
superseded_by: <optional later decision file>
---

# <Decision title>

## Question
What was being decided, in one or two sentences.

## Context
What state of the world matters here. Link out — don't duplicate Dashboard or context files.

## Options considered
- **A**: ...
- **B**: ...

## Decision
What was chosen, and the core reason in one paragraph.

## Reasoning
What tipped the balance, what was discounted, which constraints dominated.

## Revisit conditions
What would reopen this (concrete triggers, not "someday").
```

## Maintenance rule for the AI

When a session matches the "Yes" criteria:
1. **Offer** to file it — never file silently; the user confirms.
2. Write the page in the format above.
3. Append a line to `log.md` (`## [YYYY-MM-DD] decision | <title>`).
4. Update `index.md` if the Decisions section lists individual entries.
5. Cross-link from related context/active files via `[[wikilinks]]`.
