---
name: market-sizing
description: "Quantitative market analysis with TAM/SAM/SOM, Porter's Five Forces, unit economics, and market attractiveness scoring. Triggers: how big is the market, market size, TAM SAM SOM, market opportunity, revenue potential, market analysis, unit economics, is this market big enough, market attractiveness, Porter's Five Forces"
---

# Market Sizing

> Produce a quantitative market report with TAM/SAM/SOM estimates, competitive force analysis, unit economics projections, and a scored market attractiveness assessment.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

Market sizing replaces gut-feel statements like "the market is huge" with defensible, sourced numbers. This skill combines multiple methodologies -- top-down TAM/SAM/SOM, bottom-up search-volume-to-revenue chains, Porter's Five Forces, and unit economics modeling -- to produce a quantified market report. The output feeds directly into go-no-go decisions and pricing strategy.

For indie and solo products, traditional VC-style TAM is mostly theater. This skill supplements it with bottom-up proxies (search volume, competitor revenue, community size) that are more actionable at the solo builder scale.

## Methodology

### Step 1: Top-Down TAM/SAM/SOM Estimation

Use web search to find industry-level market data.

**TAM (Total Addressable Market):**
- Total market demand for the product/service category
- Search for: "[industry] market size [current year]", "[category] market forecast", "global [product type] market analysis"
- Prioritize sources: Statista, Grand View Research, Gartner, Forrester, IBISWorld, MarketsandMarkets
- Cross-validate across at least 3 sources; note where estimates diverge

**SAM (Serviceable Available Market):**
- Segment of TAM you can actually target with your product and distribution
- Narrow by: geography, customer segment, price tier, feature set
- Example: TAM is "global project management software" ($10B) but SAM is "project management for freelance designers in North America" ($200M)

**SOM (Serviceable Obtainable Market):**
- Portion of SAM you can realistically capture in 1-3 years
- Based on: current resources, distribution capability, competitive position
- Typical SOM is 1-5% of SAM for a new entrant
- For solo/indie: calculate at specific customer counts rather than market share percentages

**Output format:**
```
TAM: $[X] — [source and year]
SAM: $[X] — [narrowing criteria]
SOM: $[X] — [capture assumptions]
SAM/TAM ratio: [X]% — [sanity check: <30% is typical, >50% needs justification]
```

### Step 2: Bottom-Up Market Estimation

Build a revenue estimate from search volume data upward. This is more actionable than top-down for solo builders.

**The Search-Volume-to-Revenue Chain:**

```
Search Volume (monthly) → from Ahrefs or web search estimates
    × CTR to your site → 2-5% for ads, 10-30% for top organic
    = Estimated Visitors
    × Conversion Rate → 2-5% for email, 1-3% for trial, 0.5-2% for direct purchase
    = Estimated Customers
    × ARPU (Average Revenue Per User) → from pricing research
    = Estimated Monthly Revenue
    × 12
    = Estimated Annual Revenue (bottom-up TAM proxy)
```

**Example calculation:**
- "inventory management small business" — 2,400 searches/mo
- Related terms cluster — 8,000 total monthly searches
- 3% ad CTR = 240 visitors/mo
- 3% visitor-to-trial = 7 trials/mo
- 30% trial-to-paid = 2 customers/mo
- $49/mo ARPU = $98 MRR from this channel alone
- Scale across channels: organic, referral, community = 5-10x multiplier

**Additional bottom-up proxies:**

| Proxy Method | Data Source | Formula |
|---|---|---|
| Search volume proxy | Ahrefs, Google Keyword Planner | Total monthly volume x conversion rate x price = revenue ceiling |
| Competitor revenue proxy | Indie Hackers, job postings, interviews | Multiple competitors at $1M+ ARR = healthy market |
| Community size proxy | Subreddit subscribers, Slack members | 10,000+ self-identifying = viable; <1,000 = premium niche |

### Step 3: Porter's Five Forces Analysis

Assess the structural attractiveness of the market.

**1. Threat of New Entrants**
- What are the barriers to entry? (Capital, technology, network effects, brand, regulatory)
- How easy is it for someone else to build the same thing?
- For software: barriers are typically low unless there's a data moat or network effect
- Score: HIGH / MEDIUM / LOW threat

**2. Bargaining Power of Suppliers**
- Who are your suppliers? (Cloud providers, API services, data sources, payment processors)
- Can they raise prices or cut you off?
- How concentrated are they? (AWS/GCP/Azure = oligopoly, but switching is possible)
- Score: HIGH / MEDIUM / LOW power

**3. Bargaining Power of Buyers**
- How concentrated is your customer base?
- How price-sensitive are they? (CPC data from Ahrefs is a proxy)
- What are their switching costs?
- Score: HIGH / MEDIUM / LOW power

**4. Threat of Substitutes**
- What alternatives exist outside your direct category?
- Spreadsheets, manual processes, hiring a person, doing nothing
- How good are the substitutes? What's the switching cost?
- Score: HIGH / MEDIUM / LOW threat

**5. Competitive Rivalry**
- How many direct competitors exist? What are their sizes?
- Is the market growing (rivalry softened) or stagnant (zero-sum)?
- How differentiated are offerings?
- Score: HIGH / MEDIUM / LOW rivalry

**Overall market attractiveness based on Five Forces:** ATTRACTIVE / NEUTRAL / UNATTRACTIVE

### Step 4: Market Attractiveness Scoring

Score the market on a 0-100 scale across four dimensions:

**Growth Rate (0-30 points):**
- >20% CAGR = 30 points
- 10-20% CAGR = 20 points
- 5-10% CAGR = 15 points
- <5% CAGR = 5 points

