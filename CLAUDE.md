# Instructions for Claude Code — APEX Digital Project

This file is automatically read by Claude Code whenever it opens this project.
Follow ALL instructions here in every session, without exception.

---

## What this project is

APEX Digital is a multi-agent AI system that operates as a Google Ads management agency.
- **Phase 1 (complete):** Hermes Agent as the core platform, configured with a custom persona and skills
- **Phase 2 (planned):** CrewAI specialist agents + web dashboard + real Google Ads API

Read `README.md` for full architecture and setup details.
Read `CHANGELOG.md` to understand everything that has been done so far.

---

## Who works on this project

| Person | GitHub username | Branch to work on |
|---|---|---|
| Adir (owner) | `adirgil1515bus` | `adir` |
| Asaf (collaborator) | `asaf3698` | `asaf` |

Both work independently but share the same GitHub repository.
The `main` branch [the primary stable version of the code] is the source of truth.
Neither person works directly on `main` — all work happens on personal branches.

---

## Branch Rules — READ THIS CAREFULLY

### What each branch is for

- **`main`** — The stable, approved version of the project. Never commit directly here. Only updated via Pull Requests [a request to merge your work into the main branch, reviewed and approved before it goes in].
- **`adir`** — Adir's personal working branch. Only Adir and his Claude work here.
- **`asaf`** — Asaf's personal working branch. Only Asaf and his Claude work here.

### The golden rule
**Never work on someone else's branch. Never push to `main` directly.**
If you are Adir's Claude → only commit to `adir`.
If you are Asaf's Claude → only commit to `asaf`.

---

## Start of Every Session — Mandatory Checklist

Run these commands before doing ANY work:

```bash
# 1. Check which branch you are currently on
git branch
# The branch with * is the active one

# 2. Switch to YOUR branch (replace with the correct name)
git checkout adir         # if you are Adir's Claude
git checkout asaf         # if you are Asaf's Claude

# 3. Sync your branch with the latest from main
# (picks up any changes the other person merged since your last session)
git pull origin main

# 4. Push the sync to your remote branch
git push origin adir      # or asaf
```

Then read `CHANGELOG.md` to catch up on what the other person did since your last session.

---

## During the Session

- Commit [save a snapshot of your changes to git] regularly — after each meaningful change, not only at the end.
- Use clear, descriptive commit messages so the other person understands what you did.

```bash
# Stage specific files you changed
git add skills/new-skill.md

# Or stage all changed files
git add .

# Commit with a message
git commit -m "Add competitor analysis skill for e-commerce clients"

# Push to your branch on GitHub
git push origin adir      # or asaf
```

---

## End of Every Session — Mandatory Checklist

1. **Update CHANGELOG.md** — add a new entry at the TOP (see format below)
2. **Commit and push everything:**

```bash
git add .
git commit -m "Session summary: [one-line description of what was done]"
git push origin adir      # or asaf
```

3. **Open a Pull Request [PR] if the work is ready to go into main:**
   - Go to: https://github.com/adirgil1515bus/marketing-agency-agent
   - Click "Pull Requests" → "New Pull Request"
   - Set: base = `main`, compare = your branch (`adir` or `asaf`)
   - Write a short description of what you built
   - Tag the other person to review it before merging

---

## CHANGELOG.md — How to Update It

Add a new entry at the TOP of the file (below the intro section, above all previous entries).

```
## Session N — YYYY-MM-DD
**Who:** [Adir / Brother] + Claude (Claude Code, [model name])
**Branch:** [adir / asaf]
**Focus:** [one-line summary of the session goal]

### What was done
- [specific change 1]
- [specific change 2]

### Current state after this session
- [overall project status now]

### Next priorities
- [what should happen next — so the other person knows what's coming]
```

Be specific. This log is how both Adir and Asaf (and their Claudes) stay in sync without needing to call each other.

---

## How to Avoid Conflicts [when two people edit the same file]

### Dividing work
Before starting a new task, check CHANGELOG.md to see what the other person is currently working on. If they are editing a file, avoid editing that same file until their changes are merged into `main`.

### If CHANGELOG.md has a conflict [when git can't auto-merge because both people edited the same spot]
Git will mark the conflict in the file like this:
```
<<<<<<< adir
Session 5 — 2026-06-01 (Adir's entry)
=======
Session 5 — 2026-05-31 (Brother's entry)
>>>>>>> asaf
```
Fix it by keeping BOTH entries (Adir's above, Asaf's below), then remove the conflict markers. Commit the fix.

---

## Merging to Main — When and How

Merge your branch into `main` when:
- A feature or skill is fully working
- The CHANGELOG has been updated
- The other person has reviewed it (or it's a small fix)

Steps:
```bash
# Make sure your branch is up to date first
git pull origin main
git push origin adir      # or asaf

# Then go to GitHub and open a Pull Request
```

After a PR is merged into `main`, BOTH people must sync their branches:
```bash
git pull origin main
git push origin adir      # or asaf — to keep your branch up to date
```

---

## Division of Responsibility (default — can be changed anytime)

| Area | Default owner |
|---|---|
| Hermes skills (`skills/`) | Either — but not at the same time |
| Mock data (`data/`) | Agree before editing — shared file |
| Agent persona (`soul/SOUL.md`) | Agree before editing — shared file |
| Phase 2 planning | Both together |
| CLAUDE.md / README.md | Whoever needs to update it — communicate first |

If both people need to edit the same file in the same session, one person goes first and merges, then the other syncs and goes second.

---

## Key File Locations

| File | Purpose |
|---|---|
| `README.md` | Full project documentation |
| `CHANGELOG.md` | Session-by-session change log (the sync point) |
| `CLAUDE.md` | This file — mandatory instructions for every Claude instance |
| `soul/SOUL.md` | APEX Digital persona (copy to `~/.hermes/SOUL.md` on your machine) |
| `skills/*.md` | Custom Hermes skill definitions |
| `data/mock_campaigns.json` | Mock Google Ads data (8 campaigns) |
| `config/hermes_config.yaml` | Hermes configuration |

---

## Hermes System Files (local, not in GitHub repo)

These live on each person's Mac — they are NOT shared via GitHub and must be set up individually.

| File | Purpose |
|---|---|
| `~/.hermes/.env` | API keys: ANTHROPIC key, VOICE_TOOLS_OPENAI_KEY |
| `~/.hermes/SOUL.md` | Active persona — must match `soul/SOUL.md` from the repo |
| `~/.hermes/config.yaml` | Model: `anthropic/claude-sonnet-4-6` |

When Asaf sets up his machine, he must:
1. Install Hermes (see README.md)
2. Copy `soul/SOUL.md` → `~/.hermes/SOUL.md`
3. Add his own API key to `~/.hermes/.env`

---

## Current Known Issues

- **OpenAI API key:** The VOICE_TOOLS_OPENAI_KEY in `~/.hermes/.env` on Adir's machine was exposed in chat and must be regenerated at platform.openai.com.
- **Asaf GitHub invite:** Sent to `asaf3698` — he needs to accept the invite at github.com/notifications before he can push to the repo.

---

## Phase 2 — What's Planned (Do NOT build yet)

- CrewAI specialist agents: Campaign Manager, Data Analyst, Keyword Researcher, Optimizer, Copywriter, Market Intelligence, Reporter
- Web dashboard: FastAPI + SQLite + WebSocket
- Real Google Ads API integration
- WhatsApp/Telegram messaging interface via Hermes gateway

Do not start Phase 2 work without Adir explicitly asking for it.
