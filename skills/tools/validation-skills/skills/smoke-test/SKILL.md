---
name: smoke-test
description: "Design a lightweight validation experiment to test demand with cold traffic before scaling. Triggers: smoke test, fake door, landing page test, validate demand, test my idea, will people pay, conversion test, demand experiment"
---

# Smoke Test

> Design a structured validation experiment with a landing page, cold traffic, and pre-defined success criteria to test whether strangers will pay for your product.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

A smoke test answers the critical question: "Will strangers pay for this?" It separates real behavioral intent from polite encouragement by putting a landing page with visible pricing in front of cold traffic and measuring what happens. This skill designs the experiment end-to-end: landing page copy, success/failure criteria, traffic plan, budget, and timeline -- all defined BEFORE launching so the goalposts cannot move.

## Methodology

### Step 1: Choose the Right Test Type

**Type A: Landing Page Test (Default for itch products)**

Your product EXISTS. Create a landing page that sells it to cold traffic.
- Full product description using positioning from Phase 4
- Pricing visible (from Phase 5)
- CTA: "Start free trial" or "Get early access"
- Measure: visitor-to-signup conversion rate

Use Type A unless you have a specific reason not to. You already have a product -- test whether cold traffic will buy it.

**Type B: Fake Door Test (For feature extensions)**

Button or link for a feature that does not exist yet.
- Embedded in existing product or standalone page
- Click reveals "Coming soon, leave email"
- Measure: click rate on the fake door CTA
- Best for testing which FEATURE to build next, not overall demand

**Type C: Concierge MVP (For high-touch products)**

Manually deliver the product outcome to a handful of users.
- You do the work the product would automate, by hand
- Measure: would they pay? Do they come back?
- Best when delivery quality is unknown, not demand

### Step 2: Define the Hypothesis

Write a clear, testable hypothesis BEFORE designing anything:

```
"I believe [specific audience segment] will [specific action: sign up / start trial / enter payment info]
because [reason based on evidence from earlier phases].
I will test this by [method] over [timeframe] with [traffic source].
Success means [specific metric threshold]. Failure means [specific metric threshold]."
```

**Example:**
"I believe freelance designers will start a free trial because they actively complain about manual invoice tracking on r/freelance and r/graphic_design. I will test this with a landing page targeting cold Google Ads traffic over 14 days. Success means 3%+ of 500 visitors start a trial. Failure means less than 1% at 500 visitors."

### Step 3: Set Success Criteria (BEFORE Launching)

Define these numbers now. Do not adjust them after seeing results.

**Minimum viable test parameters:**
- **Duration**: 7-14 days (enough for patterns, not so long you waste time)
- **Traffic**: 300-1,000 unique sessions per variant
- **Budget**: $50-150 total for paid traffic
- **Statistical confidence**: Wait for 300+ sessions before drawing conclusions

**Set three thresholds:**

| Signal Level | What It Means | Action |
|-------------|---------------|--------|
| **Strong** (exceeds criteria) | Real demand exists | Proceed to distribution plan (Phase 7) |
| **Moderate** (meets baseline) | Promising but uncertain | Iterate positioning/messaging, test again |
| **Weak** (below kill criteria) | Insufficient demand evidence | Reassess audience, positioning, or kill |

**Conversion benchmarks** (use to calibrate your thresholds):

| Metric | Weak | Baseline | Strong |
|--------|------|----------|--------|
| Cold traffic to email signup | < 1% | 2-5% | > 10% |
| Cold traffic to free trial | < 0.5% | 1-3% | > 5% |
| Cold traffic to credit card trial | < 0.3% | 0.5-2% | > 3% |
| Reddit click to signup | < 5% | 10-20% | > 25% |
| Trial to paid (eventual) | < 10% | 25-30% | > 40% |

