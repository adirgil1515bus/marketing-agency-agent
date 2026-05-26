# APEX Digital — AI-Powered Google Ads Agency

A multi-agent AI system that operates as a full Google Ads management company.
Built by Adir and his brother, powered by Claude Code + Hermes Agent.

---

## What This Project Does

APEX Digital is an AI agent system that can:
- Analyze Google Ads campaigns and diagnose performance issues
- Research keywords and suggest match types + negatives
- Generate weekly/monthly client performance reports
- Run competitor analysis and counter-strategy planning
- Optimize campaigns across bids, budgets, quality scores, and ad copy

The agents work like a senior Google Ads director — data-driven, direct, and proactive.

---

## Architecture

### Phase 1 — Hermes Foundation (CURRENT — complete)
**Hermes Agent** (by Nous Research) is the core platform. It runs as a conversational AI in your terminal with:
- A custom **SOUL.md** persona (APEX Digital Senior Google Ads Director)
- 5 custom **Skills** (analysis, reporting, keywords, optimization, competitor intel)
- **Mock Google Ads data** (8 realistic campaigns across different industries)
- **Voice input** via OpenAI Whisper (microphone support)

### Phase 2 — Custom Layer (PLANNED — not started)
Once Phase 1 is understood well, replace/extend with:
- **CrewAI specialist agents**: Campaign Manager, Data Analyst, Keyword Researcher, Optimizer, Copywriter, Market Intelligence, Reporter
- **Web dashboard**: FastAPI + SQLite + WebSocket, visual KPI display
- **Real Google Ads API**: Live data instead of mock data
- **Messaging integration**: WhatsApp/Telegram via Hermes gateway

---

## File Structure

```
marketing agency agent/
├── README.md                    ← This file
├── CHANGELOG.md                 ← Session-by-session log of all changes
├── CLAUDE.md                    ← Instructions for Claude Code instances
│
├── soul/
│   └── SOUL.md                  ← APEX Digital persona (copy of ~/.hermes/SOUL.md)
│
├── skills/
│   ├── google-ads-analysis.md   ← Campaign health check skill
│   ├── performance-reporter.md  ← Report generation skill
│   ├── keyword-research.md      ← Keyword research + negatives skill
│   ├── campaign-optimizer.md    ← Optimization recommendations skill
│   └── competitor-analysis.md  ← Competitor intel + counter-strategy skill
│
├── data/
│   └── mock_campaigns.json      ← 8 realistic Google Ads campaigns (mock data)
│
└── config/
    └── hermes_config.yaml       ← Hermes configuration file
```

---

## Mock Data — What's Inside

The file `data/mock_campaigns.json` contains 8 campaigns across different industries:

| Campaign | Industry | Type | Monthly Budget |
|---|---|---|---|
| AlphaShop Brand | E-commerce | Search (Brand) | $5,000 |
| AlphaShop Non-Brand | E-commerce | Search | $12,000 |
| BetaSaaS Demo Requests | SaaS | Search | $8,000 |
| Gamma Dental Local | Dental | Search | $3,500 |
| Delta Law Group Leads | Legal | Search | $15,000 |
| EpsilonFit Shopping | Fitness | Shopping | $6,000 |
| Zeta Realty PMax | Real Estate | Performance Max | $10,000 |
| Eta Travel Display | Travel | Display Remarketing | $4,000 |

**Account totals (MTD):** $48,370 spend | $959,510 revenue | 1,983.8% blended ROAS

The file also includes:
- `keyword_opportunities` — 5 high-potential keywords to add
- `competitor_intel` — 3 competitors with impression share and ad copy patterns

---

## Setup Instructions (for the brother)

### Step 1 — Clone the repo
```bash
git clone https://github.com/adirgil1515bus/marketing-agency-agent.git
cd "marketing-agency-agent"
```

### Step 2 — Install Hermes Agent
```bash
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
```
This installs Python 3.11, uv, Node.js 22, Playwright, ripgrep, and Hermes itself.

### Step 3 — Run Hermes setup
```bash
hermes setup
```
When asked for a provider: choose **Anthropic**
When asked for credentials: choose **Use existing credentials** (Claude Code OAuth — no API key needed if you have Claude Code installed)

### Step 4 — Copy the SOUL.md persona
```bash
cp soul/SOUL.md ~/.hermes/SOUL.md
```
This gives Hermes the APEX Digital personality.

### Step 5 — Add OpenAI key for voice (optional)
If you want microphone input, add your OpenAI API key to `~/.hermes/.env`:
```
VOICE_TOOLS_OPENAI_KEY=sk-proj-YOUR_KEY_HERE
```

### Step 6 — Start the agent
```bash
hermes
```

---

## How to Use Hermes (Example Prompts)

Once `hermes` is running, try:

```
"Analyze the BetaSaaS campaign"
"Generate a weekly performance report for Delta Law Group"
"What keywords should I add to EpsilonFit?"
"Run a competitor analysis"
"Optimize the Gamma Dental campaign — reduce CPA"
```

---

## Hermes Config Location

All Hermes system files live at `~/.hermes/`:
- `~/.hermes/.env` — API keys and settings
- `~/.hermes/SOUL.md` — Agent personality
- `~/.hermes/config.yaml` — Model and provider settings (claude-sonnet-4-6)

---

## GitHub Repository

`https://github.com/adirgil1515bus/marketing-agency-agent`

Owner: Adir (adirgil1515bus)
Collaborators: brother (TBD)

---

## Current Status

**Phase 1: Complete**
- [x] Hermes installed and configured
- [x] APEX Digital persona written (SOUL.md)
- [x] 8-campaign mock dataset created
- [x] 5 custom skills built
- [x] Voice input enabled (OpenAI Whisper)
- [x] GitHub repo created and pushed

**Phase 2: Not started** — will begin once Phase 1 is well understood
