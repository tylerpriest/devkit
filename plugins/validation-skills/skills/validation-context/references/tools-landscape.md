# External Tools Landscape

Every external tool, platform, and framework whose methodology was incorporated into the validation-skills plugin. This reference documents what each tool does and which skills draw from its approach.

---

## Tools and Methodology Sources

| Tool | What It Does | Skills Using Its Methodology |
|---|---|---|
| **CheckFast** | Search volume-to-revenue calculator that validates business viability through keyword demand data | market-sizing, demand-discovery |
| **Atypica** | AI-powered audience research platform that builds detailed customer personas from behavioral and psychographic data | audience-identification |
| **BigIdeasDB** | Curated database of validated business ideas with pain-point severity scoring from cross-platform complaint mining | problem-extraction, demand-discovery |
| **DimeADozen** | AI business validator that generates comprehensive feasibility reports including market timing and competitive analysis | demand-discovery, market-sizing |
| **ValidatorAI** | AI startup idea validator with simulated customer objections and calibrated scoring from 200K+ submissions | smoke-test, go-no-go |
| **IdeaFloat** | AI business idea evaluator with financial modeling, breakeven analysis, and community discovery mapping | market-sizing, pricing-discovery, distribution-plan |
| **PainOnSocial** | Social media pain-point discovery tool that identifies and scores customer frustrations from online conversations | problem-extraction, demand-discovery |
| **Exploding Topics** | Trend discovery platform that identifies rapidly growing topics before they become mainstream | demand-discovery, market-sizing |
| **Informly** | Market research AI that generates multi-dimensional validation reports with competitive intelligence | demand-discovery, market-sizing, go-no-go |
| **IdeaProof** | Industry-specific business idea validator with templates tailored to SaaS, marketplace, physical product verticals | validation-context, smoke-test |
| **Crayon** | Competitive intelligence platform that tracks competitor changes and generates standardized battlecard reports | demand-discovery, market-sizing |
| **DigitalApplied 48-Hour Sprint** | Structured rapid validation framework with branching interview scripts, teardown grids, and weighted scoring matrices | smoke-test, go-no-go, pricing-discovery |
| **AI Labs Startup Validator** | Open-source Claude skill with TAM/SAM/SOM frameworks, Porter's Five Forces, and market attractiveness scoring | market-sizing |

---

## Methodology Integration Map

### Problem Discovery and Demand Validation

The **problem-extraction** and **demand-discovery** skills synthesize techniques from tools that scrape real user signals:

- **BigIdeasDB** approach: Cross-platform complaint mining (Reddit, G2, App Store, Google Play, Upwork, Product Hunt) with AI-driven pain-point extraction and severity scoring. We adapted the multi-source signal methodology into structured search queries across communities.
- **PainOnSocial** approach: Social media listening focused on frustration language patterns. We incorporated the pain-severity scoring concept and frustration-keyword taxonomy.
- **Exploding Topics** approach: Trend detection before mainstream adoption. We use Google Trends trajectory analysis and emerging keyword monitoring as demand timing signals.
- **Crayon** approach: Systematic competitor change tracking. We adapted the structured competitive intelligence checklist and battlecard format.

### Market Sizing and Financial Modeling

The **market-sizing** skill combines frameworks from multiple sources:

- **CheckFast** approach: Bottom-up TAM from search volume data through a chain: Search Volume -> CTR -> Visitors -> Conversion Rate -> Customers -> ARPU -> Revenue -> TAM. This is the core of our bottom-up estimation methodology.
- **AI Labs Startup Validator** approach: TAM/SAM/SOM frameworks, Porter's Five Forces analysis, and a quantitative market attractiveness scoring algorithm (0-100 scale across growth, size, competition, and maturity).
- **IdeaFloat** approach: Financial modeling with expense categorization, breakeven analysis, margin analysis, and scalability assessment at different customer counts.
- **DimeADozen** approach: Market timing assessment and feasibility scoring across multiple dimensions.
- **Informly** approach: Multi-dimensional validation scoring that weights market opportunity, competition, and problem severity.

### Audience and Positioning

The **audience-identification** and **positioning** skills draw from:

- **Atypica** approach: Behavioral and psychographic persona building. We adapted the multi-dimensional persona framework that goes beyond demographics to capture behaviors, motivations, and decision criteria.
- **IdeaProof** approach: Industry-specific validation templates. The recognition that SaaS, marketplace, and physical product ventures require fundamentally different validation approaches informed our context-adaptive methodology.

### Testing and Decision Making

The **smoke-test** and **go-no-go** skills incorporate:

- **DigitalApplied 48-Hour Sprint** approach: Structured rapid validation with branching interview scripts, competitor teardown grids, weighted scoring matrices, and smoke test landing page optimization. This informed our time-boxed validation methodology and scoring frameworks.
- **ValidatorAI** approach: Simulated customer objections and calibrated confidence scoring based on patterns from 200K+ idea submissions. We adapted the objection-anticipation methodology and evidence-based confidence calibration.

### Pricing and Distribution

The **pricing-discovery** and **distribution-plan** skills use:

- **IdeaFloat** approach: Community discovery mapping to identify where target audiences congregate, combined with financial modeling for breakeven and margin analysis.
- **DigitalApplied** approach: Pricing survey methodology and value-based pricing frameworks from the 48-hour sprint template.

---

## Data Source Tools (Used Directly, Not for Methodology)

These tools are used directly during skill execution rather than as methodology sources:

| Tool | Purpose | Skills That Use It |
|---|---|---|
| **Ahrefs** | Search volume, CPC, keyword difficulty, competitor traffic analysis | demand-discovery, market-sizing, pricing-discovery |
| **Google Trends** | Search interest over time, geographic breakdown, related queries | demand-discovery, market-sizing |
| **G2 / Capterra** | Software review mining for competitor gaps and customer language | demand-discovery, positioning |
| **Reddit** (via Dialog MCP or web search) | Community signal mining, pain point discovery, audience identification | problem-extraction, demand-discovery, audience-identification, distribution-plan |
| **Product Hunt** | New product launches, competitive landscape, launch strategy | demand-discovery, distribution-plan |
| **Indie Hackers** | Public revenue data, founder interviews, competitor benchmarking | market-sizing, pricing-discovery |

---

## Honest Assessment of Tool Landscape

Most all-in-one AI idea validators (DimeADozen, ValidatorAI, IdeaProof, Informly) are essentially structured LLM prompts with formatted output. They are useful for brainstorming blind spots and structuring thinking, but they don't scrape real data, talk to real users, or validate demand with real signals.

The real-data tools (BigIdeasDB, Ahrefs, Exploding Topics) provide genuine market signals but are fragmented — no single tool covers the full validation workflow.

The validation-skills plugin bridges this gap: it uses Claude Code's tool access (web search, web fetch, Ahrefs MCP, Reddit MCP) to run the same kind of research these tools automate, while applying the structured frameworks and scoring methodologies they pioneered. The result is evidence-based validation rather than LLM-generated guesses formatted as market research.
