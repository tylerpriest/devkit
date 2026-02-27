---
name: feature-teardown
description: "Analyze how competitors implement a specific feature to inform your build decisions. Triggers: feature teardown, how do competitors do this, competitor feature analysis, how do others implement, tear down this feature, feature comparison, competitive feature analysis, how should I build this feature"
---

# Feature Teardown

> Systematically analyze how 3-7 products implement a specific feature — UX patterns, technical architecture, strengths, weaknesses — then synthesize cross-implementation patterns into actionable build recommendations.

## Purpose

Before building a feature, study how others already implement it. Not just direct competitors — the best implementation of "onboarding wizard" or "notification preferences" might come from a completely different product category. This skill replaces guesswork with structured competitive intelligence at the feature level.

Feature teardowns answer:
- What UX patterns do existing products use for this feature?
- What technical approaches are common (and which are innovative)?
- What do users love and hate about each implementation?
- What are the table-stakes patterns vs. differentiation opportunities?
- What should I build, what should I skip, and what can I steal?

## When to Use This Skill

Use feature teardown when:
- You're about to build a feature and want to study prior art
- You're evaluating UX approaches for a specific interaction
- You want to understand why competitors made certain design decisions
- You're looking for the "best in class" implementation to learn from
- You need to prioritize what to include in your v1 of a feature

Do NOT use this skill for:
- Broad product-level competitive analysis (use demand-discovery or positioning instead)
- Market sizing or demand validation (use market-sizing or demand-discovery)
- Pricing research (use pricing-discovery)

## Methodology

### Step 1: Feature Definition & Scoping

Before researching anything, force precision about what "the feature" actually is. Vague scoping leads to scattered research.

**Capture the Feature Brief:**

| Dimension | Question | Example |
|-----------|----------|---------|
| Problem trigger | What situation makes a user need this feature? | "User receives too many notifications and misses important ones" |
| Core job | What is the user trying to accomplish? | "Control which notifications reach me and how" |
| Success outcome | How does the user know the feature worked? | "I only see notifications I care about, through channels I prefer" |
| Scope boundary | What is explicitly NOT part of this feature? | "Not the notification delivery system itself — just user preferences" |
| Feature type | Is this a flow, a setting, a view, a widget, an integration? | "Settings panel with per-channel, per-type controls" |

**Common scoping mistakes:**
- Scoping too broadly ("the dashboard") — narrow to a specific interaction ("the dashboard widget configuration flow")
- Scoping too narrowly ("the button color") — expand to the full user interaction
- Mixing features ("search and filtering") — tear down one at a time unless they're inseparable
- Ignoring adjacent features that affect UX ("notification preferences" depends on "notification types")

**Ask the maker to confirm the Feature Brief before proceeding.** Misaligned scope wastes every subsequent step.

### Step 2: Competitor Discovery

Find 3-7 products that implement this feature. Cast a wide net — the best implementation often comes from outside the maker's category.

**Three search strategies:**

#### Strategy A: Direct Category Search
Products in the same space.
- Web search: "[feature name] in [product category]"
- G2/Capterra: search feature name in category filters
- Product Hunt: search feature name, sort by upvotes
- "[competitor] [feature name]" for known competitors

#### Strategy B: Cross-Domain Search
Products in different categories that implement the same interaction pattern.
- Web search: "best [feature type] UX examples"
- Web search: "[feature pattern] design patterns" (e.g., "wizard UX design patterns")
- Dribbble/Behance: search interaction pattern for design references
- UX case studies: "[feature name] UX case study"
- "Best [feature] examples" blog posts and roundups

#### Strategy C: Technical Discovery
Products known for strong engineering of this feature type.
- GitHub: search for open-source implementations
- Engineering blogs: "[feature name] architecture" or "[feature name] at scale"
- Developer docs: products with public APIs exposing this feature
- Conference talks: "[feature name] implementation" on YouTube

**With Ahrefs MCP (if available):**
- Run `keywords-explorer-matching-terms` for "[feature name] tool" and "[feature name] software"
- Check top-ranking pages for competitive roundups and comparison posts
- Run `site-explorer-organic-competitors` on known competitors to find similar products

