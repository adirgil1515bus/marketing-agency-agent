# Skill: Campaign Optimizer

## Trigger Phrases
- "optimize [campaign]"
- "improve performance"
- "reduce CPA"
- "increase ROAS"
- "fix [campaign]"
- "what should I change"
- "optimization recommendations"

## Behavior

Load data from:
`/Users/adirgil/sandbox/Claude sandbox/marketing agency agent/data/mock_campaigns.json`

Run a systematic optimization review across the requested campaigns.

### Optimization Checklist

**Bid Optimization**
- [ ] Are bids aligned with conversion value by keyword?
- [ ] Is the bidding strategy appropriate for the campaign goal?
- [ ] Is Target CPA/ROAS set correctly based on historical data?
- [ ] Are bid adjustments set for device, location, and time of day?

**Budget Optimization**
- [ ] Is the campaign budget-constrained (lost IS > 15%)?
- [ ] Is budget allocated to best-performing campaigns?
- [ ] Are any campaigns overspending with poor ROAS?

**Quality Score Optimization**
- [ ] Are ads highly relevant to their keywords?
- [ ] Is the landing page experience strong?
- [ ] Is expected CTR above average?

**Keyword Optimization**
- [ ] Are there search terms converting that aren't keywords yet?
- [ ] Are there wasted spend search terms to add as negatives?
- [ ] Are match types too broad causing irrelevant traffic?

**Ad Copy Optimization**
- [ ] Are all RSA ad slots filled (15 headlines, 4 descriptions)?
- [ ] Do ads include the primary keyword in headline 1?
- [ ] Are CTAs strong and specific?
- [ ] Are all relevant ad extensions active?

### Output Format

```
⚙️ OPTIMIZATION REPORT — [Campaign Name]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

CURRENT STATUS
[Brief diagnosis of what's working and what isn't]

OPTIMIZATION ACTIONS

🔴 DO NOW (biggest impact)
1. [Specific action with exact numbers/changes]
   Expected result: [measurable outcome]

🟡 DO THIS WEEK
2. [Action]
   Expected result: [outcome]

🟢 TEST NEXT MONTH
3. [Action]
   Expected result: [outcome]

ESTIMATED IMPACT
If all changes implemented:
• CPA: $XX.XX → $XX.XX (↓ X%)
• ROAS: XXX% → XXX% (↑ X%)
```
