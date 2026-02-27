---
name: positioning
description: "Translate your solution into customer language and create messaging that resonates. Triggers: position my product, write my messaging, landing page copy, value proposition, how do I describe this, what should my headline say, positioning strategy, differentiation"
---

# Positioning

> Translates your itch-built product into language and framing that makes a stranger immediately think "this was built for me."

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

Also review outputs from previous skills if they exist:
- `problem-extraction` — Problem Validation Brief (language table, pain data)
- `demand-discovery` — Demand Scorecard (competitor gaps, search terms)
- `audience-identification` — Audience Report (segment definition, community language)

## Purpose

The gap between how builders describe their products and how customers describe their problems kills more itch products than any technical shortcoming. You built for YOUR context, workflow, and preferences. Their context is different. This skill bridges that gap by applying April Dunford's positioning framework adapted for indie products, mining Voice of Customer language from real sources, and producing positioning statements, headline drafts, key messages, and a "Why Now" narrative — all grounded in evidence rather than builder enthusiasm.

## Methodology

### Step 1: Competitive Alternatives Analysis

Start here — not with features. What would your best-fit customer do WITHOUT you?

**This is NOT "who are your competitors?"** For most itch products, the real competition isn't other software. It's:

| Alternative Type | Example | Your Advantage Over It |
|-----------------|---------|----------------------|
| Spreadsheets | Google Sheets, Excel templates | Automation, error reduction, real-time data |
| Manual processes | Doing it by hand | Time savings, consistency, scale |
| Hiring someone | VA, contractor, employee | Cost savings, speed, availability |
| Cobbled-together stack | 3-4 tools + Zapier | Simplicity, unified view, fewer failure points |
| Doing nothing | Living with the pain | Productivity gain, risk reduction |
| Direct software competitor | Named tools in the category | [Specific gap you fill] |

**How to identify alternatives:**
- From problem-extraction: what workarounds did people describe?
- From demand-discovery: what competitors were found?
- From audience-identification: what does your beachhead segment use now?
- Direct question: "If you couldn't use [your product], what would you do?"

**Critical insight:** Your differentiation is relative to what they'd do OTHERWISE. If the alternative is a spreadsheet, "easy to use" is not differentiation (spreadsheets are easy). "Automatic data sync so you never manually enter anything" is differentiation.

### Step 2: Key Unique Attributes

What does your product have or do that the alternatives from Step 1 don't?

**Be specific, not vague:**
- Vague: "Better" / "Faster" / "More powerful" / "AI-powered"
- Specific: "Automatically imports from [source] so you never manually enter data"
- Specific: "Shows [metric] in real-time instead of end-of-month reports"
- Specific: "One-click [action] instead of a 12-step process"

**For itch products specifically:** Your unique attributes often come from the CONSTRAINTS you built under. You built something simple because you didn't have time for complexity. That simplicity IS the feature. You built exactly what one person needed because you were that person. That focus IS the differentiation.

List 3-5 unique attributes. If you can't identify any, this is a positioning problem that needs to be solved before writing any copy.

### Step 3: Value Translation (The "So What?" Chain)

For EVERY unique attribute, ask "so what?" repeatedly until you hit an outcome the customer emotionally cares about.

**Example chain:**
- Feature: Auto-imports data from Shopify
- So what? No manual entry
- So what? Saves 3 hours per week
- So what? That's 3 hours you can spend on products that sell, not spreadsheet admin
- **THAT's the value.**

**Value categories that resonate:**

| Category | Pattern | Example |
|----------|---------|---------|
| Time | "Get back X hours/week" | "Reclaim your Friday afternoons" |
| Money | "Save $X/month vs [alternative]" | "Costs less than one hour of your VA's time" |
| Risk | "Never miss [critical thing] again" | "Catch stockouts before they cost you sales" |
| Pain | "Stop [dreaded task] forever" | "Never copy-paste between tabs again" |
| Status | "Look professional" | "Send reports that impress your clients" |

Map each attribute to its terminal value. The value statement — not the feature — goes in your messaging.

### Step 4: Best-Fit Customer Definition

Pull from audience-identification if available. If not, work through this:

Who cares MOST about the value from Step 3? Not "who could use this" but "who would be DESPERATE for this?"

**Best-fit customer characteristics:**
- The problem costs them the most (time, money, or pain)
- They have budget to pay
- They're actively looking (not passively suffering)
- They're reachable through channels you can access
- Their context is closest to YOUR context (itch product advantage)

**Write a one-sentence best-fit customer description:**
"[Role] at [company type] who [specific situation] and currently [workaround/pain]."

### Step 5: Market Category Selection

What context makes your value immediately obvious?

