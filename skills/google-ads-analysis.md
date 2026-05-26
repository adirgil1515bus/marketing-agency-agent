# Skill: Google Ads Campaign Analysis

## Trigger Phrases
- "analyze [campaign name]"
- "how is [client] performing"
- "review campaign"
- "what's wrong with"
- "campaign health check"
- "analyze all campaigns"

## Behavior

When triggered, load and analyze data from:
`/Users/adirgil/sandbox/Claude sandbox/marketing agency agent/data/mock_campaigns.json`

### Analysis Framework

**Step 1 — KPI Health Check**
Score each campaign on:
- ROAS vs. target (green/yellow/red)
- CPA vs. target (green/yellow/red)
- CTR vs. industry benchmark
- Quality Score (if Search campaign)
- Impression Share and lost IS

**Step 2 — Identify Issues**
Flag any of these automatically:
- Budget-constrained (lost_is_budget > 15%)
- Low Quality Score (< 6)
- High CPA vs. target (> 110% of target)
- Low CTR (< 2% for Search, < 0.15% for Display)
- Low ROAS vs. target (< 80% of target)

**Step 3 — Prioritized Recommendations**
List actions by impact (high/medium/low) and effort (easy/medium/hard).

### Output Format

```
📊 CAMPAIGN ANALYSIS — [Campaign Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

PERFORMANCE SNAPSHOT
• Spend MTD: $X,XXX | Budget: $X,XXX
• ROAS: XXX% [TARGET: XXX%] ✅/⚠️/🔴
• CPA: $XX.XX [TARGET: $XX.XX] ✅/⚠️/🔴
• CTR: X.XX% | Avg CPC: $X.XX
• Impression Share: XX% (lost to budget: X%, rank: X%)

KEY FINDINGS
1. [Most important finding]
2. [Second finding]
3. [Third finding]

ACTION PLAN (Priority Order)
🔴 HIGH: [Action] — [Expected impact]
🟡 MEDIUM: [Action] — [Expected impact]
🟢 QUICK WIN: [Action] — [Expected impact]
```
