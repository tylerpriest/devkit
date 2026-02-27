# Market Calculator — Scoring Methodology and Financial Modeling

This reference translates market analysis scoring logic and financial modeling into structured methodologies that Claude applies during market sizing. Derived from quantitative analysis approaches used in startup validation tools.

---

## Market Attractiveness Scoring

### Scoring Dimensions

The market attractiveness score ranges from 0-100 and is calculated across four dimensions.

#### 1. Growth Rate Score (0-30 points)

| Annual Growth Rate (CAGR) | Points | Interpretation |
|---|---|---|
| >20% | 30 | Exceptional growth — strong market tailwinds |
| 15-20% | 25 | High growth — favorable dynamics |
| 10-15% | 20 | Solid growth — healthy expanding market |
| 5-10% | 15 | Moderate growth — stable but not accelerating |
| 0-5% | 10 | Low growth — mature or stagnating market |
| Negative | 5 | Declining — structural headwinds |

**Data sources for growth rate:** Industry analyst reports (Gartner, Forrester, Statista), market research firms, public company earnings calls mentioning category growth.

#### 2. Market Size Score (0-30 points)

| TAM Range | Points | Interpretation |
|---|---|---|
| >$10B | 30 | Large market — many subsegments, room for niche players |
| $1B-$10B | 20 | Mid-size — good opportunity, need positioning focus |
| $100M-$1B | 15 | Focused market — viable for indie, limited ceiling |
| $10M-$100M | 10 | Niche market — viable only at premium pricing |
| <$10M | 5 | Micro-niche — lifestyle business or reconsider |

**Note for indie builders:** A $100M TAM with 0.1% capture = $100K ARR, which is a meaningful indie business. Don't dismiss smaller markets.

#### 3. Competition Level Score (0-20 points)

| Competition Level | Points | How to Assess |
|---|---|---|
| Low — few competitors, clear gaps | 20 | <5 direct competitors, gaps visible in reviews |
| Medium — moderate competition, differentiation possible | 10 | 5-20 competitors, some have weak positioning or poor reviews |
| High — crowded, entrenched incumbents | 5 | 20+ competitors, market leaders well-funded with strong brands |

**Assessment method:**
1. Count direct competitors from web search ("[category] software", "[category] tools")
2. Check if top 3 have >$10M ARR or significant funding
3. Read reviews for gaps and complaints
4. Check keyword difficulty in Ahrefs (KD >60 = entrenched organic competition)

#### 4. Market Maturity Score (0-20 points)

| Maturity Stage | Points | Characteristics |
|---|---|---|
| Emerging | 20 | New category forming, no dominant player, rapid experimentation |
| Growing | 15 | Established category, expanding user base, new entrants succeeding |
| Mature | 10 | Stable category, consolidation happening, switching costs rising |
| Declining | 5 | Shrinking demand, exits exceeding entries, technology shift underway |

**Assessment method:**
1. Google Trends trajectory over 5 years
2. Number of new entrants in last 2 years (growing market has many)
3. M&A activity (high = consolidation = mature)
4. VC funding trend (growing funding = growing market)

### Overall Score Interpretation

| Score Range | Rating | Recommendation |
|---|---|---|
| 80-100 | Highly Attractive | Strong tailwinds. Focus on execution and positioning. |
| 60-79 | Attractive | Good opportunity. Need solid differentiation. |
| 40-59 | Moderately Attractive | Viable with strong niche focus or unique advantage. |
| 20-39 | Challenging | Requires exceptional positioning or reconsider market. |
| 0-19 | Unattractive | Strong headwinds. Recommend pivot to adjacent market. |

---

## Unit Economics Calculator

### Customer Acquisition Cost (CAC)

**Formula:** Total marketing and sales spend / number of customers acquired

**Channel-specific CAC estimates:**

| Channel | Typical CAC Range (B2B SaaS) | Notes |
|---|---|---|
| Organic/SEO | $50-200 | Low ongoing cost, slow to build |
| Content marketing | $100-300 | Requires consistent production |
| Google Ads | $100-500 | Correlates with CPC data from keyword research |
| Reddit/community | $20-100 | High effort but low cash cost |
| Referral | $0-50 | Requires existing happy customers |
| Product Hunt launch | $0-100 | One-time spike, high variability |

**CAC from ad spend formula:**
```
Monthly ad budget / (clicks x landing page conversion x trial-to-paid rate) = CAC
Example: $500 / (250 clicks x 5% conversion x 30% trial-to-paid) = $500 / 3.75 = $133 CAC
```

### Lifetime Value (LTV)

**Formula:** Average monthly revenue per customer x average customer lifespan in months

**Customer lifespan estimates by category:**

| Product Type | Typical Monthly Churn | Avg Lifespan (months) |
|---|---|---|
| B2B SaaS (SMB) | 3-7% | 14-33 |
| B2B SaaS (Mid-market) | 1-3% | 33-100 |
| Consumer SaaS | 5-10% | 10-20 |
| Dev tools | 3-5% | 20-33 |
| Productivity tools | 5-8% | 12-20 |

**LTV calculation:**
```
LTV = ARPU / monthly churn rate
Example: $49/mo / 5% churn = $980 LTV
```

### LTV:CAC Ratio

| Ratio | Health | Interpretation |
|---|---|---|
| >5:1 | Excellent | May be under-investing in growth |
| 3:1 to 5:1 | Healthy | Sustainable unit economics |
| 2:1 to 3:1 | Acceptable | Tight margins, optimize CAC or improve retention |
| 1:1 to 2:1 | Unhealthy | Losing money or barely breaking even per customer |
| <1:1 | Critical | Unsustainable — fix before scaling |