**Competitor selection criteria:**
Aim for a diverse set, not just direct competitors:

| Slot | Why Include | Example for "notification preferences" |
|------|-----------|---------------------------------------|
| 1-2 | Direct competitors (same category) | Competing SaaS products |
| 1-2 | Best-in-class (known for great UX) | Slack, Linear, Notion |
| 1 | Cross-domain leader (different category, same pattern) | YouTube notification settings |
| 1 | Open-source/developer tool (technical reference) | GitLab, Discourse |
| 0-1 | Outlier/innovator (unconventional approach) | Any product doing it differently |

**Output a Competitors Analyzed table:**

```markdown
| # | Product | Category | Why Included | Access Method |
|---|---------|----------|-------------|---------------|
| 1 | | | | Web / API docs / Open source |
```

### Step 3: UX Pattern Teardown

For each competitor, systematically analyze the feature's UX. Do not rely on memory or assumptions — actually visit the product.

> For the complete UX teardown methodology, state inventory template, and interaction pattern classification, read `references/ux-teardown-method.md`

**Core teardown dimensions per competitor:**

#### 3a. Entry Point & Discoverability
- How does the user find/access this feature?
- Navigation path (clicks from homepage or dashboard)
- Is it obvious or buried? Primary nav, settings, contextual?
- Any progressive disclosure (shown only when relevant)?

#### 3b. Core Flow
Walk through the primary interaction:
1. What is the first thing the user sees?
2. What inputs/decisions does the user make?
3. What is the interaction pattern? (wizard, modal, inline edit, form, drag-and-drop, etc.)
4. How many steps to complete the core job?
5. What's the information architecture? (tabs, accordion, flat list, etc.)

#### 3c. State Handling
Capture every state the feature can be in:

| State | What the User Sees | Notes |
|-------|-------------------|-------|
| Empty/first-time | | Is there onboarding, defaults, or a blank slate? |
| Loading | | Skeleton, spinner, progressive load? |
| Populated/active | | The "happy path" state |
| Error | | How are errors shown? Recovery options? |
| Partial/incomplete | | What happens mid-flow if user abandons? |
| Edge case | | What happens with extreme inputs? |

#### 3d. Defaults & Configuration
- What are the default settings? (Opinionated vs. blank slate)
- Can the user customize? How granular is control?
- Are there presets or templates?
- What's the reset/undo mechanism?

#### 3e. Feedback & Confirmation
- How does the product confirm actions succeeded?
- Toast notifications, inline confirmation, page redirect?
- Is there undo? How long is the undo window?
- What microcopy is used at key moments?

#### 3f. Escape Hatches
- Can the user cancel mid-flow?
- Is there a "back" option at every step?
- What happens if the user navigates away?
- Can they undo/revert after completing?

**With Browser/Playwright MCP (if available):**
- Navigate to each product's feature
- Take screenshots at each state
- Record the interaction flow
- Note load times and transition animations

**Without browser access — fallback approach:**
- Web search for "[product] [feature] screenshot" or "[product] [feature] walkthrough"
- Check product marketing pages, help docs, YouTube demos
- Look for review sites with screenshots (G2, Capterra)
- Check the product's changelog or blog for feature announcement posts (often include screenshots/GIFs)

**Output a UX teardown summary per competitor:**

```markdown
### [Product Name] — UX Teardown

**Entry point:** [How users access it]
**Core pattern:** [Wizard / Modal / Inline / Form / etc.]
**Steps to complete:** [Number]
**Default behavior:** [Opinionated / Blank / Template-based]
**Key UX decisions:**
- [Decision 1 and likely rationale]
- [Decision 2 and likely rationale]
**States handled:** [List which states are well-handled vs. missing]
**Standout moment:** [One thing this implementation does notably well]
**Friction point:** [One thing that creates unnecessary friction]
```

### Step 4: Technical Implementation Analysis

Analyze how competitors build the feature technically — without having access to their source code (unless open-source).

> For the complete technical analysis methodology, search patterns, and structured templates, read `references/technical-analysis-method.md`

**Four investigation methods:**

