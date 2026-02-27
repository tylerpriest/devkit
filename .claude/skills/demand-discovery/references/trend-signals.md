# Trend Signals

How to classify, interpret, and act on market trend data during demand discovery.

---

## Trend Classification Framework

Every market and problem exists on a trajectory. Understanding where yours sits determines strategy, timing, and urgency.

### Growth Rate Classification

| Category | Growth Rate | Characteristics | Strategy |
|----------|-----------|-----------------|----------|
| Rapid growth | >20% YoY | Expanding market, new entrants, VC funding, media attention | Speed matters. Ship fast, iterate. First acceptable product wins. |
| Moderate growth | 5-20% YoY | Stable expansion, maturing solutions, winners emerging | Good timing. Differentiation matters more than speed. |
| Stable | <5% change | Mature market, established players, slow innovation | Must steal share. Positioning is everything. |
| Declining | Negative YoY | Shrinking volume, competitors exiting, budget reallocation | Risky. Only enter to capture remaining demand at premium. |
| Emerging | Low volume, high growth % | Small base growing fast, few players, uncertain trajectory | Early-mover opportunity. Validate carefully before committing. |

### Speed of Change Classification

| Speed | Signal | Example | Implication |
|-------|--------|---------|-------------|
| Accelerating | Growth rate increasing quarter over quarter | AI tools market 2023-2025 | Jump in now, window closing as market crowds |
| Steady | Consistent growth rate | Project management SaaS | Sustainable, can plan methodically |
| Decelerating | Growth rate slowing | Social media management tools | Approaching maturity, differentiation critical |
| Volatile | Unpredictable spikes and drops | Crypto-adjacent tools | High risk, avoid unless you have asymmetric insight |

### Seasonality Classification

| Pattern | Signal | Example | Strategy |
|---------|--------|---------|----------|
| Strong seasonal | Predictable 2-4x spikes | Tax software (Jan-Apr), fitness (Jan), e-commerce (Q4) | Time launch to pre-season, budget for troughs |
| Mild seasonal | 20-50% variation | Productivity tools (Sept, Jan) | Note peaks but don't over-optimize for them |
| Event-driven | Spikes around specific events | Conference tools, election-related | Plan around event calendar |
| Non-seasonal | Stable throughout year | Infrastructure, security | No timing advantage, launch when ready |

---

## Where to Find Trend Data

### Google Trends (Free)

The baseline for trend analysis. Available to everyone.

**How to use effectively:**
- Search core keywords with 5-year time range for trajectory
- Compare 2-3 keyword variations to find which phrasing trends stronger
- Check "Related queries" — rising queries reveal where demand is going
- Check geographic breakdown — is demand concentrated or distributed?
- Compare your keywords against known-growing categories for relative context

**Google Trends caveats:**
- Shows relative interest, not absolute volume
- Small-volume keywords show noisy data
- Breakout topics (marked "Breakout") had >5000% growth — could be fad or real trend
- Seasonal adjustments not applied — compare year-over-year, not month-over-month

### Ahrefs Volume History (Paid)

When available, Ahrefs provides absolute search volume over time for specific keywords.

**Advantages over Google Trends:**
- Shows actual monthly search volume numbers, not relative index
- Covers longer time periods for some keywords
- Includes CPC history (commercial intent trend)
- Per-keyword granularity

### Funding and Investment Signals

Track money flowing into your space:
- **Crunchbase:** search for companies in your category, filter by recent funding
- **Tech press:** TechCrunch, VentureBeat for funding announcements
- **Acquisitions:** Big companies acquiring in your space = validated market + potential competition

**What funding signals tell you:**

| Signal | Interpretation |
|--------|---------------|
| Multiple startups funded in last 12 months | Hot market, VC-validated demand, expect competition |
| Large rounds ($50M+) for competitors | Market may consolidate around big players |
| Acqui-hires (small acquisitions for team) | Big companies building in-house, harder to compete |
| No funding activity | Either too small for VC or unproven market |
| Funding but no revenue traction | Market may be hype-driven, not demand-driven |