Category sets expectations. When you say "CRM," people expect contact management, pipelines, reporting. The right category gives instant understanding. The wrong category means explaining yourself constantly.

**Category options for itch products:**

| Option | When to Use | Example |
|--------|------------|---------|
| Existing category, differentiated | Your product fits a known bucket but with a twist | "A CRM built for freelancers" |
| Subcategory | You serve a niche within a broader category | "Lightweight project tracking for agencies" |
| Comparison positioning | Your audience knows and uses a specific competitor | "Like [known tool] but simpler and half the price" |
| New category | Nothing else fits (risky, avoid if possible) | Only when truly novel — rare for itch products |

**The Less Annoying CRM principle:** Sometimes your category IS your positioning. The company name tells you everything: it's a CRM, and it's less annoying. That's brilliant positioning in five words.

### Step 6: Voice of Customer (VOC) Mining

Mine real customer language from reviews, communities, and forums to write copy that sounds like THEM, not like you.

**Sources to mine:**
- Amazon reviews for books and products in the problem domain
- G2/Capterra/TrustPilot reviews for competitor products
- Reddit threads where people discuss the problem
- YouTube comments on tutorials about the manual process
- Support forums for competitor products
- App Store / Play Store reviews for mobile competitors

**What to extract:**

| Language Type | What to Capture | How It's Used |
|---------------|----------------|---------------|
| "Before state" language | How they describe life with the problem | Becomes headline / above-fold copy |
| "Dream state" language | What they wish existed | Becomes value proposition |
| Emotional phrases | "I'm so tired of...", "I hate that..." | Authentic messaging and ad copy |
| Category language | What they call the solution type | Category positioning and SEO |
| Objection language | "The problem with most..." | FAQ section and objection handling |

**The 4-star review technique:** Focus on 4-star reviews of competitors. These contain "I love X but wish it could Y" — the gap between X and Y is your opportunity. Read at least 20 reviews per competitor.

> For detailed VOC mining methodology, read `references/voc-mining.md`

### Step 7: "Why Now" Analysis

Every great positioning needs a timing narrative. What changed in the market, technology, or regulation that makes your product possible or necessary NOW — not last year, not next year, but now?

**"Why Now" categories:**

| Driver | What Changed | Example |
|--------|-------------|---------|
| Technology shift | New capability became available | "LLMs make it possible to extract data from documents automatically" |
| Market shift | Customer behavior or expectations changed | "Remote work means teams need async tools, not real-time meetings" |
| Regulatory change | New rules create new requirements | "New privacy regulations require consent tracking that spreadsheets can't handle" |
| Cost shift | Something got cheaper or more expensive | "Cloud costs dropped enough to offer enterprise features at SMB pricing" |
| Cultural shift | Attitudes or norms changed | "Solo founders now expect tools built for one-person companies, not stripped-down enterprise" |
| Competitive gap | Established player became complacent | "[Competitor] hasn't shipped major updates in 2 years while the problem has evolved" |

If you can't articulate a compelling "Why Now," it doesn't mean the product is bad — it means the urgency angle needs work, or you rely on the timeless "it's always been painful, now there's finally a good solution."

