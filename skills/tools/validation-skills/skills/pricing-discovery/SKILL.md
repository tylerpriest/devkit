---
name: pricing-discovery
description: "Determine a defensible starting price using competitor analysis, value metrics, and unit economics. Triggers: pricing strategy, what should I charge, how much to charge, pricing page, price point, monetization, revenue model, willingness to pay"
---

# Pricing Discovery

> Determine a defensible starting price by triangulating competitor data, cost-of-alternative calculations, CPC signals, and unit economics -- before you launch.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

Most indie founders underprice by 2-5x because they price based on what it cost to build, not the value delivered. This skill replaces guesswork with a structured pricing investigation that triangulates multiple data sources to find a defensible starting price, a value metric, and a pricing structure that captures value without leaving money on the table.

## Methodology

### Step 1: Competitor Price Scan

Build a competitor pricing matrix. For every competitor identified in positioning (Phase 4), capture:

1. **Fetch pricing pages** for each competitor (use web fetch)
2. For each competitor, document:
   - Pricing model (flat, per-user, usage-based, tiered)
   - Tier names, prices, and what's included at each tier
   - Value metric (what they charge per -- seats, projects, API calls, flat)
   - Free tier existence and limits
   - Trial length and credit card requirements
   - Feature gates between tiers (reveals what customers value most)
3. Check Wayback Machine (`web.archive.org`) for pricing history -- prices only go up
4. Check G2/Capterra reviews for pricing sentiment ("expensive", "great value", "overpriced")

**Identify from the matrix:**
- **Price floor**: Cheapest competitor's entry price (market minimum expectation)
- **Price ceiling**: Most expensive competitor (maximum the market has tolerated)
- **Cluster price**: Where most competitors converge (market default)
- **Dominant value metric**: What most competitors charge per

**Output a table:**

```
| Competitor | Entry Price | Mid Tier | Top Tier | Value Metric | Free Tier | Trial |
|------------|-------------|----------|----------|--------------|-----------|-------|
| [Name]     | $X/mo       | $Y/mo    | $Z/mo    | per user     | Yes/No    | 14d   |
```

### Step 2: Cost-of-Alternative Calculation

Calculate what the problem costs WITHOUT a solution:

```
Time spent per week on manual approach: ___ hours
Hourly rate of person doing it: $___/hr
Monthly workaround cost = hours x rate x 4 = $___/mo
```

**Apply the 10x Rule:** Your price should be at most 1/10th the value delivered. If the workaround costs $800/mo, charge around $80/mo. This makes ROI obvious and the purchase decision automatic.

**Frame the value narrative:**
- "Save [X hours/month] for less than [$Y/hour]"
- "Replace your $[workaround cost]/month process for $[your price]/month"
- "Pay for itself in [timeframe]"

### Step 3: CPC-Based Price Signal

If search demand data is available from Phase 2, use CPC as a proxy for what the market will bear:

| CPC Range | Market Signal | Sustainable Price Range |
|-----------|--------------|------------------------|
| < $1 | Price-sensitive market | $9-29/mo, consider freemium |
| $1-3 | Moderate commercial value | $19-49/mo |
| $3-5 | Good commercial value | $49-99/mo |
| $5-10 | High commercial value | $99-199/mo |
| $10+ | Premium/enterprise market | $200+/mo |

**Why CPC correlates with pricing:** Advertisers calculate maximum CPC from customer lifetime value. High CPC = advertisers know customers in this market spend significant money on solutions.

If Ahrefs MCP is available, check paid keyword data for competitors to see what they're bidding on and their estimated traffic value.

### Step 4: Review Mining for Price Sensitivity

Search competitor reviews on G2, Capterra, and TrustPilot for pricing signals:

**Search terms:**
- "[Competitor] expensive" or "[Competitor] overpriced"
- "[Competitor] great value" or "[Competitor] worth every penny"
- "[Competitor] pricing" site:reddit.com
- "switched from [Competitor] because of pricing"
- "wish there was a cheaper [category]"

**Extract:**
- Where the market's price sensitivity threshold sits
- Which features justify premium pricing in customers' minds
- What customers consider "must have" vs "nice to have" (informs tier design)
- Any mentions of specific price points ("$X/mo is too much for what it does")

### Step 5: Search-to-Revenue Chain (Unit Economics)

Model the revenue potential using available search data:

```
Monthly Search Volume (from Phase 2):  ___
  x Estimated CTR (organic ~3%, paid ~5%):  ___
  = Monthly Visitors:                       ___
  x Landing Page Conversion Rate (2-5%):    ___
  = Monthly Signups:                        ___
  x Trial-to-Paid Rate (15-30%):            ___
  = Monthly New Customers:                  ___
  x Average Revenue Per User (ARPU):        $___
  = Monthly Revenue:                        $___
```

**LTV:CAC Analysis:**
- **Customer Acquisition Cost (CAC)**: CPC / conversion rate = cost to acquire one customer
- **Lifetime Value (LTV)**: ARPU x average customer lifespan in months
- **LTV:CAC ratio**: Must be 3:1 or higher for healthy unit economics
- **Payback period**: CAC / monthly revenue per customer (target < 12 months)
- **Gross margin**: (Revenue - infrastructure costs) / Revenue (target > 70% for SaaS)

If the LTV:CAC ratio is below 3:1, either raise price, lower acquisition cost, or improve retention before scaling.

### Step 6: Breakeven Analysis

Estimate when revenue covers costs:

**Fixed costs** (monthly):
- Hosting/infrastructure: $___
- Domain, email, tools: $___
- Your time (opportunity cost): $___

**Variable costs** (per customer):
- Support time: $___
- Infrastructure per user: $___

**Breakeven calculation:**
```
Breakeven customers = Fixed costs / (ARPU - Variable cost per customer)
```

**Stress-test scenarios:**
- **Optimistic**: Hit breakeven in X months at Y% conversion
- **Realistic**: Hit breakeven in X months at Y% conversion
- **Pessimistic**: Hit breakeven in X months at Y% conversion (or never)

If breakeven requires more than 200 customers at your planned price, consider whether the price is too low or costs are too high.

### Step 7: Pricing Structure Decision

Based on all signals above, recommend:

**1. Value metric** -- what to charge per:
- **Flat rate**: Best for solo tools, simple utilities, early-stage validation. Removes decision friction.
- **Per-seat**: Best for collaboration tools where more users = more value.
- **Per-project/workspace**: Best when value scales with usage, not team size.
- **Usage-based**: Best for APIs, infrastructure, developer tools.

For itch products starting out: default to flat rate or simple per-seat. Complexity kills conversion.

**2. Number of tiers** -- keep it simple at launch:
- **One tier**: "$X/month. Free 14-day trial. No credit card required." Zero decision paralysis.
- **Two tiers**: Free/limited + Paid. Best for product-led growth.
- Save three-tier pricing for after you have 50+ customers and understand feature value.

**3. Monthly vs Annual:**
- Offer both from day one
- Annual discount: 15-20% (frame as "2 months free")
- During validation, default to monthly (lower commitment = faster signal)

**4. Pricing presentation:**
- Price must be visible on the page (hiding price kills trust for indie products)
- Use charm pricing ($49 not $50, $99 not $100)
- Frame monthly: "$49/month" feels smaller than "$588/year"
- Pilot framing: "Early access: $X/month (regular $Y)" creates urgency + value

### Step 8: Price Sensitivity Testing Plan

Design a simple experiment to validate the chosen price:

**A/B test approach:**
- Version A: Landing page at lower price (e.g., $29/mo)
- Version B: Landing page at higher price (e.g., $49/mo)
- Drive equal cold traffic to both
- Measure: signup rate x price = expected revenue per visitor
- Often the higher price performs BETTER on revenue

**Anchoring test:**
- Test different presentations of the same price:
  - "$49/month" vs "$1.63/day"
  - "$49/month" vs "Save 20 hours/month for less than $2.50/hour"
  - "$49/month" vs "$588/year (save $100)"

If smoke test conversion does not drop significantly at a higher price, you are underpricing.

## Output

Deliver a **Pricing Strategy Brief** with:

```markdown
## Pricing Strategy Brief: [Product Name]

### Recommended Starting Price
- **Price**: $X/month
- **Structure**: [Flat / Per-seat / etc.]
- **Value metric**: [What they pay per]
- **Trial**: [14-day free / Freemium / etc.]

### Justification
- Competitor range: $[floor] - $[ceiling], cluster at $[median]
- Workaround cost: $[X]/month. Our price = [Y]% of value delivered.
- CPC signal: $[X] CPC supports $[Y]/month pricing
- Review sentiment: [Summary of price sensitivity from reviews]

### Competitor Price Matrix
| Competitor | Entry | Mid | Top | Value Metric | Free Tier |
|------------|-------|-----|-----|--------------|-----------|
| ...        | ...   | ... | ... | ...          | ...       |

### Unit Economics
- **CAC**: $[X] (based on $[CPC] CPC and [Y]% conversion)
- **LTV**: $[X] (based on $[ARPU]/mo and [Y]-month average lifespan)
- **LTV:CAC Ratio**: [X]:1 ([Healthy/Acceptable/Unhealthy])
- **Payback Period**: [X] months
- **Gross Margin**: [X]%

### Breakeven Analysis
- **Monthly fixed costs**: $[X]
- **Breakeven customers**: [X] at $[price]/month
- **Estimated time to breakeven**: [X] months at [Y] customers/month

### Revenue Model
Monthly search volume [X] -> [Y] visitors -> [Z] signups -> [W] customers = $[R]/month

### Pricing Psychology Notes
- [Anchoring/framing recommendations]
- [Tier structure rationale]
- [Annual discount strategy]

### Price Testing Plan
- Test $[A] vs $[B] with equal cold traffic
- Success metric: revenue per visitor, not just conversion rate
- Run for [X] days with [Y] sessions per variant
```

## Tools

### Required
- Web search, web fetch (for competitor pricing pages, review mining)

### Optional (Enhanced Results)
- **Ahrefs MCP**: Use `keywords-explorer-overview` for CPC data and `site-explorer-metrics` for competitor paid keyword analysis. Without Ahrefs, rely on web search for "CPC [keyword]" and Google Ads Keyword Planner (free).

## Related Skills

- **Previous:** [positioning](/skills/positioning) -- Positioning defines who you serve and what value you deliver; pricing quantifies that value
- **Next:** [smoke-test](/skills/smoke-test) -- Test your price with real cold traffic before committing
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) -- Founders underprice due to impostor syndrome and cost-of-build anchoring; run bias audit on pricing decisions

## Reference Files

Read these for detailed methodology:
- `references/pricing-models.md` -- Pricing model types, psychology, and common mistakes
- `references/pricing-experiments.md` -- Van Westendorp method and experiment designs