### Market Reports (Mixed Quality)

Industry reports from analysts can confirm trend direction but should be used carefully:

**Trustworthy for trends:** Gartner, Forrester, McKinsey — good for macro direction, less useful for niche sizing
**Use with caution:** Generic market research firms — often recycle data, inflated projections
**Avoid:** Reports from companies selling into the space (biased toward growth narrative)

---

## Interpreting Trend Combinations

### The Ideal Combination

- Growing search volume (demand expanding)
- New competitors entering (market validated by builder activity)
- Existing competitors getting funded (VC-validated)
- Community discussion increasing (real users engaged)
- Technology or regulatory change creating the problem (structural driver)

This combination means: real demand, growing market, and a structural reason for the trend to continue.

### Warning Combinations

- **Growing search + no competitors:** May be too early. Are people searching but nobody can figure out how to serve them? Or is the problem unsolvable?
- **Growing search + declining competitors:** Market may be shifting to a different solution type. Investigate what's replacing the old approach.
- **Declining search + happy customers:** Mature market with loyal users. Hard to break in but possible through niche or innovation.
- **Spike then decline:** Likely a news cycle or hype bubble. Don't build for temporary demand.
- **High search + zero CPC:** People are curious but nobody has figured out how to monetize. May be valuable opportunity or fundamentally non-commercial problem.

---

## Technology and Regulatory Trend Drivers

Some trends are driven by structural changes that create new problems or eliminate old solutions. These are the strongest trend signals because they have staying power.

### Technology Drivers

| Change | New Problems Created | Example |
|--------|---------------------|---------|
| AI/LLM adoption | Content quality, AI detection, prompt engineering, AI cost management | Tools for managing AI spend, detecting AI content |
| Remote work normalization | Async communication, team cohesion, time zone management | Async video tools, virtual team building |
| API economy growth | Integration management, API monitoring, webhook handling | API gateway products, integration platforms |
| No-code/low-code | Template management, migration, scaling limitations | No-code-to-code migration tools |
| Privacy regulations | Compliance management, consent tracking, data deletion | Privacy compliance automation |

### Regulatory Drivers

| Change | New Problems Created | Market Created |
|--------|---------------------|---------------|
| New data privacy laws (GDPR, state laws) | Compliance burden, consent management | Privacy tech ($10B+ market) |
| Industry-specific regulations | Workflow changes, reporting requirements | Vertical compliance SaaS |
| Tax changes | New filing requirements, calculation complexity | Tax automation tools |
| Accessibility requirements | Website/app compliance, testing | Accessibility testing and remediation |
| AI regulation (emerging) | Model documentation, bias testing, transparency | AI governance tools |

**Why regulatory trends are powerful for indie builders:**
- Compliance is mandatory (can't ignore it)
- Budget exists (legal risk justifies spend)
- Big players are slow to adapt (small builders can move faster)
- Domain expertise is a moat (understanding the regulation deeply)

---

## Trend Signal Summary Template

Use this template to document trend findings:

```markdown
### Trend Assessment

**Primary keyword trend:** [Growing / Stable / Declining] — [source]
**Growth rate estimate:** [X% YoY based on volume data]
**Seasonality:** [Pattern description or "non-seasonal"]

**Structural drivers:**
- [Technology change driving demand]
- [Regulatory change driving demand]
- [Market behavior shift driving demand]

**Funding activity in space:**
- [Recent raises, with amounts if known]
- [Acquisitions]

**New entrant activity:**
- [New competitors launched in last 12 months]
- [Product Hunt launches in category]

**Trend classification:** [Rapid growth / Moderate growth / Stable / Declining / Emerging]
**Speed of change:** [Accelerating / Steady / Decelerating / Volatile]
**Confidence level:** [High / Medium / Low] — [basis for confidence]

**Implication for this product:**
[1-2 sentences on what the trend means for timing, strategy, and urgency]
```
