# vault-bootstrap

An installable [Agent Skill](https://agentskills.io) that builds you a **personal, AI-maintained knowledge vault** — a plain-markdown folder your coding agent reads and maintains across sessions: who you are, what you're working toward, your plans, your decisions, your patterns.

I run my life on a vault like this — morning planning, decision filing, voice-note processing, the works. I wrote about it here: [**I'm terrible at organizing my life — so I built an AI that does it**](https://dobrushskiy.name/blog/built-an-ai-that-organizes-my-life/). This skill packages the setup so you can replicate it in about 30 minutes.

**Opinionated by design.** This is not a neutral note-taking template. It's the exact structure and operating rules I use daily — an agent that updates its own memory without being asked, plans that close with retrospectives, decisions filed as pages instead of evaporating into chat history. The interview adapts it to your life; the mechanics stay.

## What you get

After the interview, your folder looks like this:

```
AGENTS.md          The kernel — routing table, guard rails, standing rules. Any agent reads it.
CLAUDE.md          One line (@AGENTS.md) so Claude Code loads the same kernel.
index.md           Catalog of every file in the vault.
log.md             Append-only history of vault operations.
context/           Who you are: bio, goals, preferences, known patterns (+ opt-in modules).
active/            Dashboard (single source of truth for priorities) + current plans.
decisions/         Dated decision pages — reasoning that compounds instead of evaporating.
inbox/             Raw captures (voice memos, quick thoughts) → processed → archive/.
archive/           History. Nothing is ever deleted.
prompt/            Procedure runbooks (planning guide, ...).
_templates/        Note templates.
```

## How it works

1. **Interview** (~20–40 min, every question skippable) — conversational rounds: daily shape, work and real capacity, goals, what already goes wrong for you and what counter-moves work, how you want the AI to talk to you. Finance / health / travel / people modules are opt-in at the end.
2. **Build** — the skill scaffolds the folders and writes your context files, dashboard, and the kernel. It never invents facts: anything you skipped is marked `⚠️ to capture` for later.
3. **Walkthrough** — it explains the loops (capture → inbox processing, planning cadence, decision filing) and offers to create your first weekly plan as a live demo.

From then on, any agent session opened in that folder knows you — and keeps the vault current as you talk to it.

## Install

### Claude Code

```
/plugin marketplace add AlexDobrushskiy/vault-bootstrap
/plugin install vault-bootstrap@vault-bootstrap
```

### Codex, Gemini CLI, Cursor, or any Agent Skills client

```bash
git clone https://github.com/AlexDobrushskiy/vault-bootstrap
mkdir -p ~/.agents/skills
cp -r vault-bootstrap/skills/vault-bootstrap ~/.agents/skills/
```

(OpenCode also reads `~/.claude/skills/`, so a Claude Code install covers it too.)

## First run

Open your agent **in a new, empty folder** and say:

> Set up my personal knowledge vault — use the vault-bootstrap skill.

## Privacy

Everything stays in the folder you run it in. Plain markdown, no network calls, no accounts, no services. Editor and sync are your choice — Obsidian, git, Syncthing, Dropbox, or nothing at all.

## License

MIT
