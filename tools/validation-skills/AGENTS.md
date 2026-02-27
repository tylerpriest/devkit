# validation-skills

Product validation and go-to-market skills for Claude Code. 11 skills covering the full journey from idea to first paying customers.

## What This Plugin Does

validation-skills replaces vague encouragement with evidence-based product validation. It uses real data (search volume, competitor analysis, community signals) to answer "should I build this?" and "how do I get customers?" before and during development.

Each skill reads from and writes to a shared `validation-context.md` file in `.claude/`, so findings accumulate across sessions and skills build on each other.

## The 11 Skills

### Foundation

- **validation-context** — Initialize and maintain a shared product context document that all skills read from and write to

### Validation Lifecycle (Run in Order)

1. **problem-extraction** — Strip away your solution and isolate the raw problem in customer language
2. **demand-discovery** — Find evidence of real demand through search volume, community signals, and competitor presence
3. **audience-identification** — Define who has the problem worst, where they congregate, and how to reach them
4. **positioning** — Translate your product into customer language using April Dunford's framework
5. **pricing-discovery** — Find a defensible starting price through competitor mapping and value-based pricing
6. **smoke-test** — Design a lightweight demand test with landing page specs and conversion benchmarks
7. **distribution-plan** — Build a 30-day plan to acquire first 10-100 customers
8. **go-no-go** — Synthesize all evidence into a scored go/no-go/pivot recommendation

### Cross-Cutting (Run Anytime)

- **builder-psychology** — Surface cognitive biases (IKEA effect, sunk cost, confirmation bias) and run structured debiasing at any checkpoint
- **market-sizing** — Quantitative market analysis with TAM/SAM/SOM, Porter's Five Forces, unit economics, and attractiveness scoring

## Lifecycle Entry Points

| User says... | Skills triggered |
|---|---|
| "I have an idea, should I build it?" | validation-context -> problem-extraction -> demand-discovery -> go-no-go |
| "I built something, does anyone want it?" | validation-context -> demand-discovery -> audience-identification -> smoke-test |
| "How should I position this?" | validation-context -> positioning (runs audience-identification if needed) |
| "What should I charge?" | validation-context -> pricing-discovery (runs demand-discovery if needed) |
| "How do I get my first customers?" | validation-context -> distribution-plan (runs audience-identification if needed) |
| "How big is this market?" | validation-context -> market-sizing |
| "Am I fooling myself?" | validation-context -> builder-psychology |
| "Should I keep going or kill this?" | validation-context -> go-no-go (runs any missing prerequisite skills) |
| "Run the full validation" | validation-context -> all lifecycle skills in order |

## MCP Integrations

These MCP servers enhance results when available. All skills have fallback methods using web search.

| MCP Server | What It Provides | Skills That Use It |
|---|---|---|
| **Ahrefs** | Search volume, CPC, keyword difficulty, competitor traffic | demand-discovery, market-sizing, pricing-discovery |
| **Dialog Reddit Research** | Structured Reddit mining, pain point discovery, audience signals | problem-extraction, demand-discovery, audience-identification, distribution-plan |
| **Google Trends** (via web fetch) | Search interest over time, geographic breakdown | demand-discovery, market-sizing |

See `tools/REGISTRY.md` for the full integration registry including Phase 2 planned integrations (G2, Trustpilot, Stripe, Google Ads, outreach tools, and more).

## Architecture

```
validation-skills/
|-- .claude-plugin/marketplace.json
|-- tools/
|   |-- REGISTRY.md               # Tool integrations: current + Phase 2 planned
|   |-- integrations/             # (Phase 2) Per-tool API/MCP guides
|-- skills/
|   |-- validation-context/       # Foundation: shared product context
|   |   |-- references/tools-landscape.md  # External methodology sources
|   |-- problem-extraction/       # Phase 1
|   |-- demand-discovery/         # Phase 2
|   |-- audience-identification/  # Phase 3
|   |-- positioning/              # Phase 4
|   |-- pricing-discovery/        # Phase 5
|   |-- smoke-test/               # Phase 6
|   |-- distribution-plan/        # Phase 7
|   |-- go-no-go/                 # Phase 8
|   |-- builder-psychology/       # Cross-cutting
|   |-- market-sizing/            # Cross-cutting
|-- README.md
|-- AGENTS.md
```

### How Skills Connect

All skills read from and write to `.claude/validation-context.md` in the user's project. This shared document accumulates findings across sessions.

```
validation-context (foundation)
       |
       v
problem-extraction --> demand-discovery --> audience-identification
                           |                       |
                           v                       v
                     market-sizing            positioning
                           |                       |
                           v                       v
                     pricing-discovery        smoke-test
                           |                       |
                           v                       v
                     distribution-plan         go-no-go
                                                   ^
                                                   |
                     builder-psychology ---- (runs at any checkpoint)
```

## Design Principles

1. **Evidence over opinion.** Every claim should be sourced from real data. If evidence can't be found, say so explicitly.
2. **Behavioral signals over stated preferences.** Pre-orders and cold-traffic signups matter. "I'd definitely use this" does not.
3. **Honest assessment over cheerleading.** Surface problems early to save the builder time.
4. **Actionable over theoretical.** Every output includes specific next steps.
5. **Cumulative context.** Each skill writes findings to validation-context.md, compounding analysis across sessions.

## Skill File Structure

Each skill directory contains:
- `SKILL.md` — The main skill definition with methodology, output format, and tool requirements
- `references/` — Detailed reference materials (frameworks, scoring rubrics, research methodology)

Skills follow a consistent format: frontmatter (name, description, triggers), purpose, methodology steps, output template, tool requirements, and related skill cross-references.

## Methodology Sources

This plugin synthesizes methodologies from 13 external tools and frameworks. See `skills/validation-context/references/tools-landscape.md` for the complete list.

Key influences: CheckFast (bottom-up TAM), AI Labs Startup Validator (TAM/SAM/SOM + Porter's Five Forces), Atypica (behavioral personas), DigitalApplied 48-Hour Sprint (rapid validation), and the practitioner stack from Reddit, Indie Hackers, and Hacker News.
