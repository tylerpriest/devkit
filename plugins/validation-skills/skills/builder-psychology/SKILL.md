---
name: builder-psychology
description: "Surface and counteract cognitive biases at every validation checkpoint. Triggers: bias check, am I being objective, reality check my thinking, builder bias audit, am I fooling myself, cognitive bias review, honest assessment, sanity check my idea"
---

# Builder Psychology

> Surface the cognitive biases that cause builders to overvalue their own products and undervalue market signals, then apply structured debiasing techniques at every decision checkpoint.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

Every builder is subject to a predictable stack of cognitive biases that distort judgment about their own product. This skill provides a structured bias audit that can be run at any point during validation -- after problem extraction, after demand discovery, after smoke testing, or whenever the builder needs an honest mirror. It replaces gut-level confidence with evidence-based assessment.

The research is clear: labor leads to love (Norton, Mochon, Ariely 2012), sunk costs distort decisions (the Concorde Effect), and confirmation bias ensures you find exactly the validation you're looking for. This skill is the antidote.

## When to Run This Skill

- **At any checkpoint.** This is a cross-cutting skill, not a phase. Run it whenever you sense decision fatigue, overconfidence, or resistance to negative signals.
- **Before major investment decisions.** Before committing significant time, money, or reputation.
- **When the builder resists negative data.** If findings from demand-discovery, smoke-test, or go-no-go feel "wrong," that feeling is often bias.
- **On request.** When the user asks for a reality check, bias audit, or honest assessment.

## Methodology

### Step 1: Identify Active Biases

Review the current validation context and conversation history. For each bias below, assess whether it is **Active** (evidence of influence), **At Risk** (conditions present), or **Clear** (no evidence).

#### The Bias Catalog

**1. IKEA Effect** (Norton, Mochon, Ariely 2012 -- Harvard/Yale/Duke)
- People place disproportionately high value on things they partially created, regardless of quality
- Labor leads to love -- the more effort invested, the higher the perceived value
- Even novices overvalue their creations relative to expert-made alternatives
- Compounds with endowment effect and loss aversion into a triple bias
- **Detection question:** "Is the builder evaluating this product as a creator or as a customer?"

**2. Sunk Cost Fallacy** (The Concorde Effect)
- Continuing to invest because of past investment, not because of future evidence
- "I've spent 6 months on this" is not a reason to continue; it's a reason to evaluate objectively
- Separate from persistence -- persistence is based on evidence, sunk cost is not
- **Detection question:** "If starting fresh today with zero investment, would they still pursue this?"

**3. Confirmation Bias**
- Searching for, interpreting, and remembering information that confirms pre-existing beliefs
- Noticing 3 positive comments and ignoring 30 bounces
- Interpreting ambiguous feedback as validation
- Seeking validation in builder communities instead of customer communities
- **Detection question:** "What disconfirming evidence has been actively sought and found?"

**4. Optimism Bias**
- Overestimating the likelihood of positive outcomes
- Underestimating time, cost, and difficulty
- Believing "my case is different" when base rates say otherwise
- **Detection question:** "What do the base rates say about products like this?"

**5. Planning Fallacy** (Kahneman & Tversky)
- Underestimating time and cost while overestimating benefits
- Even when people know about past planning failures, they still underestimate the next one
- Applies to timelines, budgets, and adoption projections
- **Detection question:** "How long did the last three similar tasks actually take vs. the estimate?"

**6. Anchoring Bias**
- Over-relying on the first piece of information encountered
- If the first customer said "I'd pay $99/mo," that anchors all subsequent pricing thinking
- First competitor found anchors positioning assumptions
- **Detection question:** "Would the conclusion change if the first data point had been different?"

**7. Survivorship Bias**
- Focusing on successes while ignoring the (much larger) pool of failures
- "Shopify started as a personal project and became a $100B company" ignores 10,000 personal projects that went nowhere
- Success stories make outcomes seem more likely and more replicable than they are
- **Detection question:** "What happened to similar products that failed? What did survivors do differently?"

**8. Availability Heuristic**
- Overweighting information that comes to mind easily (recent, vivid, emotional)
- One viral success story outweighs statistical evidence
- Recent positive conversation outweighs months of silence
- **Detection question:** "Is this judgment based on systematic evidence or memorable anecdotes?"

**9. Dunning-Kruger Effect**
- Overestimating competence in areas where knowledge is limited
- A technical founder overestimating their marketing abilities
- A first-time builder overestimating their understanding of customer needs
- **Detection question:** "What relevant experience does the builder have in the areas they're most confident about?"

