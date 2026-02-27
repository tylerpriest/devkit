---
name: demand-discovery
description: "Quantify market demand using search data, competitive intelligence, and community signals. Triggers: check demand, market research, is there a market, search volume, competitive landscape, how big is the market, demand signals, keyword research"
---

# Demand Discovery

> Quantifies whether real demand exists by triangulating search data, competitive intelligence, community signals, and trend direction into a scored Demand Scorecard.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

Feelings about market demand are unreliable. This skill replaces gut instinct with data from multiple independent sources: keyword search volume and commercial intent (Ahrefs), competitor landscape analysis, community signal mining, and trend trajectory. The output is a 5-dimension Demand Scorecard rated 1-5 per dimension with specific evidence backing each score.

## Methodology

### Step 1: Seed Keyword Generation

The most critical mistake in demand research: using YOUR language instead of THEIRS.

**Translation exercise:**
1. Take the problem statement from `validation-context.md`
2. Strip all technical terms, acronyms, jargon
3. Rewrite as a complaint or question a frustrated person would Google
4. Test: would a non-technical friend phrase it this way?

**Generate keywords across 5 categories:**

| Category | Pattern | Example |
|----------|---------|---------|
| Problem keywords | "how to fix [problem]", "[problem] solution" | "how to stop inventory stockouts" |
| Alternative keywords | "[competitor] alternative", "better than [tool]" | "Procore alternative small business" |
| Job-to-be-done keywords | "best way to [task]", "how to [outcome]" | "best way to track project costs" |
| Frustration keywords | "[approach] problems", "why does [thing] suck" | "spreadsheet inventory tracking problems" |
| Buying keywords | "best [category] for [audience]", "[category] pricing" | "best inventory software small retail" |

Aim for 10-15 seed keywords across all categories.

**Keyword generation from previous skills:**
If problem-extraction has been completed, pull customer language from the Language Translation Table. The "Their words" column contains ready-made seed keywords that reflect how customers actually search.

