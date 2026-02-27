# Ahrefs Workflow for Demand Validation

Step-by-step Ahrefs MCP tool usage for quantifying search demand and competitive intelligence. When Ahrefs tools are not available, use the fallback approaches noted in each section.

---

## Phase 1: Keywords Explorer — Demand Quantification

### Step 1: Initial Keyword Overview

**Tool:** `keywords-explorer-overview`

```
Parameters:
- keywords: [your 5-10 seed keywords, comma-separated]
- select: keyword, volume, difficulty, cpc, traffic_potential, global_volume
- country: us (or target geography)
```

**What to look at first:**
- **Volume:** Monthly searches in target country. This is your demand ceiling.
- **CPC:** Cost-per-click. Any CPC > $0 means someone is paying to monetize this search, which validates commercial intent. CPC > $2 indicates significant commercial value.
- **Traffic Potential:** How much traffic the top-ranking page gets across all keyword variations. Often more useful than individual keyword volume.
- **Keyword Difficulty (KD):** How hard it is to rank in the top 10 organically. KD > 60 means you'll need paid or community channels.
- **Global Volume:** Total worldwide searches. Useful for assessing international opportunity.

**Quick interpretation framework:**

| Volume (monthly) | CPC | Reading |
|-------------------|-----|---------|
| > 5,000 | > $2 | Large validated market, strong commercial intent |
| 1,000-5,000 | > $2 | Solid market, good for focused product |
| 500-1,000 | > $0 | Niche market, viable with premium pricing |
| 100-500 | > $0 | Very niche, needs laser focus or broader keyword set |
| < 100 | $0 | Either no demand, or people don't search for this (need outbound) |
| Any | > $5 | High-value market, supports premium pricing ($99+/mo) |
| Any | $0 | No advertiser spends = unproven commercial model |

### Step 2: Expand with Matching Terms

**Tool:** `keywords-explorer-matching-terms`

```
Parameters:
- keyword: [primary seed keyword]
- select: keyword, volume, cpc, difficulty, traffic_potential
- country: us
```

**What to do with results:**
1. Filter for CPC > 0 to isolate commercially viable keywords
2. Sort by volume descending to see highest-demand variations
3. Look for keywords you didn't think of — these reveal how customers actually phrase the problem
4. Note long-tail variations with buying intent: "best [X] for [audience]", "[X] vs [Y]", "[X] pricing"
5. Group keywords into clusters: problem-aware, solution-aware, decision-stage

**Buying intent keyword patterns:**
- "best [category] for [audience]" — comparing, ready to choose
- "[product A] vs [product B]" — evaluating options
- "[product] pricing" or "[product] cost" — considering purchase
- "[product] review" or "[product] reddit" — seeking validation
- "[category] alternative" — switching intent
- "free [category]" — price-sensitive but demand exists
- "how to [specific task]" — problem-aware, early stage

### Step 3: Volume History and Trends

Check whether demand is growing, stable, or declining:
- Use the volume history data from keywords-explorer-overview when available
- Cross-reference with Google Trends for a longer time horizon
- Note seasonal patterns — some problems spike at specific times (tax season, Q4 planning, New Year)

**Trend interpretation:**
- Growing volume over 12+ months = expanding market, ride the wave
- Stable volume = mature market, need differentiation to win
- Declining volume = shrinking market, risky unless capturing remaining demand
- Sudden spike then decline = likely a news event, not sustainable demand

---

## Phase 2: Site Explorer — Competitor Intelligence

### Step 4: Competitor Metrics

**Tool:** `site-explorer-metrics`

```
Parameters:
- target: [competitor domain, e.g., competitor.com]
- select: domain_rating, organic_traffic, organic_keywords, paid_traffic, paid_keywords
```

Run this for each of your top 3-5 competitors.

**What the metrics tell you:**