### Payback Period

**Formula:** CAC / monthly revenue per customer

| Payback Period | Health | Interpretation |
|---|---|---|
| <6 months | Excellent | Fast cash cycle, can reinvest quickly |
| 6-12 months | Good | Standard SaaS benchmark |
| 12-18 months | Acceptable | Needs strong retention to work |
| >18 months | Concerning | Significant cash flow risk for bootstrapped builders |

### Gross Margin

**Formula:** (Revenue - Cost of Goods Sold) / Revenue x 100

**COGS for SaaS typically includes:**
- Hosting/infrastructure costs
- Third-party API costs (per-call pricing)
- Payment processing fees (2.9% + $0.30 typical)
- Customer support costs (if outsourced)

| Margin Range | Health | Interpretation |
|---|---|---|
| >80% | Excellent | Strong SaaS margins, high leverage |
| 70-80% | Good | Typical healthy SaaS |
| 50-70% | Acceptable | May have high API or infrastructure costs |
| <50% | Low | Investigate cost structure, may not be viable at scale |

---

## Breakeven Analysis

### Fixed vs. Variable Cost Framework

**Monthly Fixed Costs (don't change with customer count):**
- Domain and hosting baseline: $20-100/mo
- SaaS tools (analytics, email, monitoring): $50-200/mo
- Payment processor monthly fee: $0-25/mo
- If full-time: personal living expenses as minimum revenue target

**Variable Costs (scale with customers):**
- Per-customer hosting/compute: $0.50-5/mo
- Per-customer API calls: varies by product
- Payment processing: ~3% of revenue
- Support time: 5-15 min/customer/month at early stage

### Breakeven Calculation

```
Breakeven customers = Monthly Fixed Costs / (ARPU - Variable Cost per Customer)

Example:
Fixed costs: $200/mo (hosting + tools)
ARPU: $49/mo
Variable cost per customer: $3/mo (hosting + payment processing)
Breakeven: $200 / ($49 - $3) = 4.3 → 5 customers

With living expenses ($4,000/mo target):
Breakeven: $4,200 / $46 = 91.3 → 92 customers for full-time income
```

### Scalability Assessment

**At 100 customers:**
- Revenue: 100 x ARPU/mo
- Can you handle support manually?
- Does infrastructure hold?
- Any billing or operational issues?

**At 1,000 customers:**
- Revenue: 1,000 x ARPU/mo
- Need automated onboarding?
- Need dedicated support?
- Infrastructure auto-scaling required?
- Team needed or still solo?

**At 10,000 customers (aspirational):**
- Revenue: 10,000 x ARPU/mo
- Full team required
- Enterprise-grade infrastructure
- Self-serve everything

**The marginal cost question:** What does it cost to serve one more customer? For pure software, this should approach near-zero. If it doesn't (heavy support, manual processes, per-seat API costs), that's a scalability constraint to flag.

---

## Financial Projection Templates

### Conservative / Moderate / Optimistic Scenarios

For each projection, model three scenarios:

| Scenario | Growth Assumption | Churn Assumption | Pricing Assumption |
|---|---|---|---|
| Conservative | 5 new customers/mo | 7% monthly churn | Base price only |
| Moderate | 15 new customers/mo | 5% monthly churn | Base price + 10% upsell |
| Optimistic | 30 new customers/mo | 3% monthly churn | Base price + 20% upsell |

### 12-Month Revenue Projection Formula

```
For each month:
  New customers = growth assumption
  Churned customers = existing customers x churn rate
  Net customers = previous customers + new - churned
  Revenue = net customers x ARPU

Report: Month 6 and Month 12 MRR for each scenario
```

### Key Thresholds for Indie Builders

| Milestone | MRR | Significance |
|---|---|---|
| Ramen profitable | $2,000-3,000 | Covers basic living expenses |
| Comfortable solo | $5,000-8,000 | Full-time sustainable income |
| Strong indie | $10,000-25,000 | Growing, can invest in product |
| Indie success | $25,000-50,000 | Premium indie business |
| Scale inflection | $50,000+ | Hiring and growth decisions |

---

## Viability Scoring Algorithm

An overall viability score that combines market attractiveness, unit economics, and competitive position.

### Dimension Weights

| Dimension | Weight | Max Points |
|---|---|---|
| Market opportunity (size + growth) | 30% | 30 |
| Competition position | 20% | 20 |
| Problem-solution fit | 25% | 25 |
| Business model viability (unit economics) | 25% | 25 |
| **Total** | **100%** | **100** |

### Scoring Criteria

**Market Opportunity (0-30):**
- Market size >$1B: +15
- Growth rate >10%: +15

**Competition Position (0-20):**
- Low competition: +20
- Medium competition: +10
- High competition: +5 (some points because competition validates market)

**Problem-Solution Fit (0-25):**
- Problem frequency daily/weekly: +10
- Problem intensity high/critical: +10
- Existing willingness to pay: +5

**Business Model (0-25):**
- LTV:CAC >= 3:1: +15
- Payback period <= 12 months: +10

### Recommendation Thresholds

| Score | Recommendation | Confidence |
|---|---|---|
| 70-100 | STRONG GO | High — pursue aggressively |
| 50-69 | PROCEED WITH VALIDATION | Medium — validate specific assumptions |
| 30-49 | PIVOT RECOMMENDED | Low — adjacent opportunity likely stronger |
| 0-29 | NOT VIABLE | High — fundamental challenges |