**Common keyword generation mistakes:**
- Using product name as keyword (nobody searches for your product yet)
- Using only technical terms (customers search in plain language)
- Searching only for solution keywords (problem keywords often have higher volume)
- Ignoring misspellings and colloquial variations (real people don't write perfectly)
- Using only English if target market includes non-English speakers

### Step 2: Search Demand Analysis

Use Ahrefs tools if available. If not, fall back to web search for Google Trends data and autocomplete analysis.

**With Ahrefs MCP tools:**

1. **Run `keywords-explorer-overview`** with your seed keywords
   - Select: keyword, volume, difficulty, cpc, traffic_potential, global_volume
   - Country: start with target geography from context, or `us` as default
   - Review: volume, CPC, keyword difficulty, traffic potential

2. **Run `keywords-explorer-matching-terms`** for expanded keyword universe
   - Filter: CPC > 0 (shows commercial intent)
   - Sort: volume descending
   - Look for: patterns in how people phrase the problem, unexpected keywords

3. **Check volume history** for trend direction
   - Growing = ride the wave
   - Declining = risky unless capturing remaining demand
   - Seasonal = note the pattern, time your launch

**Interpret the data:**

| Signal | Reading | Implication |
|--------|---------|-------------|
| Volume > 1,000/mo + CPC > $2 | Strong validated demand | Proven market with commercial intent |
| Volume 100-1,000/mo + CPC > $0 | Niche but viable | Premium pricing opportunity |
| Volume < 50/mo | Very niche or non-search behavior | Need outbound/community strategy, not SEO |
| CPC > $5 | High commercial value | Market supports premium pricing |
| CPC = $0 across all terms | No commercial intent | People search but nobody monetizes (yet) |
| KD > 60 | Hard to rank organically | Need paid/community channels |
| Long-tail buying variants | Active evaluation | People comparing and deciding |
| Google Ads showing in SERPs | Advertisers paying | Market validated by spending |

**Without Ahrefs — fallback approach:**
- Search Google for core keywords, note ads and competitor count
- Check Google Trends for relative interest over time
- Use Google autocomplete suggestions as proxy for search behavior
- Look for "People also ask" boxes — these reflect real queries

> For detailed Ahrefs workflow steps, read `references/ahrefs-workflow.md`

### Step 3: Competitor Intelligence

Map the competitive landscape to understand who already serves this market and where gaps exist.

**Finding competitors:**
- Google search results for seed keywords (top 10 organic + ads)
- G2, Capterra, Product Hunt categories
- "Alternative to [known tool]" searches
- Reddit recommendation threads

**For each competitor, capture:**

| Dimension | What to Find | Where to Look |
|-----------|-------------|---------------|
| Pricing | Model, tiers, free plan | Pricing page, web fetch |
| Positioning | Who they say they're for | Homepage H1, about page |
| Traffic | Estimated monthly visits | Ahrefs site-explorer-metrics or SimilarWeb |
| Keywords | What they rank for | Ahrefs organic keywords |
| Reviews | Score, praise, complaints | G2, Capterra, App Store |
| Gaps | What reviewers wish it did | 4-star reviews, Reddit complaints |

**With Ahrefs MCP tools:**
- Run `site-explorer-metrics` on top 3-5 competitor domains (DR, traffic, keyword count)
- Run `site-explorer-organic-competitors` to map the full landscape
- Run `batch-analysis` to compare competitors side by side

**What competition tells you:**

| Situation | Signal | Your Advantage |
|-----------|--------|---------------|
| Funded competitors exist | Market validated | Speed, niche focus, simplicity, price |
| Many small competitors | Fragmented market | Consolidate or differentiate sharply |
| One dominant player | Defensible position | Find the segment they ignore |
| Only free/open-source | Hard to monetize | Must add significant value beyond free |
| Nobody at all | Either very early or no market | Validate extra carefully |

**The 4-star review technique:** Skip 5-star (too positive) and 1-star (rage-driven). Focus on 4-star reviews: "I love X but wish it could Y" = your product opportunity.

> For competitor research grid and battlecard structure, read `references/competitor-research.md`

### Step 4: Community Signal Mining

Search for evidence of real people describing this problem in communities. This provides qualitative depth that search data alone cannot.

**Reddit deep dive:**
- Search Reddit for problem keywords
- Check r/findareddit for relevant communities
- Search in unexpected places — audiences organize by IDENTITY, not category
- Look for decision-stage language: "looking for a tool that...", "alternative to...", "willing to pay"

**Grading community evidence:**

| Signal | Strength |
|--------|----------|
| 50+ upvotes on a problem thread | Real pain, shared widely |
| 10+ comments with specific details | Validated need |
| People sharing workarounds | No good solution exists |
| Thread is 1+ years old, still active | Persistent problem |
| "Willing to pay" or "take my money" language | Payment intent |
| Same problem in 5+ communities | Cross-validated pain |
| Only in founder/builder communities | May not be real customer demand |
| Theoretical discussion only | Weak signal |

**Beyond Reddit:** Hacker News (hn.algolia.com), Twitter/X, GitHub Issues, Product Hunt comments, industry-specific forums, Facebook Groups, Discord servers.

**Source quality hierarchy (for evaluating any research finding):**

| Tier | Source Type | Reliability |
|------|-----------|-------------|
| 1 | Primary data: company reports, government statistics, original research | Highest |
| 2 | Reputable analysts: Gartner, Forrester, McKinsey | High |
| 3 | Industry publications: trade journals, specialized news | Medium-High |
| 4 | General business press: WSJ, Bloomberg, Reuters | Medium |
| 5 | Aggregators: secondary analysis, blog posts | Low-Medium |
| 6 | LLM-generated analysis without sources | Do not cite |

> For community mining methodology, read `references/community-mining.md`
> For trend classification approach, read `references/trend-signals.md`

### Step 5: Trend Classification

Assess whether this problem and market are growing, stable, or declining. Trend direction determines strategy and urgency.

**Check these trend indicators:**
- Google Trends trajectory for core keywords (2-5 year view)
- Ahrefs volume history (if available)
- Number of new competitors entering (growing market signal)
- Funding activity in the space (Crunchbase, tech press)
- Regulatory or technology changes creating new demand
- Product Hunt launches in the category (frequency and reception)
- Job postings in the space (companies hiring = growing)

**Classify the trend:**

| Classification | Signal | Implication |
|----------------|--------|-------------|
| Rapid growth (>20% YoY) | Expanding market, new entrants, funding activity | Ride the wave, speed matters |
| Moderate growth (5-20% YoY) | Stable expansion, maturing solutions | Good timing, differentiation matters |
| Stable (<5% change) | Mature market | Must steal share, positioning is everything |
| Declining | Shrinking volume, competitors exiting | Risky unless capturing remaining demand at premium |
| Seasonal | Predictable cycles | Time launch and marketing to peaks |
| Emerging | Low volume but accelerating | Early mover opportunity, validate carefully |

**Structural trend drivers to investigate:**

Not all trends are organic demand changes. Some are driven by structural forces with staying power:

| Driver Type | What Changed | Example | Durability |
|-------------|-------------|---------|------------|
| Technology shift | New capability became accessible | LLMs enabled document understanding | High — tech doesn't un-invent |
| Regulatory change | New rules create requirements | Privacy laws require consent tracking | High — regulations rarely roll back |
| Market behavior shift | Customer expectations changed | Remote work normalized async tools | Medium-High — behavior is sticky |
| Cost shift | Economics changed | Cloud costs dropped, AI APIs commoditized | Medium — can shift again |
| Platform change | Major platform added/removed feature | Google deprecated a popular API | Medium — platform-dependent |
| Cultural shift | Attitudes or norms changed | Solo founders expect solo-friendly tools | Medium — gradual and lasting |

If you can identify a structural driver, the trend is likely durable. If the trend is purely search-volume driven with no clear structural cause, treat it with more skepticism.

> For detailed trend classification methodology, read `references/trend-signals.md`

### Step 6: Signal Triangulation

No single signal is sufficient. Cross-reference across sources:

| Signal Source | What It Tells You | Confidence |
|--------------|-------------------|------------|
| Search volume > 100/mo | People are looking | Medium |
| CPC > $0 | Someone's monetizing | High |
| 3+ competitors exist | Market validated | High |
| Competitors running ads | Proven willingness to pay | Very High |
| 5+ Reddit threads, 50+ upvotes each | Widespread pain | High |
| People describing workarounds | No good solution yet | Very High |
| "Willing to pay" language | Payment intent | Very High |
| Growing search trend | Market expanding | High |
| One viral thread only | Could be outlier | Low |
| Friends say "great idea" | Politeness | Very Low |

**Strongest combination:** Search demand EXISTS + competitors PAYING for ads + community members describe WORKAROUNDS.

## Output: Demand Scorecard

Rate each dimension 1-5 with specific evidence:

```markdown
## Demand Scorecard

### 1. Search Demand: X/5
(1=zero, 2=<50/mo, 3=50-500/mo, 4=500-5000/mo, 5=5000+/mo with CPC)
**Evidence:** [Specific keywords, volumes, CPC values]
**Key finding:** [Most important search data insight]

### 2. Competition: X/5
(1=none exists, 2=only free/OSS, 3=healthy competition, 4=crowded but differentiable, 5=dominated by well-funded players)
**Evidence:** [Top competitors, pricing, gaps identified]
**Key finding:** [Biggest competitive insight]

### 3. Community Evidence: X/5
(1=zero mentions, 2=occasional threads, 3=regular discussion, 4=active seeking, 5=multiple communities with active seekers)
**Evidence:** [Thread counts, platforms, key quotes]
**Key finding:** [Most compelling community signal]

### 4. Payment Signals: X/5
(1=nobody pays for similar, 2=only free solutions, 3=paid competitors exist, 4=multiple price points + CPC, 5=high CPC + premium competitors + WTP language)
**Evidence:** [Competitor pricing, CPC data, payment language found]
**Key finding:** [Strongest payment signal]

### 5. Trend Direction: X/5
(1=declining rapidly, 2=declining slowly, 3=stable, 4=growing moderately, 5=growing rapidly)
**Evidence:** [Trend data source and trajectory]
**Key finding:** [Most important trend insight]

### Total Score: XX/25
- 20-25: Strong market. Proceed with confidence.
- 15-19: Promising. Worth testing with smoke test.
- 10-14: Uncertain. Needs repositioning or deeper research.
- 5-9: Weak. Consider pivoting audience, positioning, or shelving.

### Competitor Matrix
| Competitor | Type | Pricing | Traffic Est. | Key Strength | Key Weakness | Gap for You |
|-----------|------|---------|-------------|-------------|-------------|-------------|
| | | | | | | |

### Search Data Summary
| Keyword | Volume/mo | CPC | KD | Intent |
|---------|-----------|-----|-----|--------|
| | | | | |

### Assessment
**Verdict:** [Strong / Promising / Uncertain / Weak]
**Biggest opportunity:** [What the data says you should exploit]
**Biggest risk:** [What the data says could kill this]
**Recommended next step:** [Specific action]
```

## Tools

### Required
- Web search, web fetch

### Optional (Enhanced Results)
- **Ahrefs MCP** — `keywords-explorer-overview`, `keywords-explorer-matching-terms`, `site-explorer-metrics`, `site-explorer-organic-competitors`, `batch-analysis`. Provides quantitative search demand and competitor intelligence. Fallback: web search for Google Trends, competitor pricing pages, review sites.
- **Dialog Reddit Research MCP** — semantic search across Reddit for pain points and demand signals. Fallback: use `site:reddit.com` web searches.
- **Google Trends MCP** — trend trajectory data. Fallback: web search for Google Trends screenshots/data.

## Related Skills

- **Previous:** [problem-extraction](/skills/problem-extraction) — Validates the problem is real before quantifying demand
- **Next:** [audience-identification](/skills/audience-identification) — Defines WHO has this problem worst and WHERE to find them
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit to check for confirmation bias in interpreting demand data
