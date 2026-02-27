# Conversion Benchmarks and False Positive Traps

Industry benchmarks for interpreting smoke test results, common false positive traps that mislead founders, and a structured decision framework for post-test action.

---

## Landing Page Conversion Benchmarks

### By Conversion Action

| Metric | Weak | Baseline | Strong | Exceptional |
|--------|------|----------|--------|-------------|
| Email capture (cold traffic) | < 1% | 2-5% | 5-10% | 10%+ |
| Free trial signup (cold traffic) | < 0.5% | 1-3% | 3-5% | 5%+ |
| Credit card trial (cold traffic) | < 0.3% | 0.5-2% | 2-3% | 3%+ |
| Pre-payment / deposit | < 0.2% | 0.5-1% | 1-3% | 3%+ |
| Demo booking (B2B) | < 1% | 2-5% | 5-10% | 10%+ |

### By Traffic Source

| Source | Typical Click-to-Signup | Notes |
|--------|------------------------|-------|
| Google Ads (search, high intent) | 3-10% | Depends on keyword intent match |
| Reddit (organic, decision-stage) | ~20% | When replying to relevant threads |
| Reddit Ads | ~5-15% | When targeting specific subreddits |
| LinkedIn Ads (B2B) | 2-5% | Higher quality leads, higher CPC |
| Product Hunt | 5-15% | Early adopter bias, not representative |
| Direct outreach | 10-30% | Highest when personalized |

### Post-Signup Conversion

| Metric | Typical | Strong |
|--------|---------|--------|
| Free trial to paid | 15-30% | 30%+ |
| Freemium to paid | 2-5% | 5-10% |
| Demo to close (B2B) | 15-25% | 25%+ |
| Waitlist to active trial | 20-40% | 40%+ |

### Page Quality Indicators

| Metric | Concerning | Acceptable | Good |
|--------|-----------|-----------|------|
| Bounce rate | > 70% | 40-70% | < 40% |
| Average time on page | < 15 sec | 15-60 sec | > 60 sec |
| Scroll depth (% past fold) | < 30% | 30-60% | > 60% |
| Form start to completion | < 50% | 50-75% | > 75% |

---

## How to Calibrate Your Specific Thresholds

### Step 1: Pick Your Primary Metric

Choose ONE primary metric based on your CTA type:
- **Email signup**: Lower friction, higher volume, weaker signal
- **Free trial**: Medium friction, good volume, solid signal
- **Credit card trial**: Higher friction, lower volume, strongest signal

### Step 2: Set Your Three Thresholds

Using benchmarks above as a guide:

```
STRONG SIGNAL: [Primary metric] > [Strong benchmark]
  -> Proceed to distribution with confidence

BASELINE: [Primary metric] between [Weak] and [Strong]
  -> Promising but needs iteration. Change ONE variable and test again.

KILL CRITERIA: [Primary metric] < [Weak benchmark] at 500+ sessions
  -> Reassess fundamentally: wrong audience? Wrong positioning? Wrong product?
```

### Step 3: Define Sample Size

Minimum viable sample sizes:
- **300 sessions**: Enough to spot strong/weak signals, not for A/B test conclusions
- **500 sessions**: Good directional data for go/no-go decisions
- **1,000+ sessions**: Required for reliable A/B test comparisons between variants
- **200+ conversions per variant**: Required before comparing A/B test winners

### Step 4: Account for Time Patterns

- Run for at least 7 days (captures weekday and weekend behavior)
- 14 days is ideal (captures two full weeks)
- Check for day-of-week patterns (B2B: weekday heavy, consumer: weekend included)
- Do not panic on day 1-2 -- early data is noisy

---

## False Positive Traps

### What Founders Mistake for Validation

**1. Friends and family enthusiasm**
- They are being nice, not validating demand
- Severity: HIGH -- this is the #1 source of false confidence
- Fix: Only count cold traffic conversions. Exclude anyone who knows you.

**2. Founder community buzz**
- r/SideProject, r/Entrepreneur, Indie Hackers -- these audiences are builders, not buyers
- They upvote cool projects, not products they would buy
- Severity: HIGH -- easy to get 50+ upvotes with zero customer potential
- Fix: Track conversions from target customer communities only

**3. Social media engagement**
- Likes, shares, and "this is awesome!" comments are not purchase intent
- Engagement metrics measure entertainment value, not commercial value
- Severity: MEDIUM -- feels like validation, but engagement does not equal revenue
- Fix: Look for behavioral signals (clicks through to pricing, signups, payments)

**4. High traffic from wrong audience**
- 10,000 visits from curious builders are worth less than 100 from target customers
- Common when HN or PH picks up your post
- Severity: MEDIUM -- impressive numbers that mean nothing
- Fix: Segment analytics by traffic source. Only evaluate target-audience cohorts.

