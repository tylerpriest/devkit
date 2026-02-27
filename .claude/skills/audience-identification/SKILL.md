---
name: audience-identification
description: "Define WHO has your problem worst and WHERE to find them. Triggers: find my audience, who is my customer, target audience, customer persona, who would buy this, find my market, segment my audience, beachhead market"
---

# Audience Identification

> Defines exactly WHO has your problem the worst, WHERE they congregate, and which segment to target first — turning "anyone who..." into a specific, reachable beachhead.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

Also review outputs from `problem-extraction` (Problem Validation Brief) and `demand-discovery` (Demand Scorecard) if they exist — they contain community evidence and language patterns that feed directly into audience identification.

## Purpose

Generic audiences don't convert. "Anyone who manages projects" is not a customer segment — it's a wish. This skill forces specificity: narrowing from a broad problem space down to 1-3 concrete audience segments, scoring them on pain severity, budget, and reachability, then mapping exactly where each segment congregates online and offline. The output is a prioritized segment list with a clear recommendation for your beachhead market.

## Methodology

### Step 1: The Specificity Principle

Start by testing whether the current audience definition from `validation-context.md` is specific enough.

**The "obviously awesome" test (April Dunford):** Your best-fit customer should read your H1 and immediately think "this was built for me." If your messaging works for everyone, it works for no one.

**Run the narrowing exercise:**

| Question | Why It Matters |
|----------|---------------|
| What SIZE of company/team has this problem worst? (Solo, 2-10, 11-50, 50+?) | Pain intensity varies dramatically by scale |
| What ROLE deals with this problem daily? (Founder, PM, marketer, ops, developer?) | The person who feels the pain is the person who buys |
| What INDUSTRY has the most acute version? (SaaS, ecom, agencies, local biz, finance?) | Industry context shapes language, budget, and buying behavior |
| What TRIGGER makes them seek a solution NOW? (New hire, new client, scaling, audit, regulation?) | Triggers convert awareness into action |
| What BUDGET tier are they in? (Bootstrap $0-50/mo, SMB $50-200/mo, mid-market $200+/mo?) | Budget determines what you can charge and how you sell |

If the answer to any of these is "everyone" or "it depends," the segment is too broad. Keep narrowing until you have a description specific enough that you could write a Reddit post targeting only that person.

**Good segment specificity test:**
- Too broad: "Small business owners"
- Still broad: "Small business owners who track inventory"
- Getting specific: "Retail shop owners with 1-3 locations managing inventory in spreadsheets"
- Useful: "Independent boutique owners with 1-3 locations who waste 4+ hours/week counting stock manually because Shopify's built-in inventory doesn't handle multi-location well"

### Step 2: Persona Extraction from Community Research

Use evidence from previous skills (problem-extraction community research, demand-discovery signal mining) to build data-driven personas — not imaginary ones.

**Reddit Thread Analysis Method:**

For each relevant thread found in earlier research:

*From the original post, extract:*
- What role/title does the poster have?
- What company size/type?
- What triggered them to post NOW?
- What have they already tried?
- What specific outcome do they want?

*From the comments, extract:*
- Do commenters share the same context or different?
- What solutions do commenters recommend?
- What language patterns repeat?
- Who are the most engaged commenters? (Check post history for more context)

**Build composite personas from 10+ threads:**
- Common role/title pattern
- Common company stage or size
- Common trigger events
- Common current tools/workarounds
- Common desired outcomes
- Common objections or concerns

**The "2 AM Post" Method:**

The most valuable community posts are emotional, unfiltered, usually posted late at night. They reveal:
- Real frustration (not polished feedback)
- Actual workflow context
- True priorities (what they care about when not performing)
- The gap between what they SAY they want and what they actually need

Search for emotionally charged language in target subreddits:
- "frustrated with", "sick of", "wasted hours", "can't believe"
- "finally found", "game changer", "wish I knew about"
- "anyone else deal with", "am I the only one"

> For the full 7-dimensional persona template, read `references/persona-template.md`

### Step 3: Adjacent Community Discovery

Your audience may not be where you expect. Subreddits and communities organize by IDENTITY, not industry category.

