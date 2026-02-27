# Pricing Models and Psychology

Detailed reference for pricing model selection, pricing psychology principles, and common mistakes that kill indie products.

---

## Pricing Models

### Flat Rate

- **How it works**: One price for everyone, all features included
- **Best for**: Solo tools, simple utilities, early-stage products
- **Advantage**: Simplest to understand, sell, and implement. Zero decision paralysis for the buyer.
- **Risk**: Leaving money on the table from high-value users who would pay more
- **Example**: Basecamp's flat $99/month for unlimited users

**When to choose flat rate:**
- You are pre-PMF and want to minimize purchase friction
- Your product delivers similar value regardless of team size
- You want to avoid the complexity of metered billing early on

### Per-Seat / Per-User

- **How it works**: Price scales with number of users on the account
- **Best for**: Collaboration tools, team software, project management
- **Advantage**: Natural expansion revenue as teams grow. Revenue scales with value delivered.
- **Risk**: Incentivizes workarounds (shared logins, fewer seats than actual users)
- **Example**: Slack, Notion, most B2B SaaS

**When to choose per-seat:**
- Value genuinely increases with more users (collaboration, shared data)
- You are targeting teams, not individuals
- Your product has per-user data isolation or personalization

### Usage-Based

- **How it works**: Pay for what you use (API calls, storage, transactions, records)
- **Best for**: Infrastructure, APIs, developer tools, data processing
- **Advantage**: Perfect alignment between cost and value. Low barrier to start.
- **Risk**: Unpredictable revenue for you, surprise bills for customers. Hard to forecast.
- **Example**: AWS, Twilio, Stripe per-transaction fees

**When to choose usage-based:**
- Value directly correlates with consumption volume
- Customers have highly variable usage patterns
- You want to minimize adoption friction (start free/cheap, scale with use)

### Tiered (Good / Better / Best)

- **How it works**: 3-4 tiers with increasing features, limits, or support levels
- **Best for**: Products with clear feature differentiation and multiple customer segments
- **Advantage**: Captures different willingness-to-pay levels across segments
- **Risk**: Complexity. Customers stuck between tiers. Decision paralysis.
- **Example**: Most SaaS products eventually evolve to this model

**Tier design principles:**
- **Low tier**: Exists to make the middle tier look reasonable. Limited but functional.
- **Middle tier**: Where you want 60-70% of customers. Price it 2-3x the low tier.
- **High tier**: Exists to make the middle tier look like a bargain. Price it 3-5x the middle tier.
- Feature gates should reflect VALUE differences, not arbitrary limitations

**When to choose tiered:**
- You have distinct customer segments with different needs
- Some features are clearly more valuable to power users
- You have 50+ customers and understand which features drive upgrades

### Freemium

- **How it works**: Free tier with limited features, paid upgrade for full access
- **Best for**: Products with network effects, low marginal cost per user, viral mechanics
- **Advantage**: Maximum distribution. Users experience value before paying.
- **Risk**: Free users cost money to serve. Conversion rates are typically 2-5%.
- **Conversion benchmarks**: Totango study found no-credit-card-required outperformed for 90-day retention

**The critical freemium mistake**: Making the free tier too good. Free should create DESIRE for paid, not satisfy the need. Free = demonstrates value. Paid = delivers full value.

**When to choose freemium:**
- Product has built-in viral mechanics (sharing, collaboration, "powered by" watermarks)
- Marginal cost per free user is near zero
- Free users generate data, content, or network effects that improve the paid product

### Free Trial

- **How it works**: Full product access for a limited time (7, 14, or 30 days)
- **Best for**: Products where value takes time to realize, complex setup required
- **Credit card upfront**: Higher quality leads, lower signup volume, higher trial-to-paid rate
- **No credit card**: More signups, needs strong onboarding to convert, lower trial-to-paid rate
- **Trial length guidance**: 7 days for simple tools, 14 days standard, 30 days for complex products

### Per-Outcome

- **How it works**: Price tied to the result delivered (per sale generated, per lead captured, per hour saved)
- **Best for**: Products where value is directly measurable and attributable
- **Advantage**: Perfect alignment with customer value. Easy ROI justification.
- **Risk**: Hard to measure attribution. Revenue unpredictable. Customer may dispute results.
- **Example**: Affiliate marketing platforms, performance-based ad networks

---

## Pricing Psychology

### Anchoring

The first price a customer sees sets their reference point. Show the most expensive option first. This makes the middle option feel reasonable.

**Why "Enterprise: Contact Us" exists**: It anchors the perceived price ceiling. Even if nobody buys Enterprise, it makes the $99/month Pro plan feel affordable.

**Application**: On pricing pages, show tiers from high to low (right to left or top to bottom). The expensive option sets the anchor.

### Decoy Effect

