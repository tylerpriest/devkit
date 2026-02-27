# Competitor Research

Structured methodology for mapping competitive landscapes, building competitor teardowns, and creating battlecard-format intelligence summaries.

---

## Finding All Competitors

Most founders undercount their competition. Map three layers:

### Layer 1: Direct Competitors
Same solution to the same problem for the same audience.

**Where to find them:**
- Google search: top 10 organic + all ad results for core keywords
- G2/Capterra category pages
- Product Hunt: search category, sort by recent
- "Alternative to [known competitor]" searches
- Reddit recommendation threads: "What do you use for [task]?"

### Layer 2: Indirect Competitors
Different solution to the same problem.

**Common indirect competitors for software products:**
- Spreadsheet templates (Google Sheets, Excel) — the default for everything
- Manual processes — doing it by hand, however painful
- Hiring someone — VA, contractor, freelancer, new employee
- Cobbled-together stack — 3-4 tools connected with Zapier/Make
- Platform features — what if Notion/Slack/Salesforce adds this capability?
- Consultant/agency services — paying a human to do the work

### Layer 3: Stealth Competitors
Things you might miss that absorb customer budget or attention.

- Free tools: open-source projects, Google Sheets templates shared in communities
- Intern/VA doing it manually for $15-25/hr
- Status quo: living with the pain and never solving it
- Adjacent products expanding scope (platform creep)
- Enterprise tools trickling down to SMB (freemium tiers)

**For most itch products, the biggest "competitor" is the spreadsheet or manual process.** Your positioning should primarily beat THAT, not other software.

---

## 4-Part Competitor Teardown Grid

For each significant competitor (top 3-5), conduct a structured teardown:

### Part 1: Product Intelligence

| Dimension | What to Capture | Where to Look |
|-----------|----------------|---------------|
| Core features | What does it do? Main capabilities | Product page, feature list |
| Key differentiator | How do THEY position themselves? | Homepage H1, about page |
| Target audience | Who do they say they're for? | Pricing page tiers, case studies |
| Platform/tech | Web, mobile, desktop? Integrations? | Product docs, integration page |
| Maturity | How long in market? Recent releases? | Blog, changelog, Crunchbase |
| AI/automation | Any AI features? | Feature page, recent announcements |

### Part 2: Business Intelligence

| Dimension | What to Capture | Where to Look |
|-----------|----------------|---------------|
| Pricing model | Per-seat, flat, usage, freemium? | Pricing page |
| Price range | Lowest to highest tier | Pricing page (web fetch) |
| Free plan | What's included? Limitations? | Pricing page, signup flow |
| Trial terms | Length, credit card required? | Signup page |
| Estimated traffic | Monthly visits | Ahrefs/SimilarWeb |
| Estimated revenue | Public data if available | Indie Hackers, Crunchbase, interviews |
| Funding | Bootstrapped or funded? How much? | Crunchbase, press releases |
| Team size | How many people? | LinkedIn, About page |

### Part 3: Market Intelligence

| Dimension | What to Capture | Where to Look |
|-----------|----------------|---------------|
| SEO keywords | Top organic keywords | Ahrefs organic keywords |
| Paid keywords | What they bid on | Ahrefs paid keywords |
| Content strategy | Blog topics, guides, tools | Blog page, resource center |
| Social presence | Followers, engagement, platforms | Social media profiles |
| Community | Forum, Discord, subreddit? | Website, social links |
| Partnerships | Integrations, co-marketing | Partners page, blog announcements |

### Part 4: Customer Intelligence

| Dimension | What to Capture | Where to Look |
|-----------|----------------|---------------|
| Review score | Average rating | G2, Capterra, TrustPilot |
| Total reviews | Volume of reviews | G2, Capterra |
| Top praise | What customers love most | 5-star review themes |
| Top complaints | What customers hate most | 1-3 star review themes |
| Feature gaps | "I wish it could..." | 4-star reviews, Reddit |
| Audience gaps | Who they DON'T serve well | Negative reviews from specific segments |
| Switching reasons | Why people leave | Reddit, G2 "cons" section |
| Loyalty drivers | Why people stay | G2 "pros" section, testimonials |