**Mapping technique:**
1. Start with the obvious communities (r/[your industry])
2. Look at what OTHER communities your target users post in
3. Check sidebar links for "related communities"
4. Think about the IDENTITY of your user, not just their job title

**Examples of unexpected audience locations:**
- Fitness app customers found in r/ADHD (exercise as coping mechanism)
- B2B communication tool insights found in r/relationships (same communication patterns)
- Productivity tool users active in r/digitalminimalism (not r/productivity)
- Accounting software users in r/freelance (not r/accounting)
- Developer tool users in r/sysadmin or r/devops (not r/programming)

**The identity question:** Beyond their job title, how does your target user THINK of themselves?
- "I'm a scrappy founder trying to do everything myself"
- "I'm a creative who hates admin work"
- "I'm a data person stuck in a spreadsheet-first company"
- "I'm the one person who cares about doing things properly"

Identity shapes which communities they join and which messaging resonates.

### Step 4: Decision-Stage Language Mapping

People at different stages of problem-solving use different language. For your first 10 customers, focus on Stages 4-5 — people already evaluating solutions.

| Stage | Language Pattern | Example Searches | Your Approach |
|-------|----------------|------------------|---------------|
| 1. Unaware | No searching | — | Can't target directly (expensive, slow) |
| 2. Problem-aware | "how to fix [problem]", "why does [thing] keep happening" | "why does my inventory keep running out" | Educational content, thought leadership |
| 3. Solution-aware | "best [category] tool", "[A] vs [B]" | "best inventory management small business" | Comparison content, differentiation |
| 4. Product-aware | "has anyone used [product]", "[product] review" | "[competitor] review reddit" | Social proof, testimonials, direct outreach |
| 5. Decision-stage | "looking for a tool that...", "switching from [X]" | "switching from spreadsheets to inventory software" | Direct response with specific value prop |

**Decision-stage trigger phrases to monitor:**
- "looking for a tool that..."
- "evaluating alternatives"
- "has anyone replaced [X]?"
- "switching from [X] because..."
- "budget for [category]"
- "need to solve [problem] by [deadline]"
- "willing to pay for..."
- "recommendations for [task]?"

### Step 5: Founder-Idea Fit Assessment

Not all audiences are equally good for YOU. Assess fit between the founder and each identified segment. This is especially important for itch products, where the founder's personal experience is a competitive advantage — but only for the segment closest to their own context.

| Dimension | Assessment Questions | Strong Signal | Weak Signal |
|-----------|---------------------|--------------|-------------|
| **Domain expertise** | Do you deeply understand this segment's context? Can you speak their language? | Worked in this role/industry for 3+ years | Read about it online but never lived it |
| **Access** | Can you reach them through your existing network, communities, or channels? | Already active in their communities, know people personally | Would need to cold-start from scratch |
| **Credibility** | Would they trust you as the person building their solution? Why or why not? | "Built by someone who does this job" resonates | No obvious reason they'd trust your expertise |
| **Empathy** | Is your personal experience close to theirs? | You built the product for yourself doing exactly their job | Your context is tangentially related at best |
| **Passion** | Do you care enough about this audience to spend years serving them? | Genuinely interested in their problems and success | Only interested because the market looks profitable |

**Fit assessment:**
- Strong fit (4-5 dimensions): This is your beachhead. Your experience IS the product advantage. The "built by someone who gets it" narrative writes itself.
- Moderate fit (2-3 dimensions): Viable but will require extra effort to understand, reach, and build credibility with. Consider whether you can close the gaps.
- Weak fit (0-1 dimensions): Consider whether another segment fits you better, even if this one is larger. Founder-market fit matters — pursuing a segment you don't understand leads to misaligned features and messaging.

**The "dinner test":** Would you genuinely enjoy having dinner with 10 people from this segment and talking about their work for two hours? If the answer is no, you'll burn out trying to serve them before you reach product-market fit. This matters more than people think — the average timeline to indie product sustainability is 2-3 years.

### Step 6: Community Launch Map

Identify 15-25 specific communities where your target audience is active and reachable. This becomes your distribution foundation.

**For each community, document:**

| Community | Platform | Size | Relevance | Activity Level | Rules/Norms |
|-----------|----------|------|-----------|---------------|-------------|
| [name] | Reddit/Discord/Slack/Forum/Facebook | [members] | [High/Med/Low] | [Posts/day or week] | [Self-promo rules, notable norms] |

