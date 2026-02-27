# Tool Registry

MCP server integrations and external data tools used by validation-skills. Each entry documents what the tool provides, which skills use it, setup instructions, and fallback behavior when the tool is unavailable.

---

## Phase 1 Integrations (Current)

These integrations are supported today. All skills have fallback methods using web search and web fetch when these tools are not available.

### Ahrefs MCP

**What it provides:** Real-time search volume, CPC, keyword difficulty, traffic potential, competitor organic/paid keywords, domain metrics, SERP analysis.

**Skills that use it:**
| Skill | MCP Functions Used | What It Gets |
|---|---|---|
| demand-discovery | `keywords-explorer-overview`, `keywords-explorer-matching-terms` | Search volume, CPC, keyword difficulty for problem keywords |
| market-sizing | `keywords-explorer-overview`, `site-explorer-metrics`, `site-explorer-organic-competitors` | TAM estimation from search volume, competitor traffic data |
| pricing-discovery | `keywords-explorer-overview`, `site-explorer-metrics` | CPC as price signal, competitor paid keyword analysis |
| smoke-test | `keywords-explorer-overview`, `serp-overview` | Keyword CPC for Google Ads planning, SERP competition |
| distribution-plan | `keywords-explorer-overview`, `site-explorer-organic-competitors` | Content/SEO keyword targeting, community traffic sources |

**Setup:** Install the Ahrefs MCP server in your Claude Code configuration. Requires an Ahrefs account (from $99/mo).

**Fallback:** Web search for "keyword search volume [term]", Google Ads Keyword Planner (free), Google Trends for trend direction. CPC data is less precise without Ahrefs but directionally available from web search.

---

### Dialog Reddit Research MCP

**What it provides:** Structured Reddit community mining, subreddit discovery, pain point extraction, audience signal analysis, thread monitoring.

**Skills that use it:**
| Skill | What It Gets |
|---|---|
| problem-extraction | Pain point discovery, workaround identification, customer language extraction |
| demand-discovery | Community signal mining, discussion volume, sentiment analysis |
| audience-identification | Subreddit discovery, audience profiling, congregation points |
| distribution-plan | Active seeker threads, decision-stage discussions, community monitoring |

**Setup:** Install the Dialog Reddit Research MCP server. Check Dialog's documentation for current availability and pricing.

**Fallback:** Web search with `site:reddit.com "[search term]"`, manual subreddit browsing, Google Alerts with `site:reddit.com`. Manual monitoring takes 30-45 min/day vs automated.

---

### Google Trends (via Web Fetch)

**What it provides:** Search interest over time, geographic breakdown, related queries, trending topics, comparison between terms.

**Skills that use it:**
| Skill | What It Gets |
|---|---|
| demand-discovery | Trend direction (growing/stable/declining), seasonality patterns |
| market-sizing | Market growth trajectory, geographic demand distribution |

**Setup:** No MCP required. Accessed via web fetch to `trends.google.com` URLs. Works out of the box.

**Fallback:** Web search for "[keyword] google trends" for summary data. Less granular but directionally useful.

---

## Phase 2 Integrations (Planned)

These integrations would enhance specific skills with real data. Phase 2 will add `integrations/*.md` guides and potentially `clis/*.js` wrappers following the [marketingskills](https://github.com/coreyhaines31/marketingskills) pattern.

| Tool | Category | API | MCP | CLI | Would Enhance | Status |
|------|----------|:---:|:---:|:---:|---------------|--------|
| G2 | Reviews | ✓ | - | ✓* | problem-extraction, positioning | Planned |
| Trustpilot | Reviews | ✓ | - | ✓* | problem-extraction, positioning | Planned |
| Google Ads | Ads | ✓ | ✓ | ✓* | smoke-test | Planned |
| Meta Ads | Ads | ✓ | - | ✓* | smoke-test | Planned |
| Stripe | Payments | ✓ | ✓ | ✓* | pricing-discovery, go-no-go | Planned |
| SimilarWeb | Traffic | ✓ | - | - | demand-discovery, market-sizing | Planned |
| Hunter | Email Outreach | ✓ | - | ✓* | distribution-plan | Planned |
| Instantly | Email Outreach | ✓ | - | ✓* | distribution-plan | Planned |
| Lemlist | Email Outreach | ✓ | - | ✓* | distribution-plan | Planned |
| Apollo | Data Enrichment | ✓ | - | ✓* | audience-identification, distribution-plan | Planned |
| Typeform | Forms/Surveys | ✓ | - | ✓* | problem-extraction, pricing-discovery | Planned |
| DataForSEO | SEO/SERP | ✓ | - | ✓* | demand-discovery, market-sizing | Planned |

*CLI available via marketingskills `tools/clis/` — shared API keys work for both plugins.

### How Phase 2 Tools Would Enhance Validation

**Reviews & VOC Mining (G2, Trustpilot)**
- problem-extraction: Automated pain-point extraction from competitor negative reviews
- positioning: Real customer language from review text (not guesses)
- pricing-discovery: Price sensitivity signals from review mentions

**Smoke Testing & Ads (Google Ads, Meta Ads)**
- smoke-test: Run actual paid traffic experiments with real conversion data
- Budget forecasting from keyword CPC and audience size estimates

**Distribution & Outreach (Hunter, Instantly, Lemlist, Apollo)**
- distribution-plan: Find prospect emails, send cold outreach sequences
- audience-identification: B2B prospect enrichment for persona validation

**Payments & Pricing (Stripe)**
- pricing-discovery: Real revenue impact data from pricing changes
- go-no-go: Actual financial metrics (MRR, churn, LTV) for PMF measurement

**Advanced Market Data (SimilarWeb, DataForSEO)**
- demand-discovery: Competitor traffic volumes as market size proxy
- market-sizing: More accurate TAM from competitor traffic + SERP data

**Surveys & Forms (Typeform)**
- problem-extraction: Deploy Mom Test interview forms
- pricing-discovery: Van Westendorp pricing surveys sent to real prospects

---

## Integration Architecture

```
validation-skills
    |
    |-- Phase 1 (Current) ---- Ahrefs MCP (search demand data)
    |                      |-- Dialog Reddit MCP (community signals)
    |                      |-- Google Trends (trend direction)
    |                      |-- Web Search (universal fallback)
    |                      |-- Web Fetch (page content access)
    |
    |-- Phase 2 (Planned) ---- G2/Trustpilot (review mining)
                           |-- Google Ads/Meta Ads (smoke tests)
                           |-- Hunter/Instantly/Lemlist (outreach)
                           |-- Apollo (prospect enrichment)
                           |-- Stripe (revenue metrics)
                           |-- SimilarWeb/DataForSEO (market data)
                           |-- Typeform (survey deployment)
```

## Compatibility with marketingskills

This plugin runs alongside [marketingskills](https://github.com/coreyhaines31/marketingskills). Where tool overlap exists, shared API keys work for both plugins:

| Tool | marketingskills Uses For | validation-skills Uses For |
|------|-------------------------|---------------------------|
| Ahrefs | SEO audits, backlink analysis | Demand quantification, competitor traffic |
| G2 | Review management | Competitor VOC mining, pain extraction |
| Google Ads | Campaign management | Smoke test experiments |
| Stripe | Payment analytics | Pricing validation, PMF metrics |
| Hunter | Link building outreach | Direct prospect outreach |

## Fallback Behavior

Every skill works with web search and web fetch alone. MCP/CLI integrations enhance precision and speed but are never required. Fallback behavior is documented in each SKILL.md under the "Tools" section.