**Market Size (0-30 points):**
- TAM >$10B = 30 points
- TAM $1B-$10B = 20 points
- TAM $100M-$1B = 15 points
- TAM <$100M = 10 points

**Competition Level (0-20 points):**
- Low competition, clear gaps = 20 points
- Medium competition, differentiation possible = 10 points
- High competition, entrenched incumbents = 5 points

**Market Maturity (0-20 points):**
- Emerging (new category forming) = 20 points
- Growing (established but expanding) = 15 points
- Mature (stable, consolidating) = 5 points

**Total Score Interpretation:**
- 70-100: Highly attractive market — strong tailwinds
- 50-69: Moderately attractive — viable with good execution
- 30-49: Challenging market — needs strong differentiation or niche focus
- 0-29: Unattractive — reconsider market selection

### Step 5: Unit Economics Projection

Model the financial viability at the individual customer level.

**Core Metrics:**

| Metric | Formula | Healthy Benchmark |
|---|---|---|
| Customer Acquisition Cost (CAC) | Total marketing spend / customers acquired | Varies by model |
| Lifetime Value (LTV) | ARPU x average customer lifespan (months) | LTV > 3x CAC |
| LTV:CAC Ratio | LTV / CAC | 3:1 minimum, 5:1+ strong |
| Payback Period | CAC / monthly revenue per customer | <12 months |
| Gross Margin | (Revenue - COGS) / Revenue | >70% for SaaS |

**Expense Categories (for breakeven analysis):**
- Infrastructure: hosting, APIs, third-party services
- Marketing: paid ads, content, tools
- Operations: support, payment processing, legal
- Development: if hiring, contractor costs

**Breakeven Calculation:**
```
Monthly Fixed Costs / (ARPU - Variable Cost per Customer) = Customers needed to break even
```

**Scalability Check:**
- At 100 customers: What breaks? (manual support, infrastructure, billing)
- At 1,000 customers: What breaks? (team needs, architecture, operations)
- What's the marginal cost of the next customer? (Should approach zero for software)

### Step 6: Market Signals Assessment

**Green Flags:**
- Multiple funded competitors = validated market, room for alternatives
- Growing search volume = expanding demand
- New regulations/changes creating the problem = emerging market
- Competitors charging high prices with bad reviews = ripe for disruption
- CPC > $2 = significant commercial intent
- Community size > 10,000 self-identifying with the problem

**Red Flags:**
- "Everyone needs this" = haven't identified actual customer
- Zero competitors = usually no market, not blue ocean
- Only enterprise competitors = may be hard to reach SMB at indie scale
- Market declining year over year in Google Trends
- CPC = $0 across all terms = no commercial intent
- Community < 1,000 = very niche, requires premium pricing

**Verdict Categories:**
- LARGE & GROWING: Market supports multiple players, strong tailwinds
- NICHE BUT VIABLE: Small but profitable with premium pricing and focus
- CROWDED BUT DIFFERENTIATION POSSIBLE: Needs clear positioning
- INSUFFICIENT EVIDENCE: Need more data before committing
- TOO SMALL OR DECLINING: Reconsider market or pivot

## Output

### Quantitative Market Report

```markdown
## Market Sizing Report — [Product Name]

### TAM/SAM/SOM
- TAM: $[X] — [source]
- SAM: $[X] — [narrowing criteria]
- SOM: $[X] — [capture assumptions]

### Bottom-Up Revenue Estimate
[Search-volume-to-revenue chain with numbers]
Conservative: $[X]/mo | Moderate: $[X]/mo | Optimistic: $[X]/mo

### Porter's Five Forces
| Force | Rating | Key Factor |
|---|---|---|
| New Entrants | [H/M/L] | [one-liner] |
| Supplier Power | [H/M/L] | [one-liner] |
| Buyer Power | [H/M/L] | [one-liner] |
| Substitutes | [H/M/L] | [one-liner] |
| Rivalry | [H/M/L] | [one-liner] |
**Overall:** [ATTRACTIVE / NEUTRAL / UNATTRACTIVE]

### Market Attractiveness Score: [X]/100
- Growth: [X]/30
- Size: [X]/30
- Competition: [X]/20
- Maturity: [X]/20

### Unit Economics
- CAC: $[X] (estimated)
- LTV: $[X] (at [X] month average lifespan)
- LTV:CAC: [X]:1
- Breakeven: [X] customers at $[X]/mo
- Gross margin: [X]%

### Market Signals
**Green flags:** [list]
**Red flags:** [list]

### Verdict: [CATEGORY]
[2-3 sentence summary with recommendation]
```

Log findings to `validation-context.md` under `## Market Sizing`.

## Tools

### Required
- Web search (industry reports, market data, competitor pricing)
- Web fetch (full articles from Statista, Gartner, industry reports)

### Optional (Enhanced Results)
- **Ahrefs MCP** — Search volume data, CPC, keyword difficulty, competitor traffic
  - `keywords-explorer-overview` — seed keyword volume and CPC
  - `keywords-explorer-matching-terms` — related keyword cluster sizing
  - `site-explorer-metrics` — competitor domain traffic estimates
  - Fallback: Use web search for Google Keyword Planner estimates and SimilarWeb data
- **Google Trends** (via web fetch) — Trend direction over time

## Related Skills

- **Previous:** [demand-discovery](/skills/demand-discovery) — Provides search volume and competitor data that feeds market sizing
- **Next:** [pricing-discovery](/skills/pricing-discovery) — Uses unit economics and competitor data from this analysis
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit to check if projections are inflated by optimism bias
- **Feeds into:** [go-no-go](/skills/go-no-go) — Market sizing is a major input to the final decision