**Categories to cover:**
1. **Primary communities** (3-5): Where target users discuss this exact problem
2. **Adjacent communities** (5-8): Where they hang out by identity, not just problem
3. **Evaluation communities** (3-5): Where they compare and recommend tools
4. **Industry communities** (3-5): Broader industry discussion where the problem surfaces
5. **Content communities** (2-3): Where they consume educational content about the domain

**For each community, note:**
- Self-promotion rules (many ban direct product mentions)
- Cultural norms (technical depth, tone, formality)
- Key influencers or frequent helpful posters
- Best post types that get engagement
- How competitors are discussed (positively, negatively, absent)

### Step 7: Segment Prioritization

If multiple segments are identified, score them using a weighted matrix:

| Criteria | Weight | Why This Weight |
|----------|--------|----------------|
| Pain severity | 3x | Mild pain doesn't convert to purchases |
| Budget availability | 3x | Pain without money = free users, not customers |
| Reachability | 2x | You need to actually find them |
| Your understanding of them | 2x | Closer to your own context = easier to serve |
| Segment size | 1x | For first 10 customers, even small segments work |

**Score each segment 1-5 per criteria, apply weights, total:**

| Criteria | Weight | Segment A | Segment B | Segment C |
|----------|--------|-----------|-----------|-----------|
| Pain severity | 3x | ?/5 | ?/5 | ?/5 |
| Budget availability | 3x | ?/5 | ?/5 | ?/5 |
| Reachability | 2x | ?/5 | ?/5 | ?/5 |
| Your understanding | 2x | ?/5 | ?/5 | ?/5 |
| Segment size | 1x | ?/5 | ?/5 | ?/5 |
| **Weighted total** | /55 | | | |

Start with ONE segment. Don't try to serve multiple at once. You can expand later.

## Output: Audience Identification Report

```markdown
## Audience Identification Report

### Primary Segment (Beachhead)

**Segment name:** [Descriptive label]
**Description:** [1-2 sentences: role, company type, key characteristic]
**Problem intensity:** X/5 — [justification from evidence]
**Current solution:** [What they use now]
**Trigger event:** [What makes them seek a solution NOW]
**Budget range:** [Estimated willingness to pay]

**Where they are:**
| Community | Platform | Size | Relevance | Activity |
|-----------|----------|------|-----------|----------|
| [list 5-8 specific communities] | | | | |

**Language patterns:**
- How they describe the problem: "[exact phrases from research]"
- How they describe desired outcome: "[exact phrases]"
- Category terms they use: "[their words, not yours]"

**Decision-stage phrases found:**
- [Specific trigger phrases observed in communities]

**Buying signals found:**
- [Specific threads/posts with evidence]

**Estimated segment size:** [Based on community sizes + search data]

### Secondary Segment(s) (if identified)
[Same template, abbreviated]

### Founder-Idea Fit
- Domain expertise: [Strong/Moderate/Weak] — [why]
- Access to audience: [Strong/Moderate/Weak] — [why]
- Credibility: [Strong/Moderate/Weak] — [why]
- Empathy with segment: [Strong/Moderate/Weak] — [why]
- Overall fit: [Strong/Moderate/Weak]

### Segment Prioritization Matrix
[Completed scoring matrix from Step 7]

### Community Launch Map
[15-25 communities organized by category]

### Recommendation
**Beachhead segment:** [Which segment and why]
**First community to engage:** [Specific community and approach]
**Key risk:** [What could make this audience choice wrong]
```

## Tools

### Required
- Web search, web fetch

### Optional (Enhanced Results)
- **Dialog Reddit Research MCP** — for deeper subreddit discovery and audience analysis. Fallback: use web search with `site:reddit.com` queries.
- **Ahrefs MCP** — `site-explorer-organic-competitors` reveals where audiences evaluate tools. Fallback: manual competitor review site analysis.

## Related Skills

- **Previous:** [demand-discovery](/skills/demand-discovery) — Provides market demand data and community evidence
- **Next:** [positioning](/skills/positioning) — Translates audience insights into messaging that resonates with the beachhead segment
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit to check whether you're selecting the audience closest to you rather than the best market opportunity