Add a third option that makes the target option look like the best deal.

**Classic example:**
- Small: $5 (basic)
- Medium: $10 (standard) -- nobody picks this
- Large: $11 (everything)

Medium exists solely to make Large look like incredible value. The $1 difference between Medium and Large makes the upgrade feel like a no-brainer.

**For indie products**: If you have a Basic ($29) and Pro ($49), consider adding Premium ($149) that includes white-glove onboarding. The Premium exists to make Pro look reasonable.

### Charm Pricing

Price endings affect perception:
- **$49 vs $50**: The left digit changes (4 vs 5), creating a "significantly cheaper" feeling
- **$99 vs $100**: Crossing the $100 threshold matters psychologically
- **$9.99 vs $10**: Works for consumer products, less important for B2B SaaS

**For SaaS**: Use $X9 pricing ($29, $49, $99). The effect is real but subtle. Don't overthink it.

### Value Framing

How you present the price changes perception more than the price itself:

- **Daily framing**: "$49/month" becomes "less than $1.70/day" or "less than your daily coffee"
- **ROI framing**: "$49/month to save 20 hours/month = $2.45/hour saved"
- **Comparison framing**: "Replace your $5,000/month agency for $49/month"
- **Payback framing**: "Pays for itself in the first week"

**For itch products**: ROI framing is most powerful because you can quantify time/money saved from the cost-of-alternative calculation.

### Annual Discount Psychology

- Standard discount: 15-20% for annual billing
- Frame as "2 months free" (more compelling than "17% off")
- Benefits you: reduces churn, improves cash flow, signals customer commitment
- Benefits them: lower effective monthly cost, budget certainty
- During validation, default to monthly display (lower commitment = more signups = faster signal)

### Loss Aversion

People feel losses ~2x more intensely than equivalent gains. Use this ethically:
- "Stop losing $600/month to manual processes" > "Save $600/month"
- "Don't let another week of [pain] go by" > "Start saving time today"
- Free trial ending: "Your data and settings will be saved" reduces cancellation anxiety

---

## Common Pricing Mistakes

### Mistake 1: Racing to the Bottom

"I'll win on price." You will not. Competing on price is a race you will always lose against funded competitors who can afford to run at a loss for years. Compete on value, specificity, niche focus, or experience instead.

**Exception**: If you have a genuine structural cost advantage (e.g., AI replacing manual labor), lower pricing can be a differentiator. But it must be sustainable.

### Mistake 2: Pricing Based on Build Cost

"It costs me $20/mo to run, so I'll charge $30." Your infrastructure costs are irrelevant to the customer. They are paying for VALUE delivered, not servers consumed. If your tool saves someone $800/month, charging $80/month is appropriate even if it costs you $5 to serve them.

### Mistake 3: Free Tier That Is Too Generous

If your free tier solves the core problem well enough, nobody upgrades. The free tier should create desire for paid, not satisfy it.

**The test**: Would a free user's core problem remain unsolved? If yes, good free tier design. If no, you are giving away too much.

### Mistake 4: Hiding the Price

"Contact us for pricing" or no pricing page is a trust killer for indie products. Only enterprise products with genuinely variable pricing can get away with hidden pricing. Your audience wants to see a number. Show them one.

### Mistake 5: Never Raising Prices

Standard Resume went from $5/mo to significantly higher and saw MRR grow. Most indie products should raise prices every 6-12 months as they add value. Grandfather existing customers at their original price, apply new pricing to new signups.

**Signal to raise prices**: When customers say "this is a great deal" or "I'd pay more for this." You are leaving money on the table.

### Mistake 6: Charging Per Feature Instead of Per Value

Don't gate features arbitrarily. Gate based on the VALUE METRIC:
- Value scales with usage -> charge for usage
- Value scales with team size -> charge per seat
- Value is the same regardless -> charge flat

Arbitrarily locking features behind tiers frustrates users and creates a perception of being nickeled-and-dimed.

---

## The Builder's Pricing Trap

Builders systematically underprice because:

1. **They know how "simple" the code is**: Customers do not care about code complexity. They care about outcomes.
2. **Impostor syndrome**: "Who am I to charge $X?" You are the person who solved the problem. That is who.
3. **Fear of rejection**: A low price feels less scary to ask for. But a too-low price also signals low value.
4. **Builder cost fallacy**: Pricing based on what it cost to build, not value delivered
5. **Self-anchoring**: Anchoring to your OWN willingness to pay, which as a technical person is typically lower than your target customer's

**The fix**: Price based on VALUE DELIVERED, not effort invested. If your tool saves someone 10 hours/week, that is $2,000+/month in value at most professional hourly rates. Charging $49/month for that is not overcharging -- it is a 40:1 value ratio that makes the purchase decision trivial.