#### 4a. Public API Analysis
If the product has a public API, it reveals architectural decisions:
- Web search: "[product] API documentation [feature area]"
- Check developer docs for relevant endpoints
- Note: data models, naming conventions, parameters, response shapes
- What the API exposes reveals what the backend supports

**What API design reveals:**

| API Pattern | Implies |
|------------|---------|
| Separate endpoints per sub-feature | Modular architecture |
| Single endpoint with many params | Monolithic, flexible but complex |
| Webhook support for feature | Event-driven, real-time capable |
| Rate limits on feature | Performance-sensitive operation |
| Batch endpoints | Designed for scale |
| Versioned endpoints | Mature, backward-compatible |

#### 4b. Developer Documentation Mining
Product docs, SDK references, and integration guides reveal implementation details:
- Data models and schemas
- Configuration options and their boundaries
- Integration patterns (webhooks, polling, real-time)
- Limitations and known constraints (docs often list these explicitly)

#### 4c. Open-Source Code Review
For open-source competitors, dive into the actual implementation:
- GitHub search: "[feature name]" in repo, filter by language
- Look at: data models, state management, API layer, UI components
- Check issues and PRs related to the feature for design decisions and tradeoffs
- Read commit messages for evolution of the feature

#### 4d. Engineering Blog & Conference Talk Mining
Companies often write about how they built notable features:
- Web search: "[company] engineering blog [feature]"
- Web search: "[company] [feature] architecture"
- YouTube: "[company] [feature] talk" or "[feature] at scale"
- Job postings: roles related to this feature reveal tech stack and architecture priorities

**Output a technical summary per competitor:**

```markdown
### [Product Name] — Technical Analysis

**Evidence sources:** [API docs / Open source / Eng blog / Inferred]
**Architecture approach:** [Description based on evidence]
**Data model (inferred):** [Key entities and relationships]
**Integration pattern:** [REST / GraphQL / Webhooks / Real-time]
**Scale indicators:** [Evidence of how it handles scale]
**Notable technical decisions:**
- [Decision 1 with evidence source]
- [Decision 2 with evidence source]
**Confidence level:** [High (source code) / Medium (API + docs) / Low (inferred)]
```

### Step 5: Strengths & Weaknesses Assessment

For each competitor's implementation, assess what works and what doesn't. Back every claim with evidence.

**Evidence sources (in order of reliability):**

| Source | Reliability | What It Reveals |
|--------|-----------|----------------|
| Your own UX teardown (Step 3) | High | Interaction quality, flow logic |
| User reviews mentioning the feature | High | Real user experience |
| Reddit/HN threads about the feature | Medium-High | Unfiltered opinions |
| GitHub issues (for open-source) | High | Actual bugs and feature requests |
| Competitor's own changelog | Medium | What they've had to fix/improve |
| Blog posts about switching from competitor | Medium | Dealbreaker identification |

**What to assess per competitor:**

```markdown
### [Product Name] — Strengths & Weaknesses

**Strengths:**
1. [Strength] — Evidence: [source]
2. [Strength] — Evidence: [source]
3. [Strength] — Evidence: [source]

**Weaknesses:**
1. [Weakness] — Evidence: [source]
2. [Weakness] — Evidence: [source]
3. [Weakness] — Evidence: [source]

**User sentiment summary:**
- What users praise most: [with source]
- What users complain about most: [with source]
- Most-requested improvement: [with source]
```

**Where to find feature-specific user feedback:**
- Web search: "[product] [feature] review" or "[product] [feature] problems"
- Reddit: "site:reddit.com [product] [feature]"
- G2/Capterra: search reviews for feature-specific keywords
- GitHub issues: filter by feature label or keyword
- Twitter/X: "[product] [feature]" for real-time complaints and praise
- Product Hunt: comments on the feature launch post

### Step 6: Cross-Implementation Pattern Extraction

This is the synthesis step. Stop analyzing individual competitors and look across all implementations to find patterns.

> For the complete pattern extraction framework, convergence/divergence matrix, innovation scoring, and "steal this" methodology, read `references/pattern-extraction-framework.md`

**Four pattern categories to extract:**

