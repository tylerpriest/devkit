# Pricing Experiments and Validation Methods

How to validate your pricing with real behavioral data before committing, including the Van Westendorp method, A/B testing, and experiment design.

---

## The Van Westendorp Price Sensitivity Meter

### When to Use

Use Van Westendorp when you have access to 50+ potential users (ideally 100-200 per segment). This works best AFTER you have some user traction, not during initial validation. During pre-launch, use the signal methods in the main pricing-discovery skill instead.

### The Four Questions

Send a simple 4-question survey to potential or existing users:

1. **Too cheap**: At what price would [product] be so cheap you would question its quality?
2. **Bargain**: At what price would [product] be a bargain -- a great buy for the money?
3. **Getting expensive**: At what price would [product] start getting expensive, but you would still consider buying?
4. **Too expensive**: At what price would [product] be too expensive to consider?

### How to Analyze Results

Plot cumulative distribution curves for each answer:

1. **"Too cheap"** curve: cumulative % who said price is too cheap (ascending from low to high price)
2. **"Bargain"** curve: cumulative % who said price is a bargain (ascending)
3. **"Getting expensive"** curve: cumulative % who said expensive but would consider (descending)
4. **"Too expensive"** curve: cumulative % who said too expensive (descending)

**Key intersections:**
- **Optimal Price Point (OPP)**: Where "too cheap" crosses "too expensive." This is where equal numbers of people think it is too cheap vs too expensive.
- **Indifference Price Point (IDP)**: Where "bargain" crosses "getting expensive." The price where equal numbers see it as a deal vs expensive.
- **Acceptable Price Range**: The zone between the "bargain/too expensive" intersection (low end) and the "too cheap/getting expensive" intersection (high end).

**For itch products**: Price in the UPPER HALF of the acceptable range. Indie founders consistently underprice, and pricing at the upper end of what the market accepts is appropriate.

### Limitations

- People systematically lowball (state lower prices than they would actually pay)
- Does not account for features, competitive context, or brand perception
- Hypothetical -- behavioral data (actual purchases) always trumps stated preferences
- Best used as one INPUT alongside behavioral signals, not as the sole pricing decision
- Requires enough respondents to be statistically meaningful (100+ per segment ideal)

### Quick Alternative: The One-Question Version

If you cannot get 50+ survey responses, use conversations instead. The Mom Test approach:

- "How much time do you spend on this per week?" (quantifies the pain = price anchor)
- "Have you looked for solutions? What did you find?" (tests urgency + competitive awareness)
- "What's your budget for tools in this area?" (reveals real spending constraints)
- "What do you currently spend on [solving this problem]?" (anchors mental budget)

Do NOT ask "would you pay $X?" -- they will say yes to be polite. Ask about their behavior and spending, not hypothetical willingness.

---

## Landing Page Price Testing

### Experiment 1: Price Point A/B Test

The simplest and most reliable pricing experiment. Requires only a landing page and traffic.

**Setup:**
1. Create two identical landing pages with different prices
   - Version A: Lower price ($29/mo)
   - Version B: Higher price ($49/mo)
2. Drive equal cold traffic to both (Google Ads, Reddit ads)
3. Use separate URLs or split-testing tool
4. Run for 7-14 days with 200+ visitors per variant

**What to measure:**
- Signup rate per variant
- **Revenue per visitor** = signup rate x price (this is the key metric, not conversion rate alone)
- Time on page, scroll depth, bounce rate per variant

**How to interpret:**
- If Version B converts at 3% and Version A at 4%, but B generates more revenue per visitor ($1.47 vs $1.16), price higher
- If Version B conversion drops by more than 50% vs Version A, the higher price has crossed a sensitivity threshold
- If both convert similarly, the market is not price-sensitive at this range -- go with the higher price

**Common finding**: The higher price often wins on revenue. Fewer signups but higher value per customer. This surprises founders who assumed lower price = more customers = more revenue.

### Experiment 2: Price Anchoring Variations

Test how different PRESENTATIONS of the same price affect conversion:

**Variations to test:**
- "$49/month" (raw price)
- "$1.63/day" (daily framing -- feels smaller)
- "Less than your daily coffee" (comparison anchoring)
- "$49/month -- save 20 hours for less than $2.50/hour" (value framing)
- "$588/year, or $49/month" (annual anchoring makes monthly feel like a deal)
- "$49/month. Save $600+/month vs doing it manually." (ROI anchoring)

