# Famous Smoke Test Case Studies

Real-world examples of smoke tests that validated (or invalidated) demand before major investment. Study these for patterns, not just inspiration.

---

## Buffer (2010) -- The Two-Page Smoke Test

**What they did:**
- Created a landing page describing a scheduled tweeting tool that did not exist yet
- Page 1: Value proposition + "Plans and Pricing" button
- Page 2: Pricing tiers. If someone clicked a plan, they saw "You caught us before we're ready -- leave your email."
- Promoted via Twitter

**The pricing validation twist:** After validating initial demand (people clicked through to a pricing page), Joel Gascoigne added the pricing page BETWEEN the landing page and signup. People who clicked through at a specific price point = willingness-to-pay validation, not just "cool idea" validation.

**Results:** 5,000+ email signups via Twitter before writing a single line of product code.

**What it proved:** Both demand AND willingness to pay, in sequence. The two-step approach (interest, then pricing) filtered for real purchase intent.

**Key lesson:** You can validate WTP without building anything. Showing price and measuring who still clicks through is a behavioral signal worth more than any survey.

---

## Dropbox (2007) -- The Explainer Video

**What they did:**
- Created a 3-minute screencast video showing how the product would work
- Posted it to Hacker News
- Signup page captured emails

**Results:** Waitlist went from 5,000 to 75,000 overnight.

**What it proved:** Massive demand for the concept. The video demonstrated the value proposition so clearly that people signed up for something that barely worked.

**Key lesson:** For technically complex products, a demo video can be a more effective smoke test than a landing page. Showing the product solving the problem in real-time is powerful.

---

## Tesla Model 3 (2016) -- The Deposit Smoke Test

**What they did:**
- Announced the Model 3 with a $1,000 refundable deposit to reserve
- No car existed yet (just a concept and prototype)

**Results:** 325,000 reservations in the first week. $325 million in deposits.

**What it proved:** Demand at massive scale. Real money is the ultimate validation signal. The refundable deposit lowered the barrier while still filtering for genuine intent.

**Key lesson:** Even at a $1,000 price point, people will put money down for something they truly want. The deposit model works at any scale -- from $5 pre-orders to $1,000 reserves.

---

## Zynga -- The Five-Word Test

**What they did:**
- Wrote 5-word game descriptions as promotional links inside existing games
- Measured click-through rates on each concept
- Concepts with highest CTR got development budget

**Results:** Pure behavioral data at scale. No prototypes, no mockups -- just words and click rates.

**What it proved:** Which game concepts generated the most curiosity and intent from actual players. The CTR was a proxy for demand intensity.

**Key lesson:** You can test concepts with nothing more than a headline and a click. For itch products, this translates to testing different positioning angles via ad copy CTR before building landing pages.

---

## Superhuman (2015-2017) -- The Concierge Smoke Test

**What they did:**
- Manually onboarded every single user with a 30-minute video call
- 730 days of manual onboarding before any self-serve option
- Zero revenue during the concierge phase

**Results:** Eventually achieved product-market fit (40%+ on Sean Ellis test) and raised $33M Series B.

**What it proved:** The concierge approach gave them deep insight into what users actually needed. They iterated the product based on hundreds of personal conversations.

**Key lesson:** For complex products where the value is not immediately obvious, manual onboarding IS the smoke test. If people will not give you 30 minutes, they will not use the product. If they give you 30 minutes and come back, you have something.

---

## Standard Resume -- The Price Iteration Smoke Test

**What they did:**
- Started at $5/month for a resume builder
- Iteratively raised prices based on retention and feedback

**Results:** MRR grew from $440 to $2,700+ as prices increased. Conversion barely dropped.

**What it proved:** They were massively underpriced. The market perceived higher value than they were charging.

**Key lesson:** Your first price is almost certainly too low. Run the same smoke test at multiple price points. If conversion barely moves when you raise price, you have room to charge more. This is one of the most common and costly mistakes indie founders make.

---

## Concierge MVP Examples

### Wealthfront
- **Before automation:** Manually managed investment portfolios for early users
- **What it validated:** People wanted algorithmic investing, but the trust came from human interaction first
- **Transition:** Gradually replaced manual work with algorithms as patterns emerged

### Food on the Table
- **Before automation:** Founder personally planned meals and bought groceries for early users
- **What it validated:** The OUTCOME (not having to meal plan) was genuinely valued
- **Transition:** Built the app only after understanding exactly what users needed from the manual version

### Aardvark
- **Before automation:** Manually routed questions to the right people in their network
- **What it validated:** People would use a "smart friend" network for questions
- **Transition:** Built search algorithms to replace manual matching

**Pattern across all three:** They validated the OUTCOME was valuable before building the AUTOMATION. This is the essence of the concierge approach.

---

## Fake Door Test Examples

### Amazon
- Tests features by showing buttons/links in the interface for features that do not exist
- Click reveals "This feature is coming soon" or redirects
- Uses click-through rates to prioritize development roadmap

### Booking.com
- Runs thousands of fake door tests simultaneously
- Tests everything from new sort options to entire product categories
- Decisions are data-driven: if users click, it gets built

### Application to Itch Products
- If you have an existing product, use fake doors to test which EXTENSION or FEATURE to build next
- Add a menu item, button, or link for the proposed feature
- Track click rate over 1-2 weeks
- If click rate is high relative to other features, there is demand
- This tests feature demand within your existing user base, not market demand from strangers

---

## Anti-Patterns: Smoke Tests That Give False Signals

### The ProductHunt Launch Trap
- PH gives a massive traffic spike on launch day
- Traffic is primarily other builders and early adopters, not target customers
- High signup numbers from PH do not validate demand from your actual market
- **Use PH for**: awareness, backlinks, and initial burst
- **Do not use PH for**: demand validation from target customers

### The Build-in-Public Bias
- Sharing your journey on Twitter/Indie Hackers generates follows and encouragement
- Followers are other founders, not customers
- "This is awesome!" from a fellow builder is not a demand signal
- **Use BIP for**: accountability, network building, and learning
- **Do not use BIP for**: demand validation (unless your customers ARE founders)

### The Warm Traffic Trap
- Showing your landing page to friends, colleagues, and followers
- They convert at artificially high rates because they know you and want to be supportive
- Cold traffic conversion is typically 3-10x lower than warm traffic
- **Always validate with COLD traffic**: people who have never heard of you or your product