#### 6a. Universal Patterns (Table Stakes)
Things every competitor does — these are non-negotiable for your implementation:
- What UX patterns appear in 4+ of your analyzed products?
- What technical approaches are consistent across implementations?
- What user expectations have been set by existing products?

If all competitors do it, your users will expect it. Deviating from universal patterns requires strong justification.

#### 6b. Divergent Choices
Places where competitors made different (valid) decisions:
- Where do implementations meaningfully differ?
- What tradeoffs does each choice represent?
- Is there a clear winner, or are they optimized for different audiences?

Divergent choices are where your positioning matters. Choose the approach that aligns with YOUR audience.

#### 6c. Innovation Outliers
One or two implementations that do something genuinely novel:
- What does one competitor do that nobody else does?
- Is it a gimmick or a genuine improvement?
- Could it be adopted without the rest of their architecture?

Innovation outliers are differentiation opportunities — but validate that the innovation actually helps users, not just that it's different.

#### 6d. Anti-Patterns
Things competitors do poorly that you should avoid:
- What patterns consistently receive negative feedback?
- What UX choices create unnecessary friction?
- What technical decisions lead to performance or reliability issues?

**Output a Cross-Implementation Pattern Matrix:**

```markdown
## Cross-Implementation Patterns

### Universal Patterns (Table Stakes)
| Pattern | Seen In | User Expectation |
|---------|---------|-----------------|
| | [Product A, B, C...] | |

### Divergent Choices
| Choice Point | Option A | Option B | Tradeoff |
|-------------|----------|----------|----------|
| | [Products using A] | [Products using B] | |

### Innovation Outliers
| Innovation | Product | What It Does | Adoptable? |
|-----------|---------|-------------|------------|
| | | | Yes/No — [reason] |

### Anti-Patterns to Avoid
| Anti-Pattern | Seen In | Evidence of Harm |
|-------------|---------|-----------------|
| | | [User complaints, poor metrics, etc.] |
```

### Step 7: Actionable Recommendations

Synthesize everything into a prioritized, actionable build plan.

**Recommendation framework:**

#### Must Have (Table Stakes)
Features and patterns that are universal across competitors. Shipping without these will feel incomplete to users. Source from Step 6a universal patterns.

#### Should Have (Expected Polish)
Common patterns that most competitors include. Missing these won't block adoption but will generate "why doesn't it do X?" feedback. Source from Step 6a/6b overlap.

#### Differentiation Opportunities
Where your implementation can stand out. Source from Step 6b divergent choices (pick the better side) and Step 6c innovations (adopt the adoptable ones).

#### Avoid
Anti-patterns and approaches that consistently fail. Source from Step 6d.

#### "Steal This"
Specific implementation details worth borrowing — but only UX patterns and interaction ideas, never proprietary visual designs or code.

| Idea | Source Product | What to Steal | What NOT to Copy |
|------|--------------|--------------|-----------------|
| | | [The pattern/interaction] | [Their specific visual design/branding] |

#### Architecture Recommendation
Based on the technical analysis, recommend an implementation approach:
- Suggested data model (informed by what works across competitors)
- Integration pattern (REST, webhooks, real-time — based on what the feature requires)
- Build vs. buy decisions for sub-components
- Phased rollout suggestion (v1 = must-haves, v2 = should-haves + differentiation)

## Output: Feature Teardown Report

