# Skill: Keyword Research

## Trigger Phrases
- "find keywords for"
- "keyword research"
- "what keywords should I add"
- "keyword opportunities"
- "expand keywords"
- "negative keywords"

## Behavior

Use data from:
`/Users/adirgil/sandbox/Claude sandbox/marketing agency agent/data/mock_campaigns.json`
(keyword_opportunities section + top_keywords per campaign)

### Research Framework

**1. Intent Classification**
Classify every keyword by search intent:
- 🛒 Transactional — user wants to buy/hire NOW ("buy running shoes", "hire lawyer")
- 🔍 Commercial Investigation — user is comparing options ("best crm software", "X vs Y")
- ℹ️ Informational — user wants to learn ("how to run google ads")
- 🏢 Navigational — user is looking for a specific brand

**2. Keyword Scoring**
Score each keyword on:
- Search Volume (monthly searches)
- Commercial Intent (1-10)
- Competition Level (Low/Medium/High)
- Estimated CPC
- Relevance to campaign (1-10)

**3. Match Type Recommendation**
- Exact [keyword] — for high-intent, proven converters
- Phrase "keyword" — for medium-intent with volume
- Broad keyword — for discovery only, with tight negatives

**4. Negative Keyword Mining**
Always suggest negatives alongside new keywords.

### Output Format

```
🔍 KEYWORD RESEARCH — [Campaign/Topic]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

NEW KEYWORD OPPORTUNITIES
┌─────────────────────────────┬─────────┬──────┬──────────┬──────┬───────────────┐
│ Keyword                     │ Volume  │ CPC  │ Comp.    │ Int. │ Match Type    │
├─────────────────────────────┼─────────┼──────┼──────────┼──────┼───────────────┤
│ [keyword]                   │ X,XXX   │ $X.XX│ High     │ 🛒   │ [exact]       │
└─────────────────────────────┴─────────┴──────┴──────────┴──────┴───────────────┘

RECOMMENDED NEGATIVES (add immediately)
- [negative keyword] — reason
- [negative keyword] — reason

PRIORITY ADDS (implement first)
1. [keyword] — why it will perform
```