**10. Status Quo Bias**
- Preference for the current state of affairs, resistance to change
- Refusing to pivot even when evidence supports it
- Defaulting to "stay the course" when data says otherwise
- **Detection question:** "If this were someone else's product, what would the data recommend?"

### Step 2: Apply the Bias Stack Analysis

These biases compound. Walk through the stack:

1. Built it (IKEA Effect -- overvalue it)
2. Invested months (Sunk Cost -- resist abandoning it)
3. It's theirs (Endowment Effect -- feels precious)
4. Looked for validation (Confirmation Bias -- found it everywhere)
5. It was hard (Effort Justification -- must be valuable)
6. Read success stories (Survivorship Bias -- believe they'll be next)

For each layer, assess: **Is there behavioral evidence or just feelings?**

### Step 3: Run the Honest Mirror

Present these questions directly to the builder and record their answers:

1. Am I building because the MARKET wants this, or because I want to build it?
2. Would I still pursue this if I hadn't already invested X months/dollars?
3. Am I avoiding sales conversations because they're uncomfortable?
4. Am I adding features to delay the moment of market truth?
5. Am I interpreting silence as "they'll come later" instead of "they're not interested"?
6. Am I spending more time in builder communities than in customer communities?
7. What would convince me this ISN'T going to work? Have I looked for that evidence?
8. If a stranger showed me this data, what would I advise them?

### Step 4: Evidence vs. Feelings Inventory

Create two columns:

**Behavioral Evidence FOR (signals from what people DO):**
- Signups, payments, engagement, referrals, repeat usage
- Time invested by users, unsolicited feedback, organic sharing
- Pre-orders, waitlist entries with specific use cases, demo bookings

**Behavioral Evidence AGAINST (signals from what people DON'T do):**
- Bounces, churn, silence, zombie leads (signed up, never returned)
- Free users who never convert, demo no-shows
- Lack of organic sharing, no inbound inquiries

Rule: Stated preferences ("I'd definitely use this!") go in neither column. Only behavioral evidence counts.

### Step 5: Pre-Commitment Framework

If the builder is about to make a significant investment decision:

1. **Write kill criteria.** Define what would prove this isn't working, before continuing.
2. **Set a time box.** "4 weeks to get 5 paying customers" -- specific, measurable, time-bound.
3. **Find an accountability partner.** Someone outside the project who will enforce the criteria.
4. **Commit to honoring the criteria** regardless of how it feels when the deadline arrives.
5. **Frame as experiment.** This is a test, not a commitment. Experiments have outcomes, not failures.

### Step 6: Distinguish Persistence from Stubbornness

Not everything is bias. Legitimate persistence signals:

- Behavioral evidence of need (not just stated interest)
- A specific segment shows strong signal even if the broad market doesn't
- Improving metrics over time (not flat or declining)
- Users who DO engage become passionate advocates
- Sean Ellis test: >30% "very disappointed" and trending upward
- You're in the "messy middle" where most founders quit prematurely

The key distinction: **persistence based on evidence** vs. **persistence based on hope.**

## Output

### Bias Audit Report

Log the following to `validation-context.md` under a `## Bias Audit` section:

```markdown
## Bias Audit — [Date]

### Active Biases Detected
- [Bias name]: [Specific evidence of influence]
- [Bias name]: [Specific evidence of influence]

### At-Risk Biases
- [Bias name]: [Why conditions are present]

### Honest Mirror Responses
[Summarize builder's answers to the 8 questions]

### Evidence Inventory
**FOR:** [List behavioral evidence]
**AGAINST:** [List behavioral evidence]
**Net assessment:** [Evidence-based conclusion]

### Pre-Commitment Criteria
- Kill criteria: [What would prove this isn't working]
- Time box: [Deadline and measurable goal]
- Accountability: [Who will enforce]

### Recommendation
[CONTINUE WITH EVIDENCE / PAUSE AND GATHER MORE DATA / CONSIDER PIVOT / REASSESS FUNDAMENTALS]
```

## Tools

### Required
- Web search, web fetch (for base rate research and comparison data)

### Optional (Enhanced Results)
- None required -- this skill is primarily analytical, applied to existing validation data

## Related Skills

- **Cross-cutting with all skills:** Run a bias audit at any checkpoint in the validation lifecycle
- **After:** [demand-discovery](/skills/demand-discovery) — Check if demand signals are being interpreted objectively
- **After:** [smoke-test](/skills/smoke-test) — Audit whether test results are being read honestly
- **Before:** [go-no-go](/skills/go-no-go) — Clear biases before making the final decision
- **Complements:** [market-sizing](/skills/market-sizing) — Verify market projections aren't inflated by optimism bias
