# Market Analysis Frameworks — Complete Reference

This reference provides the full methodology behind the market sizing skill, including TAM/SAM/SOM analysis, Porter's Five Forces, competitive analysis dimensions, and data source quality hierarchy.

---

## TAM/SAM/SOM Methodology

### Total Addressable Market (TAM)

The total market demand for a product or service category, assuming 100% market share with no constraints.

**Calculation approaches:**

**1. Top-down (industry reports):**
- Find total industry revenue from analyst firms
- Apply relevant segment filters
- Sources: Statista, Grand View Research, Gartner, Forrester, IBISWorld
- Strength: authoritative numbers with methodology
- Weakness: often too broad, may not match your specific product category

**2. Bottom-up (unit economics):**
- Number of potential customers x average revenue per customer
- Start with the most specific population you can identify
- Example: 28M small businesses in the US x 15% that manage inventory x $49/mo = $2.5B TAM
- Strength: directly tied to your business model
- Weakness: requires accurate population and penetration estimates

**3. Value theory:**
- Total value currently spent solving this problem (all methods combined)
- Includes: software spend, manual labor costs, consultant fees, lost revenue from not solving
- Strength: captures the full opportunity including non-software alternatives
- Weakness: hardest to calculate accurately

**Validation checklist for TAM:**
- [ ] Is the number sourced from at least 2 independent estimates?
- [ ] Is the geography specified (global vs. US vs. specific markets)?
- [ ] Is the year of the estimate noted?
- [ ] Does the category actually match what you're building?
- [ ] If >$50B, have you narrowed enough?

### Serviceable Available Market (SAM)

The portion of TAM you can actually reach with your product, distribution, and business model.

**Narrowing dimensions:**
- **Geography:** Which markets can you serve? (Language, regulations, payments, time zones)
- **Customer segment:** Which subset of the TAM is your product actually built for?
- **Price tier:** If TAM includes enterprise at $10K/mo and you charge $49/mo, your SAM is the segment that buys at your tier
- **Feature scope:** If TAM is "all CRM" but you only do email tracking, your SAM is the email-tracking segment
- **Distribution reach:** Can you actually reach them? Online-only cuts out offline-only buyers.

**SAM/TAM ratio sanity check:**
- <10%: Very focused niche — make sure it's big enough in absolute terms
- 10-30%: Typical for a focused product in a large market
- 30-50%: Broad product or narrow TAM definition
- >50%: Your TAM definition is probably too narrow, or your SAM too generous

### Serviceable Obtainable Market (SOM)

What you can realistically capture in 1-3 years given current resources and competitive landscape.

**For indie/solo builders, calculate SOM in customers, not market share:**
- 100 customers at $49/mo = $4,900 MRR = $58,800 ARR — meaningful lifestyle revenue
- 500 customers at $49/mo = $24,500 MRR = $294,000 ARR — full-time income
- 1,000 customers at $49/mo = $49,000 MRR = $588,000 ARR — strong indie business

**SOM estimation methods:**
1. Competitor benchmarking: What do similar indie products achieve in years 1-3?
2. Channel capacity: How many customers can your planned distribution channels deliver?
3. Conversion funnel math: Traffic x CTR x conversion x close rate
4. Reference class: Search Indie Hackers for products at similar price points in similar categories

---

## Porter's Five Forces — Deep Dive

### Force 1: Threat of New Entrants

**Key questions:**
- Capital requirements to build an MVP?
- Technical complexity or proprietary technology needed?
- Network effects that protect incumbents?
- Brand loyalty or switching costs?
- Regulatory barriers (licenses, certifications)?
- Access to distribution channels?

**For software products, typical barriers are:**
- LOW: most SaaS can be replicated technically
- MODERATE: if data moat, integrations ecosystem, or brand trust required
- HIGH: if network effects, regulatory approval, or significant data advantage needed

### Force 2: Bargaining Power of Suppliers

**In software, suppliers are typically:**
- Cloud providers (AWS, GCP, Azure) — moderate power, switching possible
- API providers (Stripe, Twilio, OpenAI) — varies, some have lock-in
- Data providers — high power if exclusive data access
- App store platforms (Apple, Google) — high power, 15-30% revenue take

**Assess:** Could a supplier cut you off, raise prices 5x, or enter your market?

### Force 3: Bargaining Power of Buyers

**Key indicators:**
- Customer concentration — if one customer = 20%+ of revenue, they have leverage
- Price sensitivity — low CPC = price-sensitive market; high CPC = less price-sensitive
- Switching costs — monthly billing with data export = low switching cost; annual contract with deep integration = high
- Information availability — can they easily compare alternatives?

**For indie products:** Buyer power is typically HIGH because individual customers are small but have low switching costs and high information access.

### Force 4: Threat of Substitutes

**Substitute categories for software:**
- Manual process (spreadsheets, pen and paper)
- Hiring a person (VA, freelancer, employee)
- Adjacent software adding the feature (Notion adding X, Slack adding Y)
- Doing nothing (accepting the status quo)
- Free/open-source alternatives

**The most dangerous substitute is "good enough."** If a spreadsheet gets 80% of the job done for free, your product needs to deliver dramatically more value to justify paying.

