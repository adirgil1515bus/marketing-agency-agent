# Skill: Competitor Analysis

## Trigger Phrases
- "competitor analysis"
- "who are we competing against"
- "what are competitors doing"
- "auction insights"
- "competitor ad copy"
- "how do we compare to"

## Behavior

Load competitor data from:
`/Users/adirgil/sandbox/Claude sandbox/marketing agency agent/data/mock_campaigns.json`
(competitor_intel section)

### Analysis Framework

**1. Competitive Landscape**
- Who are the top competitors per client/campaign?
- What is their estimated impression share?
- Which keywords are they aggressively bidding on?

**2. Ad Copy Intelligence**
- What messaging patterns do competitors use?
- What offers/hooks are they leading with?
- What are they NOT doing that we could own?

**3. Strategic Gaps**
- Keywords competitors rank for that we don't bid on
- Ad copy angles we haven't tested
- Positioning opportunities (what we can own)

**4. Counter-Strategy**
- How to differentiate in ad copy
- Where to increase bids to beat them
- Where to avoid overpaying to compete

### Output Format

```
🕵️ COMPETITOR ANALYSIS — [Client/Campaign]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TOP COMPETITORS
┌─────────────────┬────────────────┬──────────────────────────────────────┐
│ Competitor      │ Imp. Share     │ Main Keywords Targeted               │
├─────────────────┼────────────────┼──────────────────────────────────────┤
│ [name]          │ XX%            │ [keyword1], [keyword2]               │
└─────────────────┴────────────────┴──────────────────────────────────────┘

THEIR AD COPY PATTERNS
• [Pattern 1 — e.g., "All lead with free trial offer"]
• [Pattern 2]
• [Pattern 3]

STRATEGIC OPPORTUNITIES (what they're missing)
1. [Gap/Opportunity] — how we exploit it
2. [Gap/Opportunity]

OUR COUNTER-STRATEGY
• Short-term: [Immediate tactical response]
• Long-term: [Positioning play]
```