**How to find your "Why Now":**
1. Search for recent news, regulations, or technology announcements affecting your problem domain
2. Check if competitor landscape has changed recently (major player acquired, shut down, raised prices)
3. Look for behavior shifts in your audience (new tools they've adopted that create new workflows)
4. Consider whether macro trends (AI adoption, remote work, regulation) have changed the problem

**"Why Now" strength assessment:**

| Strength | Signal | Example |
|----------|--------|---------|
| Very strong | Structural change that creates the problem | New regulation requires compliance tracking |
| Strong | Technology shift that enables the solution | AI makes document extraction feasible for indie builders |
| Moderate | Market shift that changes expectations | Competitors raised prices, leaving a gap |
| Weak | General trend that's been building for years | "More people work remotely" (true but not urgent) |
| None | No timing angle | "This problem has always existed" (still valid, just harder to market) |

### Step 8: Assemble Positioning and Messaging

**Positioning statement (internal — guides all external messaging):**

> "For [best-fit customers] who [situation/pain], [product] is [market category] that [key benefit] unlike [competitive alternatives] which [limitation the alternatives have]."

**Draft H1/H2 (for landing page hero):**

Use patterns that work for itch products:

| Pattern | H1 | H2 |
|---------|-----|-----|
| Direct statement | "[Desired outcome] for [specific audience]" | "[How it works in one sentence]" |
| Pain killer | "Stop [painful task] forever" | "[Product] does [task] automatically so you can [outcome]" |
| Replacement | "Replace your [painful process] with [better thing]" | "[Benefit 1]. [Benefit 2]. [Benefit 3]." |
| Less annoying | "[Category] that doesn't [main complaint]" | "[How you're different in one line]" |

**The H1 test:** Someone in your beachhead segment should read it and immediately think "this was built for me." If it could apply to any product in your category, it's too generic.

**3-5 Key Messages (benefit-focused, in customer language):**
Each message should:
- Start from the customer's pain or desired outcome (not your feature)
- Use VOC language where possible
- Be specific enough to differentiate ("saves time" fails; "saves 4 hours/week on inventory" works)
- Connect a unique attribute → value chain from Step 3

**Ad copy validation:** Write 2-3 ad headlines as a positioning stress test. If the positioning is strong, ads write themselves. If you struggle to write a compelling 90-character headline, the positioning needs work. Use a before/after structure: "[Pain] → [Outcome with product]."

### Common Positioning Traps for Itch Products

Watch for these patterns — they're especially common when the builder writes their own messaging:

| Trap | What It Sounds Like | Why It Fails | Fix |
|------|---------------------|-------------|-----|
| Feature-first | "AI-powered analytics with real-time sync" | Nobody cares about features. They care about outcomes. | Lead with what the feature DOES for them |
| Platform positioning | "An all-in-one solution for [broad category]" | Too vague. You're one person. Pick the ONE thing. | Narrow to your strongest value for your beachhead |
| Technology positioning | "Built with [tech stack/algorithm]" | Customers don't care how it's built | Rewrite as the outcome the technology enables |
| Builder's excitement | "I was frustrated so I built something better!" | YOUR story, not their value prop. About page material, not H1. | Reframe from their perspective: what do THEY get? |
| Everything positioning | Trying to appeal to multiple audiences at once | "For everyone" = "for no one" | Pick ONE segment and position exclusively for them |
| Comparison positioning | "Like [famous product] but for [niche]" | Only works if the famous product IS their current solution | Use only when the comparison genuinely helps them understand |

**Self-check:** Read your positioning statement aloud. Does it sound like something the CUSTOMER would say, or something the BUILDER would say? If it's the latter, rewrite it.

> For landing page copy patterns and architecture, read `references/landing-page-copy.md`

## Output: Positioning Package

```markdown
## Positioning Package

### Positioning Statement
"For [best-fit customers] who [situation/pain], [product] is [market category] that [key benefit] unlike [competitive alternatives] which [limitation]."

### Competitive Alternatives Mapped
| Alternative | What They Do | Our Advantage |
|------------|-------------|---------------|
| | | |

### Value Chain
| Unique Attribute | So What? | Terminal Value |
|-----------------|----------|---------------|
| | | |

### Draft H1/H2 (2-3 variants to test)
**Variant A:**
- H1: [headline]
- H2: [subheadline]

**Variant B:**
- H1: [headline]
- H2: [subheadline]

**Variant C:**
- H1: [headline]
- H2: [subheadline]

### Key Messages
1. [Benefit-focused message in customer language]
2. [Benefit-focused message in customer language]
3. [Benefit-focused message in customer language]
4. [Benefit-focused message in customer language]
5. [Benefit-focused message in customer language]

### VOC Phrase Bank
**Pain phrases:**
- "[exact quote]" — [source]
- "[exact quote]" — [source]

**Outcome phrases:**
- "[exact quote]" — [source]
- "[exact quote]" — [source]

**Emotional language:**
- "[exact quote]" — [source]
- "[exact quote]" — [source]

### "Why Now" Narrative
[2-3 sentences explaining what changed to make this product timely]

### Ad Copy Test (Positioning Validation)
- Ad 1: "[90-char headline targeting pain]"
- Ad 2: "[90-char headline targeting outcome]"
- Ad 3: "[90-char headline targeting comparison]"

### Message Match Check
Keyword → Ad → Landing page H1 → CTA must all align:
- Target keyword: [keyword]
- Ad copy: [matches keyword intent]
- H1: [matches ad promise]
- CTA: [matches page message] — use first-person: "Start my [X]" not "Start your [X]"
```

## Tools

### Required
- Web search, web fetch (for review mining on G2, Capterra, Amazon, Reddit)

### Optional (Enhanced Results)
- **Ahrefs MCP** — `keywords-explorer-matching-terms` reveals how customers phrase their searches, feeding VOC and keyword targeting. Fallback: Google autocomplete analysis.

## Related Skills

- **Previous:** [audience-identification](/skills/audience-identification) — Defines the beachhead segment this positioning targets
- **Next:** [smoke-test](/skills/smoke-test) — Tests positioning with real traffic and conversion measurement
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit to catch feature-first positioning and builder language leaking into customer-facing copy
