# feature-teardown

Feature-level competitive analysis for Claude Code. Tear down how competitors implement specific features — UX patterns, technical architecture, strengths, weaknesses — then synthesize cross-implementation patterns into actionable build recommendations.

## Overview

Before building a feature, study how others already implement it. Not just direct competitors — the best implementation of "notification preferences" or "onboarding wizard" might come from a completely different product category. This plugin replaces guesswork with structured competitive intelligence at the feature level.

feature-teardown is a standalone plugin. It complements the validation-skills plugin (which handles product-level analysis like demand, positioning, and pricing) but does not depend on it.

## Quick Start

1. Install the plugin in your Claude Code project
2. Say: **"feature teardown"** or **"how do competitors implement [feature]?"**
3. Claude will guide you through scoping the feature, discovering competitors, and analyzing implementations
4. You'll receive a Feature Teardown Report with prioritized build recommendations

## Installation

Add the devkit marketplace and install the plugin:

```
/plugin marketplace add tylerpriest/devkit
/plugin install feature-teardown@devkit
```

## Example Use Cases

| You say... | What happens |
|-----------|-------------|
| "Feature teardown for notification preferences" | Full 7-step teardown of how products handle notification settings |
| "How do competitors implement onboarding wizards?" | Cross-domain analysis of onboarding wizard patterns |
| "Competitor feature analysis for drag-and-drop file upload" | UX + technical teardown of file upload implementations |
| "How should I build search? What do others do?" | Search feature teardown with architecture recommendations |
| "Tear down how Notion, Linear, and Slack handle keyboard shortcuts" | Targeted teardown of specific products' implementations |

## The 7-Step Methodology

| Step | Purpose | Output |
|------|---------|--------|
| 1. Feature Definition & Scoping | Precisely define the feature: problem, trigger, outcome, scope boundary | Feature Brief |
| 2. Competitor Discovery | Find 3-7 products with this feature — including cross-domain | Competitors Analyzed table |
| 3. UX Pattern Teardown | Analyze entry point, core flow, states, defaults, feedback, escape hatches | UX teardown per competitor |
| 4. Technical Implementation Analysis | Research API docs, developer docs, open-source repos, engineering blogs | Technical summary per competitor |
| 5. Strengths & Weaknesses Assessment | Assess what works and what doesn't, backed by reviews and community feedback | Strengths/weaknesses per competitor |
| 6. Cross-Implementation Pattern Extraction | Synthesize universal patterns, divergent choices, innovations, anti-patterns | Cross-Implementation Pattern Matrix |
| 7. Actionable Recommendations | Must-have, should-have, differentiation opportunities, architecture recommendation | Prioritized build plan |

## Architecture

```
feature-teardown/
|-- .claude-plugin/
|   |-- plugin.json               # Plugin manifest
|
|-- skills/
|   |-- feature-teardown/
|       |-- SKILL.md              # Core skill: 7-step methodology + output template
|       |-- references/
|           |-- ux-teardown-method.md           # UX analysis methodology
|           |-- technical-analysis-method.md    # Technical analysis without source access
|           |-- pattern-extraction-framework.md # Synthesis and prioritization framework
|
|-- README.md
```

### Reference Files

| File | Purpose | Size |
|------|---------|------|
| `ux-teardown-method.md` | Feature walk-through protocol, state inventory, micro-copy audit, interaction pattern classification, accessibility/performance checks | ~9KB |
| `technical-analysis-method.md` | Public API analysis, developer doc mining, open-source code review, engineering blog mining, job posting analysis | ~9KB |
| `pattern-extraction-framework.md` | Convergence/divergence matrix, innovation scoring, anti-pattern detection, "steal this" framework, MoSCoW build priority | ~8KB |

## MCP Integrations

These MCP servers enhance results when available. All steps have fallback methods using web search and web fetch.

| MCP Server | What It Provides | Steps That Use It |
|-----------|-----------------|------------------|
| **Ahrefs** | Keyword discovery for finding competitor roundups, competitor domain analysis | Step 2: Competitor Discovery |
| **Browser/Playwright** | Navigate competitor products, observe UX flows, capture screenshots | Step 3: UX Pattern Teardown |

### Fallback Strategy

Every step works without MCP integrations:
- **Competitor discovery:** Web search for roundup posts, G2/Capterra categories, Product Hunt
- **UX analysis:** Marketing pages, help docs, YouTube walkthroughs, review site screenshots
- **Technical analysis:** Public API docs (via web fetch), engineering blogs, GitHub repos
- **User feedback:** Web search with `site:reddit.com`, G2/Capterra reviews, GitHub issues

## Design Principles

1. **Evidence over assumption.** Every recommendation is backed by data from the teardown — convergent patterns, user reviews, or technical evidence. If evidence doesn't exist, say so.

2. **Breadth then depth.** Start by analyzing 3-7 products broadly, then go deep on the most interesting approaches. Don't get stuck analyzing one competitor exhaustively.

3. **Patterns over products.** The goal is not to copy any single competitor. It's to identify universal patterns (table stakes), divergent choices (positioning decisions), and innovations (differentiation opportunities).

4. **Actionable over encyclopedic.** Every teardown ends with a prioritized build plan: must-have, should-have, differentiation opportunities, and explicit "avoid" list. No analysis without recommendations.

5. **Cross-domain thinking.** The best implementation of a feature often comes from outside your category. Explicitly include products from different domains that solve the same interaction problem.

## Relationship to validation-skills

feature-teardown and validation-skills are complementary but independent:

| Question | Use This |
|----------|---------|
| "Should I build this product?" | validation-skills (demand-discovery, go-no-go) |
| "How should I build this feature?" | feature-teardown |
| "Who is my audience?" | validation-skills (audience-identification) |
| "How do competitors implement search?" | feature-teardown |
| "What should I charge?" | validation-skills (pricing-discovery) |
| "What UX patterns work for onboarding?" | feature-teardown |

Feature teardown insights can inform validation-skills analysis (competitive positioning benefits from feature-level intelligence) and vice versa (knowing your audience helps you pick the right competitors to analyze).