**5. Hypothetical purchase intent**
- "Would you buy this?" is nearly worthless -- people lie to be nice (Mom Test rule)
- "I would definitely use this!" from someone who has never searched for a solution
- Severity: HIGH -- the single most dangerous false signal
- Fix: Only count actual behavioral commitments (time, money, reputation)

**6. Warm traffic conversion rates**
- People who already follow you, know you, or received a personal message convert at 3-10x cold rates
- Using warm traffic benchmarks to predict cold traffic performance leads to devastation
- Severity: HIGH -- the math looks great until you try to scale
- Fix: Test with cold traffic ONLY for demand validation

---

## Anti-Patterns in Test Design

**1. Not specifying success criteria upfront**
If you do not define what success looks like BEFORE the test, you will rationalize any result as positive. "Well, 0.5% is low, but some of those people REALLY seemed interested..." This is confirmation bias at work.

**2. Testing with warm traffic**
Already-aware audiences give unreliable conversion data. Your newsletter subscribers, Twitter followers, and colleagues are not representative of cold market demand.

**3. Over-optimizing the page before testing**
If you spend 3 weeks perfecting animations, copy, and design, you cannot tell whether a good result comes from a good product or a good landing page. Start ugly but functional. Polish after validation.

**4. Drawing conclusions too early**
50 visitors is noise, not signal. At 50 visitors, a single conversion is a 2% rate, but it could easily be 0% or 4% with a different 50 visitors. Wait for 300-500+ sessions before making decisions.

**5. Ignoring negative results**
"They just didn't understand it yet" or "The ad targeting was off" or "It was a bad week." Sometimes the answer is simply: insufficient demand. Facing that honestly saves months of wasted effort.

**6. Changing the page mid-test**
Every change resets your data. If you tweak the headline on day 4, you now have two datasets (pre-change and post-change) that cannot be combined. Pick a version and let it run for the full test duration.

**7. Multiple goals on one page**
"Sign up for the trial AND join our newsletter AND follow us on Twitter." One page, one CTA, one action. Multiple goals dilute conversion measurement.

---

## Post-Test Decision Framework

### Strong Signal Playbook

Your smoke test exceeded success criteria. What to do:

1. **Email the waitlist/signups within 24 hours**. Do not let interested people go cold. The gap between signup and first contact should be as short as possible.

2. **Start manual onboarding for first users**. High-touch, personal, hands-on. This is the Collison Installation approach -- offer to set it up for them, walk them through it, be available.

3. **Capture their exact words**. How they describe the value, what surprised them, what they wish it did. These become your testimonial copy, your FAQ, and your product roadmap.

4. **Transition to Phase 7** (distribution-plan). You have validation. Now systematically acquire your first 10 paying customers.

5. **Keep the landing page running**. It is no longer a test -- it is your acquisition funnel.

### Weak Signal Playbook

Your smoke test fell below kill criteria. Do not assume the product is wrong -- test these first:

1. **Different positioning**: Same product, reframed for a different value angle. The product may be right but the MESSAGE is wrong.

2. **Different audience**: Same product, targeted at a different segment. The product may solve a real problem for someone you have not identified yet.

3. **Different traffic source**: Your ads may be reaching the wrong people. Try a different keyword set or platform.

4. **Different price point**: Sometimes RAISING price increases conversion by signaling quality. Sometimes lowering it unlocks a price-sensitive segment.

5. **Different offer structure**: Free trial vs freemium vs demo vs consultation. The barrier type matters.

Run a SECOND test with exactly ONE changed variable before concluding "no demand." Most successful itch products needed 2-3 positioning iterations before finding resonance.

If the second test is also below kill criteria with a meaningfully different approach, seriously consider killing or pivoting. See the `go-no-go` skill.

### Mixed Signal Playbook

Results are ambiguous -- some conversion but unclear picture.

1. **Segment by traffic source**: Which specific channels produced signups? Reddit organic vs Google Ads vs direct may tell very different stories.

2. **Analyze conversion by visitor quality**: Time on page, scroll depth, pages per session. Are converters spending more time? This tells you who the real prospects are.

3. **Check qualitative signals**: Did anyone reply to your follow-up email? What did they say? A single detailed reply can be more informative than aggregate conversion numbers.

4. **Test 2-3 positioning variants**: Create separate landing pages with different headlines and value propositions. Split traffic equally. The winning variant tells you which message resonates.

5. **Look for segment patterns**: If 80% of converters share a characteristic (industry, job title, use case), you may have found a niche within your broader market. Narrow your targeting and test again.
