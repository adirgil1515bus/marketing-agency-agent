# Instructions for Claude Code — APEX Digital Project

This file is automatically read by Claude Code whenever it opens this project.
Follow these instructions in every session.

---

## What this project is

APEX Digital is a multi-agent AI system that operates as a Google Ads management agency.
- **Phase 1 (complete):** Hermes Agent as the core platform, configured with a custom persona and skills
- **Phase 2 (planned):** CrewAI specialist agents + web dashboard + real Google Ads API

Read `README.md` for full architecture and setup details.
Read `CHANGELOG.md` to understand what has been done so far and what is currently in progress.

---

## Rule: Always read CHANGELOG.md first

At the start of every session, read `CHANGELOG.md` to understand the current state of the project before doing any work.

---

## Rule: Always update CHANGELOG.md at the end of every session

At the END of every session (before the conversation closes), append a new entry to `CHANGELOG.md` at the TOP of the entries list (below the intro, above all previous entries).

Use this format exactly:

```
## Session N — YYYY-MM-DD
**Who:** [Adir / Brother / Both] + Claude (Claude Code, [model name])
**Focus:** [one-line summary of the session goal]

### What was done
- [bullet: specific change made]
- [bullet: specific change made]

### Current state after this session
- [what is working / what is the overall status now]

### Next priorities
- [what should be done next]
```

This log is how both Adir and his brother stay in sync. It is also how any new Claude instance gets fully up to speed. Keep it accurate and specific — not vague summaries.

---

## Who works on this project

- **Adir** — owner, using personal GitHub account `adirgil1515bus`
- **Brother** — collaborator (GitHub TBD), has his own Claude Code instance

Both work independently but share the same repo. The CHANGELOG is the sync point between them.

---

## Key file locations

| File | Purpose |
|---|---|
| `README.md` | Full project documentation |
| `CHANGELOG.md` | Session-by-session change log |
| `CLAUDE.md` | This file — instructions for Claude |
| `soul/SOUL.md` | APEX Digital agent persona (copy to ~/.hermes/SOUL.md) |
| `skills/*.md` | Custom Hermes skill definitions |
| `data/mock_campaigns.json` | Mock Google Ads data (8 campaigns) |
| `config/hermes_config.yaml` | Hermes configuration |

---

## Hermes system files (local, not in repo)

| File | Purpose |
|---|---|
| `~/.hermes/.env` | API keys — ANTHROPIC, VOICE_TOOLS_OPENAI_KEY |
| `~/.hermes/SOUL.md` | Active persona (must match soul/SOUL.md) |
| `~/.hermes/config.yaml` | Model: anthropic/claude-sonnet-4-6 |

---

## Current known issues

- **OpenAI API key security:** The previous VOICE_TOOLS_OPENAI_KEY was shared in chat and must be regenerated at platform.openai.com. Update `~/.hermes/.env` with the new key.
- **Brother collaborator:** Not yet added to GitHub repo. Need his GitHub username.

---

## Phase 2 — what's planned (do not build yet)

- CrewAI specialist agents: Campaign Manager, Data Analyst, Keyword Researcher, Optimizer, Copywriter, Market Intelligence, Reporter
- Web dashboard: FastAPI + SQLite + WebSocket
- Real Google Ads API integration
- WhatsApp/Telegram messaging interface via Hermes gateway

Do not start Phase 2 work without Adir explicitly asking for it.