---

## The 4-Star Review Technique

The most valuable competitive intelligence lives in 4-star reviews.

- **5-star reviews:** Too positive. Often incentivized. "Love it!" tells you nothing actionable.
- **1-star reviews:** Rage-driven. Often unfair or user error. Noisy data.
- **4-star reviews:** Honest. Specific. Balanced. They contain the pattern: "I love X but wish it could Y."

**Patterns to extract from 4-star reviews:**

| Pattern | What It Reveals | Your Opportunity |
|---------|----------------|-----------------|
| "Great for [A] but not [B]" | Underserved use case | Build for use case B |
| "Love it but too expensive" | Price sensitivity | Compete on price |
| "Would be perfect if..." | Feature gap | Build the missing feature |
| "Easy to use but missing..." | Simplicity vs power tradeoff | Start simple, add depth |
| "Good for small teams but..." | Scaling limitations | Serve the segment they outgrow |
| "Works but the UX is..." | Design opportunity | Win on usability |

Read at least 20 reviews per competitor to identify reliable patterns.

---

## Competitor Battlecard Format

For quick reference during positioning and messaging work, create a battlecard for each major competitor:

```markdown
## Battlecard: [Competitor Name]

### Quick Facts
- **Founded:** [year]
- **Funding:** [amount or "bootstrapped"]
- **Pricing:** [range, model]
- **Est. customers:** [if known]
- **Est. traffic:** [monthly]

### How They Position
**Tagline:** "[their H1 or tagline]"
**Target:** [who they say they serve]
**Category:** [how they categorize themselves]

### Their Strengths
- [Strength 1]
- [Strength 2]
- [Strength 3]

### Their Weaknesses
- [Weakness 1 — source: reviews/research]
- [Weakness 2 — source: reviews/research]
- [Weakness 3 — source: reviews/research]

### Where We Win
- [Our advantage 1 vs their weakness]
- [Our advantage 2 vs their gap]
- [Segment they underserve that we target]

### Where They Win
- [Their advantage over us — be honest]
- [What we'd need to match or counter]

### Switching Triggers
What makes their customers leave:
- [Trigger 1 from review data]
- [Trigger 2 from community research]

### Key Review Quotes
> "[Relevant 4-star review quote]" — G2
> "[Relevant complaint from Reddit]" — r/[subreddit]
```

---

## Competitive Matrix Template

Summarize all competitors in a single comparison matrix:

```markdown
| Dimension | [Your Product] | Competitor A | Competitor B | Competitor C |
|-----------|---------------|-------------|-------------|-------------|
| Target audience | | | | |
| Core positioning | | | | |
| Starting price | | | | |
| Free tier | | | | |
| Key differentiator | | | | |
| Review score (G2) | N/A | | | |
| Top complaint | N/A | | | |
| Est. traffic | N/A | | | |
| Your advantage | — | | | |
```

---

## What Competition Tells You

### Healthy Signs
- 3-10 competitors = validated market with room for differentiation
- Mix of funded and bootstrapped = accessible market
- Active G2/Capterra pages with recent reviews = buyers actively evaluating
- Growing number of new entrants = expanding market
- Competitors charging $50+/mo = willingness to pay established
- Gap between enterprise solutions and small tools = mid-market opportunity

### Warning Signs
- 0 competitors = usually means no market, not blue ocean. Validate very carefully.
- Only enterprise players ($10K+/yr) = may be hard to reach SMB audience without sales team
- All competitors free/open-source = monetization is the hard problem
- One dominant player with 80%+ market share = expensive to unseat
- Competitors pivoting away from this market = they know something you don't
- All competitors declining in traffic = market may be shrinking

### Actionable Frameworks

**If the market is crowded:** Win on niche focus. Pick the segment that's underserved and position exclusively for them.

**If there's one dominant player:** Find their ignored segment. Every big player has customers they serve poorly. Be the best option for that group.

**If the market is emerging:** Move fast. In early markets, the first product with acceptable quality wins. Don't over-build.

**If the market is declining:** Either avoid it, or capture remaining demand at premium pricing with zero competition overhead.
