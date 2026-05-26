# Skill: Performance Report Generator

## Trigger Phrases
- "generate report"
- "weekly report"
- "monthly report"
- "performance summary"
- "report for [client]"
- "how did we do this month"

## Behavior

Load data from:
`/Users/adirgil/sandbox/Claude sandbox/marketing agency agent/data/mock_campaigns.json`

Generate a structured report based on the requested period and client.

### Report Structure

**Executive Summary** (3 bullet points max — what the client needs to know)

**Account-Level KPIs**
- Total spend vs. budget
- Total revenue / conversions
- Blended ROAS
- MoM or WoW trend (use estimated delta if no historical data)

**Campaign Breakdown Table**
| Campaign | Spend | ROAS | CPA | Conversions | Status |
|---|---|---|---|---|---|

**Top Wins This Period**
- Best performing campaign
- Best performing keyword
- Biggest improvement

**Areas of Concern**
- Campaigns underperforming vs. target
- Budget waste identified
- Quality issues

**Next Period Action Plan**
- Top 3 priorities for next week/month
- Budget reallocation recommendations
- New tests to run

### Output Format

Professional, client-ready format. Use clear headers. Include numbers with context (not just raw data — explain what it means).