### Force 5: Competitive Rivalry

**Rivalry indicators:**
- Number of direct competitors and their relative size
- Market growth rate (growing market = less zero-sum)
- Product differentiation (commoditized = higher rivalry)
- Exit barriers (high exit barriers = competitors stay even when losing)
- Innovation pace (fast-moving = more disruption opportunity)

**Competition is generally GOOD for indie builders:**
- Validates market demand
- Educates customers on the category
- Creates comparison-shopping behavior (people search "X alternatives")
- The key is finding differentiation, not avoiding competition

---

## Competitive Analysis Dimensions

For each competitor, systematically capture:

| Dimension | What to Find | Sources |
|---|---|---|
| Pricing | Model, tiers, free plan, trial | Pricing page, web fetch |
| Positioning | Who they target, how they describe themselves | Homepage, about page |
| Reviews | G2/Capterra scores, common praise, complaints | Review sites, web search |
| Traffic | Estimated monthly visits, traffic trend | SimilarWeb, Ahrefs |
| Keywords | What they rank for organically | Ahrefs, web search |
| Content | Blog topics, case studies, guides | Site review |
| Social proof | Customer logos, testimonials | Homepage, case studies |
| Gaps | What reviewers wish it could do | 4-star reviews, Reddit |

### The 4-Star Review Method

- 5-star reviews: Too positive, not specific, often fake
- 1-star reviews: Often rage-driven, edge cases
- **4-star reviews: Specific praise AND specific criticism. Gold mine.**

Look for patterns:
- "I love X but wish it could Y" = product gap = your opportunity
- "Great for [use case A] but not [use case B]" = underserved segment
- "Would be perfect if..." = feature roadmap from the market

### Competitor Classification

- **Direct:** Same solution, same problem, same market
- **Indirect:** Different solution, same problem (spreadsheets, consultants, manual processes)
- **Adjacent:** Similar solution, different market (enterprise version of what you do for SMB)
- **Emerging:** New technologies or business models that could disrupt the category

---

## Data Source Quality Hierarchy

Not all sources are equal. When data conflicts, defer to higher-quality sources.

**Tier 1 — Primary Sources (highest reliability):**
- Company financial reports (SEC filings, annual reports)
- Government data (Census, BLS, patent office)
- Original academic research with peer review

**Tier 2 — Reputable Analysts:**
- Gartner, Forrester, IDC, McKinsey
- Statista (aggregates from multiple primary sources)
- Grand View Research, MarketsandMarkets

**Tier 3 — Industry Publications:**
- Trade journals specific to the industry
- Specialized news outlets (TechCrunch for tech, etc.)
- Industry association reports

**Tier 4 — General Business Press:**
- Wall Street Journal, Bloomberg, Reuters
- Major tech press (The Information, Protocol)

**Tier 5 — Aggregators and Secondary Analysis:**
- Blog posts citing primary sources
- Comparison articles
- "Top 10" lists and buyer's guides

**Red flags for unreliable data:**
- No cited sources or methodology
- Promotional content disguised as research
- Outdated (>3 years for fast-moving tech markets)
- Suspiciously precise forecasts without explanation
- Contradicts multiple higher-tier sources

---

## Market Sizing for Indie Products — Practical Proxies

Traditional TAM/SAM/SOM is designed for VC pitch decks. For indie builders, these proxies provide more actionable signal:

### Search Volume Proxy
- Total monthly search volume across relevant keywords = rough market interest
- Multiply by estimated conversion rate = rough customer potential
- Multiply by expected price = rough revenue potential
- Best combined with CPC data (commercial intent signal)

### Competitor Revenue Proxy
- If competitors exist with public revenue (Indie Hackers, interviews, job postings)
- Multiple competitors each doing $1M+ ARR = healthy market
- No competitors with visible revenue = either very early or non-market
- Check: Indie Hackers profiles, "open startup" dashboards, interview mentions

### Community Size Proxy
- Relevant subreddits, Facebook groups, Slack communities, Discord servers
- 10,000+ people self-identifying with the problem = viable market
- 1,000-10,000 = niche, viable with premium pricing
- <1,000 = very niche or people don't self-identify as a community

### CPC Signal Proxy
- CPC = $0 across all terms: No commercial intent — people aren't paying to solve this
- CPC $0.50-$2: Low-moderate commercial value — supports $9-29/mo pricing
- CPC $2-$5: Significant value — supports $29-99/mo pricing
- CPC $5+: Premium market — supports $99-299/mo+ pricing

---

## Trend Analysis Methods

### Google Trends Interpretation
- **Rising (>50% YoY):** Growing demand, good market timing
- **Stable (flat over 2+ years):** Established category, competition likely entrenched
- **Declining:** Shrinking demand, avoid unless you have a differentiation thesis
- **Seasonal:** Plan launch timing and cash flow around cycles
- **Breakout:** New category forming, first-mover opportunity but also uncertainty

### Investment Pattern Signals
- VC funding flowing into the category = institutional validation of market
- Acquisitions happening = consolidation, potential for indie alternatives
- No funding = either too small for VC (fine for indie) or not validated (investigate)