```markdown
# Feature Teardown: [Feature Name]

## Feature Brief
- **Problem trigger:** [What situation creates the need]
- **Core job:** [What the user is trying to do]
- **Success outcome:** [How the user knows it worked]
- **Scope:** [What's in and out of scope]
- **Feature type:** [Flow / Setting / View / Widget / Integration]

## Competitors Analyzed
| # | Product | Category | Why Included | Access Method |
|---|---------|----------|-------------|---------------|
| 1 | | | | |

## UX Pattern Matrix
| Dimension | [Product 1] | [Product 2] | [Product 3] | [Product N] |
|-----------|------------|------------|------------|------------|
| Entry point | | | | |
| Core pattern | | | | |
| Steps to complete | | | | |
| Default behavior | | | | |
| Empty state | | | | |
| Error handling | | | | |
| Undo/recovery | | | | |
| Standout moment | | | | |
| Friction point | | | | |

## Technical Architecture Comparison
| Dimension | [Product 1] | [Product 2] | [Product 3] | [Product N] |
|-----------|------------|------------|------------|------------|
| Architecture | | | | |
| Data model | | | | |
| Integration pattern | | | | |
| Scale approach | | | | |
| Confidence level | | | | |

## Strengths & Weaknesses
### [Product 1]
**Best at:** [One-line summary]
**Weakest at:** [One-line summary]
**Key user feedback:** [Most telling quote or signal]

### [Product 2]
...

## Cross-Implementation Patterns

### Universal Patterns (Must Build)
1. [Pattern] — seen in [N] of [total] products
2. ...

### Divergent Choices (Pick Your Side)
1. [Choice] — Option A: [products] / Option B: [products] — Recommended: [choice] because [reason]
2. ...

### Innovation Outliers (Differentiation Opportunities)
1. [Innovation] from [product] — Adoptable: [yes/no, why]
2. ...

### Anti-Patterns (Avoid)
1. [Pattern] — seen in [products] — Evidence of harm: [source]
2. ...

## Build Recommendations

### Must Have (Table Stakes)
- [ ] [Feature/pattern 1]
- [ ] [Feature/pattern 2]
- [ ] ...

### Should Have (Expected Polish)
- [ ] [Feature/pattern 1]
- [ ] [Feature/pattern 2]
- [ ] ...

### Differentiation Opportunities
- [ ] [Opportunity 1] — from [source]
- [ ] [Opportunity 2] — from [source]
- [ ] ...

### Avoid
- [Anti-pattern 1] — [why]
- [Anti-pattern 2] — [why]

### "Steal This" Ideas
| Idea | Source | Steal the Pattern | Don't Copy |
|------|--------|-------------------|-----------|
| | | | |

## Architecture Recommendation
**Suggested approach:** [Summary]
**Data model:** [Key entities]
**Integration pattern:** [REST / Webhooks / Real-time]
**Build vs. buy:** [Sub-components]
**Phased rollout:**
- v1: [Must-haves]
- v2: [Should-haves + differentiation]

## Next Steps
1. [Specific action with clear scope]
2. [Specific action with clear scope]
3. [Specific action with clear scope]
```

## Tools

### Required
- **Web search** — Competitor discovery, UX research, user feedback mining, technical documentation lookup
- **Web fetch** — Read product pages, API documentation, engineering blogs, review sites, pricing pages

### Optional (Enhanced Results)
- **Ahrefs MCP** — `keywords-explorer-matching-terms` for feature-related keyword discovery, `site-explorer-organic-competitors` for finding similar products. Fallback: web search for competitor roundup posts and comparison articles.
- **Browser/Playwright MCP** — Navigate competitor products to observe actual UX flows, capture screenshots, test interaction patterns. Fallback: web search for product screenshots, walkthrough videos, help documentation with screenshots.

### Fallback Strategy
Every step has a non-MCP fallback path. If enhanced tools are not available:
- Competitor discovery: web search for roundup posts, G2/Capterra category pages, Product Hunt
- UX analysis: marketing pages, help docs, YouTube walkthroughs, review site screenshots
- Technical analysis: public API docs (via web fetch), engineering blog posts, GitHub repos
- User feedback: web search with `site:reddit.com`, G2/Capterra reviews, GitHub issues

## Related Skills

This is a standalone plugin. It complements — but does not depend on — the validation-skills plugin.

**Complementary validation-skills (if installed):**
- **demand-discovery** — Validates that market demand exists for the broader product before building specific features
- **positioning** — Uses feature teardown insights to inform competitive positioning and messaging
- **pricing-discovery** — Feature comparison data informs pricing strategy and feature-tier decisions
- **audience-identification** — Understanding who your audience is helps scope which competitors matter most

**When to use feature-teardown vs. validation-skills:**
- Use **feature-teardown** when you know WHAT you're building and want to study HOW others build it
- Use **validation-skills** when you're deciding WHETHER to build something at all