**How to test**: Create separate landing pages or use a split-test tool. Drive equal traffic to each. Measure signup conversion rate.

**What you will learn**: Which framing resonates with your audience. Value framing (showing the ROI) typically wins for B2B. Daily framing typically wins for consumer/prosumer.

### Experiment 3: Decoy Pricing Test

If you have two tiers, test adding a third "decoy" tier that makes your target tier look better.

**Setup:**
- **Without decoy**: Basic $29/mo | Pro $49/mo
- **With decoy**: Basic $29/mo | Pro $49/mo | Enterprise $149/mo

The Enterprise tier exists to make Pro look like a bargain by comparison. Measure whether adding the decoy shifts more users to Pro vs Basic.

**Alternative decoy structure:**
- Starter $29/mo (limited)
- Growth $49/mo (everything most people need) <-- target tier
- Scale $59/mo (Growth + minor extras)

The $10 gap between Growth and Scale makes Growth look like the sweet spot. The Scale tier is the decoy.

### Experiment 4: Willingness-to-Pay Ladder

Test multiple price points sequentially to find the conversion cliff:

**Setup:**
1. Week 1-2: Landing page at $29/mo, measure conversion
2. Week 3-4: Same page at $49/mo, measure conversion
3. Week 5-6: Same page at $79/mo, measure conversion
4. Week 7-8: Same page at $99/mo, measure conversion

**What to look for:**
- The point where conversion drops by more than 40% from the previous level = price ceiling
- The sweet spot is one tier below that cliff
- If conversion barely changes across all price points, you are dramatically underpricing

**Important**: Use cold traffic only. Each cohort must be fresh visitors, not returning ones. Keep traffic source, ad copy, and landing page identical -- only change the price.

---

## Pricing Page Conversion Optimization

### Elements That Increase Pricing Page Conversion

1. **Show all prices upfront**: No "Contact us" unless genuinely enterprise. Transparency builds trust.
2. **Highlight the recommended tier**: Use "Most Popular" or "Best Value" badges. Make the target tier visually prominent.
3. **Use annual toggle with savings shown**: "Save 20%" or "2 months free" next to the annual option.
4. **Feature comparison table**: Below the tier cards, show a detailed comparison. Customers want to see exactly what they get.
5. **Money-back guarantee**: "30-day money-back guarantee, no questions asked." Reduces risk.
6. **Reassurance copy**: "No long-term contracts. Cancel anytime. No hidden fees." near the CTA.
7. **Social proof near price**: "Trusted by 500+ teams" or "4.8/5 on G2" adds credibility at the decision moment.

### Elements That Kill Pricing Page Conversion

1. **Too many tiers** (4+): Creates decision paralysis. Stick to 2-3.
2. **Unclear differentiation**: If customers cannot quickly see why tier B is worth 2x tier A, simplify.
3. **Per-feature pricing**: Feels like being nickeled-and-dimed. Gate by value metric, not individual features.
4. **No free option or trial**: For indie products, some form of try-before-buy is expected.
5. **Complexity**: If the pricing page needs a calculator or explanation video, it is too complex.

---

## When to Raise Prices

### Signals That You Are Underpriced

- Customers say "this is a great deal" or "I'd pay more"
- Trial-to-paid conversion is unusually high (> 50%) -- the price barrier is too low
- Sean Ellis score is 40%+ "very disappointed" -- you have PMF, capture more value
- Competitors charge 2-3x more for inferior product
- Churn is low (< 5% monthly) -- customers clearly value the product

### How to Raise Prices

1. **Grandfather existing customers**: Keep them at their original price. New price applies to new signups only.
2. **Announce with value**: "We've added [features]. New pricing reflects [increased value]."
3. **Give notice**: 30-60 days warning if you must raise existing customer prices.
4. **Test first**: Run the new price on a cohort of new signups for 30 days before making it universal.

### Frequency

Most indie products should evaluate pricing every 6-12 months. The default should be to raise unless there is a strong reason not to. Markets and value perception evolve. Your product improves. Your price should reflect that.