| Metric | What It Means | Implication |
|--------|--------------|-------------|
| Domain Rating (DR) > 60 | Established, authoritative site | Hard to outrank organically, need other channels |
| DR < 30 | Smaller or newer player | Organically beatable with good content |
| Organic traffic > 10K/mo | Significant organic presence | Validated SEO opportunity in this space |
| Paid traffic > 0 | They're buying ads | Market has proven paid acquisition economics |
| Paid keywords > 0 | Specific terms worth paying for | These keywords have highest commercial value |
| Organic keywords > 1,000 | Broad keyword coverage | They've invested heavily in content |

### Step 5: Organic Competitors Map

**Tool:** `site-explorer-organic-competitors`

```
Parameters:
- target: [primary competitor domain]
- select: domain, organic_traffic, common_keywords, keywords_unique
```

This reveals the full competitive landscape — competitors you may not have found through manual search. It shows who ranks for similar keywords.

**What to look for:**
- Competitors with high common keywords but low DR = beatable
- Competitors with unique keywords = may serve a different segment
- Many competitors = validated market
- Competitors you didn't know about = market is more crowded than expected (or reveals adjacent opportunities)

### Step 6: Batch Competitor Comparison

**Tool:** `batch-analysis`

```
Parameters:
- targets: [comma-separated competitor domains]
- select: domain_rating, organic_traffic, paid_traffic, referring_domains
```

Creates a side-by-side comparison of all competitors on key metrics.

**Analysis questions:**
- Who's winning on organic traffic? Why? (Check their top pages)
- Who's spending on paid? What are they bidding on?
- What's the DR range? Where would your new site fall?
- Are competitors growing (rising traffic) or stagnating (flat/declining)?

---

## Phase 3: Interpreting Results

### The Demand Matrix

Combine keyword data and competitor data into a single assessment:

| | High Search Volume | Low Search Volume |
|---|---|---|
| **Many Competitors** | Validated market, need differentiation | Niche market, competitors found it through non-search channels |
| **Few Competitors** | Opportunity — demand exists but supply is thin | Either very early or no market — validate carefully |

### CPC as Price Signal

CPC data from Ahrefs directly correlates with what the market will bear:

| CPC Range | Market Price Signal | Typical Product Pricing |
|-----------|-------------------|----------------------|
| $0-$1 | Price-sensitive market | $9-29/mo or freemium with upsell |
| $1-$3 | Moderate commercial value | $29-79/mo |
| $3-$5 | Significant commercial value | $79-149/mo |
| $5-$10 | High-value market | $149-299/mo |
| $10+ | Enterprise or high-ticket | $299+/mo or per-transaction |

### Volume as Market Size Proxy

For indie products, search volume provides a rough bottom-up market sizing:

1. Total monthly volume across all relevant keywords = raw search demand
2. Multiply by 50x (searchers represent roughly 2% of people with the problem)
3. That's your rough total addressable audience
4. Multiply by realistic capture rate (1-3% for new entrant) and price = rough revenue potential

**Example:**
- 5,000 monthly searches across keyword cluster
- x 50 = ~250,000 people with this problem
- x 2% capture = 5,000 potential customers
- x $49/mo = ~$245K/mo revenue ceiling at scale
- Reality check: most indie products capture 0.1-0.5% of the addressable market in year 1

---

## Fallback: Without Ahrefs

When Ahrefs MCP tools are not available, use these alternative approaches:

### Google Search Analysis
- Search core keywords and count: how many ads show? (Ads = CPC > $0)
- Count organic results with commercial pages vs informational
- Check "People also ask" for related queries
- Note Google Shopping results (= product market exists)

### Google Trends
- Search core keywords on Google Trends for relative interest
- Compare multiple keywords to find which phrasing has more demand
- Check geographic distribution
- Look at related queries and rising queries

### Autocomplete Mining
- Type seed keywords into Google and note autocomplete suggestions
- These reflect real search behavior
- Pay attention to "vs", "alternative", "best", "pricing" suggestions

### Review Site Traffic
- Check if competitors have G2/Capterra pages with many reviews
- Many reviews = established market with active evaluation behavior
- Review count growth rate indicates market trajectory

### SimilarWeb (Free Tier)
- Check competitor traffic estimates
- Note traffic sources (organic, paid, referral, social)
- Compare top competitors on relative traffic