**Commitment ladder** (signal strength from weakest to strongest):
1. "I would definitely pay for that" -- WORTHLESS (people lie to be polite)
2. "Cool idea!" -- WORTHLESS (compliments are fool's gold)
3. Email signup -- WEAK but measurable (2-5% eventually convert)
4. Clicked CTA / fake door -- MODERATE (behavioral intent)
5. Joined waitlist with specific use case -- GOOD
6. Booked demo/call -- STRONG (time commitment)
7. Pre-paid deposit -- VERY STRONG
8. Credit card on file -- STRONGEST

### Step 4: Design the Landing Page

**Critical Elements -- Above the Fold:**

1. **H1 Headline**: From Phase 4 positioning. Answer their search keyword. Speak to their pain.
   - Pattern: "Stop [painful task]. Start [desired outcome]."
   - Must pass the "built for me" test -- reader should instantly think "this is for people like me"

2. **H2 Subheadline**: Expand on who and how.
   - Pattern: "[Product] [does what] for [who] so they can [outcome]."

3. **Hero visual**: Screenshot, demo GIF, or 60-second video
   - Videos convert well (38.6% of marketers say it is the #1 element)
   - A GIF of the product in action is even faster to consume
   - Showing the product working beats describing it every time

4. **Primary CTA**: Bold, contrasting color, first-person language
   - "Start my free trial" > "Start your free trial" (20%+ lift documented)
   - "See my dashboard" > "Sign up"
   - Must be visible without scrolling

5. **Reassurance copy**: Directly beside or below the CTA
   - "No credit card required"
   - "Cancel anytime"
   - "Set up in 2 minutes"

**Below the Fold:**

6. **Problem/Agitate section**: PAS formula from positioning
   - State the pain in customer language
   - Show consequences of not solving it

7. **Solution section**: 3-4 key benefits, each with brief explanation
   - Show, don't tell: screenshots or GIFs for each
   - Use customer language, not builder/technical language

8. **Social proof** (use what you have):
   - Even 1-2 testimonials help massively
   - Specific numbers: "Saves an average of 4 hours/week"
   - If no customers yet: "Built by a [role] who had the same problem"

9. **Pricing section**: MUST include price
   - Visible pricing filters for real intent -- this is critical
   - "Starting at $X/month" or show full tier comparison
   - Pilot framing: "Early access: $X/month (regular $Y)"

10. **FAQ section**: Use real questions from community research (Phase 3)
    - Address top 3-5 objections
    - Use customer language, not corporate speak

11. **Second CTA**: Repeat primary CTA at page bottom

**What NOT to include:**
- Navigation menu (distraction -- kills conversion)
- Multiple goals (one page, one CTA, one action)
- Technical specifications (nobody cares about your tech stack)
- Founder story as hero (save for About page)
- Generic stock photos (use real screenshots)

### Step 5: Plan the Traffic

**Tier 1: Highest Quality (Decision-Stage Intent)**

**Google Ads (Search)**
- Target decision-stage keywords from Phase 2 (buying intent)
- Keywords: "best [category] for [audience]", "[competitor] alternative", "[problem] tool"
- Budget: $50-100 for initial test
- Expected CPC: $1-5 depending on market
- Landing page MUST match ad copy (message match = higher quality score, lower CPC)

**Reddit (Organic)**
- Find threads with active seekers from Phase 3
- Reply with genuine help + soft mention of your tool
- Low-comment threads (5-15 comments) convert better than viral posts
- Cost: $0, just time
- See the `distribution-plan` skill for Reddit reply structure

**Tier 2: Medium Quality**

**Reddit Ads**
- Target specific subreddits from Phase 3
- Budget: $50-100
- Reddit click-to-signup: ~20% typical
- Creative: use community language, not marketing speak

**LinkedIn Ads** (B2B only)
- Target by job title + company size
- Budget: $100-200 (LinkedIn CPCs are higher, $5-15)
- Good for enterprise-adjacent products

**Tier 3: Use With Caution**

**ProductHunt** -- mostly other builders, not customers. Good for signal, bad for sustained growth.
**Indie Hacker communities** -- good for feedback, terrible for demand validation.

**Traffic sources to AVOID for validation:**
- Friends and family (biased -- will click anything for you)
- Your existing audience (warm traffic skews results)
- Generic display ads (low intent, high volume, meaningless conversions)

### Step 6: Set Up Tracking

Before launching, ensure:

- **UTM parameters** on all traffic sources (source, medium, campaign)
- **Conversion events** defined: page view, CTA click, form start, form complete
- **Analytics**: Plausible, Simple Analytics, or Google Analytics -- whichever is set up
- **Heatmap** (optional): Hotjar free tier shows where people click and scroll

**Message match rule**: The keyword, ad copy, and landing page headline must align. If someone searches "inventory management for small stores," the ad should say "Inventory management for small stores" and the H1 should address inventory management for small stores. Mismatch = bounce.

### Step 7: Launch and Monitor

**During the test (daily, 10 minutes):**
- Check traffic volume (on pace for 300-1,000 sessions?)
- Check conversion rate (directional only -- do not draw conclusions yet)
- Check bounce rate: > 70% means page is not matching traffic intent
- Check time on page: < 15 seconds means headline is not grabbing them
- Respond to any inbound questions or interest immediately

**Do NOT:**
- Change the page during the test (invalidates the data)
- Optimize ads before 100-200 clicks (need baseline data first)
- Draw conclusions before 300 sessions (sample size too small)
- Share with friends/followers (contaminates cold traffic)

### Step 8: Interpret Results and Decide

**If demand is strong (exceeds criteria):**
1. Email the waitlist/signups IMMEDIATELY -- do not let interested people go cold
2. Start onboarding first users manually and personally
3. Document their exact words -- these become testimonial copy
4. Proceed to Phase 7 (distribution-plan) with confidence
5. Keep the landing page running -- it is now your acquisition funnel

**If demand is weak (below kill criteria):**

Do NOT assume the product is wrong. Test these first:
1. Different headline/positioning: Same product, reframed for a different value angle
2. Different audience: Same product, targeted at a different segment
3. Different traffic source: Your ads may be hitting the wrong people
4. Different price point: Sometimes raising price increases conversion (signals quality)
5. Different offer: Free trial vs freemium vs demo vs consultation

Run a SECOND test with the changed variable before giving up. Most itch products need 2-3 positioning iterations before they find resonance.

**If demand is mixed:**
- Segment by traffic source: Which channels produced signups? Double down there.
- Analyze form completion by source: Reddit visitors vs Google Ads visitors behave differently.
- Check qualitative signals: Did anyone reply to your follow-up email? What did they say?
- Test different value propositions: Create 2-3 landing pages with different positioning, split traffic.

## Output

Deliver a **Smoke Test Blueprint** with:

```markdown
## Smoke Test Blueprint: [Product Name]

### Hypothesis
"I believe [audience] will [action] because [evidence from earlier phases]."

### Test Design
- **Test type**: Landing Page Test / Fake Door / Concierge
- **Duration**: [X] days
- **Target sessions**: [X] unique visitors
- **Budget**: $[X]

### Success Criteria (PRE-DEFINED)
- **Strong signal**: [metric] > [threshold] (proceed to distribution)
- **Baseline**: [metric] between [low]-[high] (iterate positioning, test again)
- **Kill criteria**: [metric] < [threshold] at [sessions]+ sessions (reassess or kill)

### Landing Page Copy
**H1**: [Headline from positioning]
**H2**: [Subheadline]
**CTA**: [Button text]
**Reassurance**: [Copy near CTA]
**Key benefits**: [3-4 benefits in customer language]
**Price**: $[X]/month ([framing])
**FAQ**: [Top 3-5 objections addressed]

### Traffic Plan
| Source | Type | Budget | Expected CPC | Target Sessions |
|--------|------|--------|-------------|-----------------|
| [Source] | [Paid/Organic] | $[X] | $[X] | [X] |

### Tracking Setup
- Analytics: [Tool]
- Conversion events: [List]
- UTM structure: [Template]

### Decision Framework
- If [strong]: [specific next step]
- If [baseline]: [specific iteration to test]
- If [weak]: [specific reassessment plan]

### Timeline
- Day 1: [Setup tasks]
- Day 2-3: [Launch, initial monitoring]
- Day 7: [Mid-test check]
- Day 14: [Final analysis and decision]
```

## Tools

### Required
- Web search, web fetch (for competitor landing page analysis, traffic source research)

### Optional (Enhanced Results)
- **Ahrefs MCP**: Use `keywords-explorer-overview` for keyword CPC data to plan Google Ads targeting. Use `serp-overview` to see what currently ranks for target keywords. Without Ahrefs, use Google Ads Keyword Planner (free) for keyword data.

## Related Skills

- **Previous:** [pricing-discovery](/skills/pricing-discovery) -- Price must be set before you can test it on a landing page
- **Next:** [distribution-plan](/skills/distribution-plan) -- If smoke test succeeds, move to active distribution
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) -- The #1 risk is moving goalposts after seeing results; run bias audit before interpreting

## Reference Files

Read these for detailed methodology:
- `references/smoke-test-examples.md` -- Famous smoke test case studies and what they proved
- `references/conversion-benchmarks.md` -- Industry benchmarks, false positive traps, and post-test decision framework
