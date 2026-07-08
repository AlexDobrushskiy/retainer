<!-- TEMPLATE: becomes prompt/planning-guide.md. Adjust cadence if the user
     opted for lighter planning (e.g. weekly-only); keep the retrospective
     sections — they are what makes plans compound. Fill {{...}}; delete this
     comment. -->

# Planning Guide

Read this when creating or archiving any plan.

## Planning hierarchy

Three levels: **Monthly > Weekly > Daily**. Each references the level above; none duplicates Dashboard.md (Dashboard = strategy, plans = tactics). Only one daily and one weekly plan live in `active/` at a time.

Naming: `Daily plan YYYY-MM-DD.md`, `Weekly plan YYYY-MM-DD - YYYY-MM-DD.md`, `Monthly plan YYYY-MM.md` — all in `active/`.

## Monthly plan template

```markdown
# Monthly Plan — [Month Year]
## Time allocation target
<!-- hours split across commitments; must sum to ≤ {{HOURS}} h/week -->
## Milestones
<!-- 3-5 outcomes; each traceable to a goal in context/goals.md -->
## Weekly plans
<!-- links accumulate here as weeks close -->
## Monthly retrospective
<!-- filled at month close: hit/missed milestones, allocation actuals vs target, one structural insight -->
```

## Weekly plan template

```markdown
# Weekly Plan — [Mon date] to [Sun date]
## Goals
<!-- max 5, each linked to a monthly milestone or Dashboard priority -->
## Daily plans
<!-- links accumulate -->
## Weekly retrospective
### Completion rate
### Recurring skips        <!-- what got avoided twice+ — name the pattern, ask why -->
### Disruption patterns
### Energy & sleep
### Key insight
```

## Daily plan template

```markdown
# Daily Plan — [Weekday], [Month Day, Year]
<!-- VERIFY the weekday with the `date` command — never guess -->
## Schedule
<!-- time-blocked; respect fixed anchors: {{DAILY_ANCHORS}}; nothing after {{EVENING_CUTOFF}} -->
## Tasks
<!-- ≤ 3 primary + secondary list -->
## Carried from [previous day]
<!-- items marked ❓ carried forward; 3+ carries = flag it in the retrospective -->
## Day retrospective
<!-- done/skipped + one line why; energy note -->
```

## Auto-update rules

1. Creating a new daily plan: first close the previous one — fill its retrospective, move it to `archive/`, carry unfinished items forward explicitly.
2. Same at week/month boundaries: retrospective → archive → new plan referencing the closed one's insights.
3. Mid-day updates: update the plan FILE first (mark done, adjust schedule), then summarize in chat.
4. Before scheduling, check the user's calendar(s) if connected, and current capacity ({{HOURS}} h/week budget).

## Retrospective analysis guide

When closing a week or month, look for: recurring skips (same task avoided repeatedly — surface it and ask why), over-scheduling (completion < 60% two periods running — cut volume), guard-rail erosion (sleep/anchor violations), and drift between plan contents and Dashboard priorities (one of them is stale — ask which).
