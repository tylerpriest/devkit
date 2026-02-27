# validation-skills

Product validation and go-to-market skills for Claude Code. 11 skills covering the full journey from idea to first paying customers.

## Overview

validation-skills is a Claude Code plugin that replaces vague encouragement with evidence-based product validation. It runs alongside your development workflow, using real data (search volume, competitor analysis, community signals) to answer "should I build this?" and "how do I get customers?" before and during development.

Each skill reads from and writes to a shared `validation-context.md` file, so findings accumulate across sessions and skills build on each other.

## Quick Start

1. Install the plugin in your Claude Code project
2. Say: **"validate my product idea"** or **"start validation"**
3. Claude will run the `validation-context` skill to capture your product details
4. Then proceed through the validation lifecycle, or jump to any specific skill

## Installation

Add the devkit marketplace and install the plugin:

```
/plugin marketplace add tylerpriest/devkit
/plugin install validation-skills@devkit
```

Or add manually by cloning into your project:

```bash
git clone https://github.com/tylerpriest/devkit.git
cp -r devkit/plugins/validation-skills/skills/* your-project/.claude/skills/
```

## The 11 Skills

Skills are organized into three categories: the validation lifecycle (run in order), cross-cutting skills (run anytime), and the foundation skill.

### Foundation

| Skill | Description |
|---|---|
| **validation-context** | Initialize and maintain a shared product context document that all skills read from and write to |

### Validation Lifecycle (Run in Order)

| # | Skill | Description |
|---|---|---|
| 1 | **problem-extraction** | Strip away your solution and isolate the raw problem in customer language |
| 2 | **demand-discovery** | Find evidence of real demand through search volume, community signals, and competitor presence |
| 3 | **audience-identification** | Define who has the problem worst, where they congregate, and how to reach them |
| 4 | **positioning** | Translate your product into customer language using April Dunford's framework |
| 5 | **pricing-discovery** | Find a defensible starting price through competitor mapping and value-based pricing |
| 6 | **smoke-test** | Design a lightweight demand test with landing page specs and conversion benchmarks |
| 7 | **distribution-plan** | Build a 30-day plan to acquire first 10-100 customers |
| 8 | **go-no-go** | Synthesize all evidence into a scored go/no-go/pivot recommendation |

### Cross-Cutting (Run Anytime)

| Skill | Description |
|---|---|
| **builder-psychology** | Surface cognitive biases (IKEA effect, sunk cost, confirmation bias) and run structured debiasing at any checkpoint |
| **market-sizing** | Quantitative market analysis with TAM/SAM/SOM, Porter's Five Forces, unit economics, and attractiveness scoring |

## Lifecycle Entry Points

Not every validation starts at Step 1. Here's where to enter based on your situation:

| You say... | Skills triggered |
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
| **Ahrefs** | Search volume, CPC, keyword difficulty, competitor traffic, organic keyword data | demand-discovery, market-sizing, pricing-discovery |
| **Dialog Reddit Research** | Structured Reddit community mining, pain point discovery, audience signals | problem-extraction, demand-discovery, audience-identification, distribution-plan |
| **Google Trends** (via web fetch) | Search interest over time, geographic breakdown, related queries | demand-discovery, market-sizing |

See `tools/REGISTRY.md` for the full integration registry including Phase 2 planned integrations (G2, SimilarWeb, Stripe, BigIdeasDB, and more).

## Architecture

```
validation-skills/
|
|-- .claude-plugin/
|   |-- plugin.json               # Plugin manifest
|
|-- tools/
|   |-- REGISTRY.md               # MCP integrations: current + planned Phase 2
|
|-- skills/
|   |-- validation-context/       # Foundation: shared product context
|   |   |-- SKILL.md
|   |   |-- references/
|   |       |-- tools-landscape.md  # External tools methodology reference
|   |
|   |-- problem-extraction/       # Phase 1: Isolate the problem
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- demand-discovery/         # Phase 2: Find demand evidence
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- audience-identification/  # Phase 3: Define target audience
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- positioning/              # Phase 4: Craft positioning and messaging
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- pricing-discovery/        # Phase 5: Determine pricing
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- smoke-test/               # Phase 6: Design demand test
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- distribution-plan/        # Phase 7: First customers plan
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- go-no-go/                 # Phase 8: Final decision
|   |   |-- SKILL.md
|   |   |-- references/
|   |
|   |-- builder-psychology/       # Cross-cutting: Bias audits
|   |   |-- SKILL.md
|   |   |-- references/
|   |       |-- cognitive-biases.md
|   |
|   |-- market-sizing/            # Cross-cutting: Market quantification
|       |-- SKILL.md
|       |-- references/
|           |-- analysis-frameworks.md
|           |-- market-calculator.md
|
|-- README.md
```

### How Skills Connect

All skills read from and write to `.claude/validation-context.md` in the user's project. This shared document accumulates findings across sessions, so later skills build on earlier research.

```
validation-context (foundation)
       |
       v
problem-extraction --> demand-discovery --> audience-identification
                                                     |
                                                     v
                                                positioning
                                                     |
                                                     v
                                              pricing-discovery
                                                     |
                                                     v
                                                smoke-test
                                                     |
                                                     v
                                             distribution-plan
                                                     |
                                                     v
                                                 go-no-go

Cross-cutting (run at any checkpoint):
  - builder-psychology
  - market-sizing
```

## Design Principles

1. **Evidence over opinion.** Every claim should be sourced from search data, competitor analysis, community signals, or behavioral evidence. If evidence can't be found, say so explicitly.

2. **Behavioral signals over stated preferences.** "I'd definitely use this" is worthless. Pre-orders, signups from cold traffic, and time investment are meaningful.

3. **Honest assessment over cheerleading.** The goal is to save the builder time by surfacing problems early, not to make them feel good about a doomed product.

4. **Actionable over theoretical.** Every output includes specific next steps, not vague recommendations.

5. **Cumulative context.** Each skill writes findings to validation-context.md, so the analysis compounds across sessions.

## Methodology Sources

This plugin synthesizes methodologies from 13 external tools and frameworks. See `skills/validation-context/references/tools-landscape.md` for the complete list with descriptions and integration mapping.

Key influences: CheckFast (bottom-up TAM from search volume), AI Labs Startup Validator (TAM/SAM/SOM + Porter's Five Forces), Atypica (behavioral persona building), DigitalApplied 48-Hour Sprint (rapid validation framework), and the practitioner stack documented across Reddit, Indie Hackers, and Hacker News.
