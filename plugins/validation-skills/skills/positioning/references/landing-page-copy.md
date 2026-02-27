# Landing Page Copy Architecture

Patterns and principles for writing landing page copy that converts — specifically tailored for itch products where the builder needs to translate personal experience into customer-resonant messaging.

---

## Above the Fold (Hero Section)

The hero section has roughly 5 seconds to convince a visitor to keep reading. Every element must earn its space.

### Hero Headline (H1)

**Rule:** Answer the search keyword as accurately as possible using "before state" language from VOC mining.

**Patterns that work for itch products:**

| Pattern | Template | Example |
|---------|----------|---------|
| Direct outcome | "[Desired outcome] for [specific audience]" | "Never run out of stock again" |
| Pain killer | "Stop [painful task] forever" | "Stop counting inventory by hand" |
| Replacement | "Replace your [painful thing] with [better thing]" | "Replace your inventory spreadsheet with something that works" |
| Less annoying | "[Category] that doesn't [main complaint]" | "Project management that doesn't need a project manager to set up" |
| Simple statement | "[What it does] in [simple terms]" | "Real-time inventory for small stores" |

**H1 quality checks:**
- Would someone in your beachhead segment read this and think "this is for me"?
- Does it use customer language (not builder language)?
- Is it specific enough to differentiate from competitors?
- Could you understand it in under 3 seconds?

### Subheadline (H2)

Expands on the H1 with how or why. Uses "dream state" language.

**Patterns:**
- "[Product] [how it works] so you can [outcome]"
- "[Specific benefit 1]. [Specific benefit 2]. [Specific benefit 3]."
- "For [audience] who [situation]. [What changes with your product]."

### CTA Button

**First-person language** lifts conversions approximately 20%:
- "Start my free trial" (not "Start your free trial")
- "See my dashboard" (not "See the dashboard")
- "Get my first report" (not "Get started")

**Benefit-oriented** beats action-oriented:
- "See my inventory now" beats "Sign up"
- "Get my Fridays back" beats "Start trial"
- "Fix my reports" beats "Try it free"

### Reassurance Line

Place directly near the CTA button to reduce friction:
- "No credit card required. Cancel anytime."
- "Setup takes 2 minutes."
- "Free for teams under 5."
- "Works with [tool they already use]."

---

## Benefits Section

### Feature-to-Benefit Translation

For each feature, always lead with the benefit and support with the feature:

**Structure:** "[Benefit statement]. [Feature that enables it]."

| Feature Only (Weak) | Benefit + Feature (Strong) |
|---------------------|---------------------------|
| "Automatic Salesforce sync" | "Never copy-paste between tabs again. Your data syncs automatically from Salesforce." |
| "Real-time dashboard" | "Know what's selling right now, not what sold last week. Live data, always current." |
| "Mobile app" | "Check your numbers from the shop floor. Works on your phone, no laptop needed." |
| "AI-powered reports" | "Get your Monday report without touching a spreadsheet. AI generates it from your data." |

### Specificity Principle

Specific numbers beat vague claims every time:
- "Saves time" → "Saves 4 hours every week"
- "Increases efficiency" → "Cuts report time from 4 hours to 15 minutes"
- "Affordable" → "Starts at $29/month — less than one hour of your VA's time"
- "Easy setup" → "Set up in 5 minutes with 3 clicks"

If you don't have real numbers yet, use the best estimates from your workaround analysis. "Most users save 3-5 hours per week" is better than "save time."

---

## Social Proof Section

### What Works (In Priority Order)

1. **Specific quantitative results:** "Cut reporting time from 4 hours to 15 minutes" — most persuasive
2. **Named testimonials with context:** "Name, Title, Company" + specific result — high trust
3. **Customer logos with aggregate stats:** "Trusted by 1,200+ B2B SaaS companies" — establishes scale
4. **Before/after stories:** "Before: 4 hours on reports. After: 15 minutes." — most relatable
5. **Case studies:** 3x conversion rate for visitors who engage with them — richest format

### What Doesn't Work

- Anonymous testimonials ("A happy customer says...")
- Vanity metrics without context ("10,000 downloads!")
- Testimonials that praise YOU instead of describing THEIR outcome
- Social proof from people unlike the target audience

### For Pre-Launch / Early Stage

When you don't have customers yet:
- Beta user quotes (even from 2-3 people)
- "Currently used by [specific type of user]" (even if it's 5 people)
- Founder credibility: "Built by a [role] who dealt with this for X years"
- Waitlist count: "Join X people waiting for access"
- Problem validation: "Based on research with X [audience type] who share this problem"

Never fake social proof. An honest "currently in beta with 5 users" is better than manufactured testimonials.

---

## FAQ Section

Use real questions from customer research, not invented ones.

### Essential FAQs for Itch Products

| Question | Source | Why It Matters |
|----------|--------|---------------|
| "How is this different from [competitor]?" | Competitor comparison threads | #1 question for anyone evaluating |
| "Does it integrate with [tool they use]?" | Community discussion, workflow analysis | Integration is often a dealbreaker |
| "How long does setup take?" | Setup friction from reviews | "5 minutes" is a conversion driver |
| "What happens to my data if I cancel?" | Trust concern from review mining | Reduces risk perception |
| "Is there a free plan/trial?" | Universal pricing concern | Clear answer prevents bounce |
| "Can I import from [current tool]?" | Switching cost concern | Reduces migration anxiety |
| "Is my data secure?" | Enterprise/B2B concern | Table stakes for business tools |

### FAQ Copy Rules

- Answer the actual question in the first sentence (don't dance around it)
- Keep answers 2-3 sentences maximum
- Link to detailed docs if the answer requires depth
- Use the same language the customer used when asking

---

## Message Match

The #1 conversion killer is broken message match.

**What it means:** The language in your ad/post MUST match the hero copy on your landing page. A visitor who clicked an ad expects to land on a page that continues the same conversation.

### Good Message Match

```
Keyword: "inventory management small retail"
Ad: "Stop counting inventory by hand"
Landing page H1: "Stop Counting Inventory by Hand"
CTA: "See my inventory now"
```

Every step reinforces the same message for the same person about the same problem.

### Broken Message Match

```
Keyword: "inventory management small retail"
Ad: "Stop counting inventory by hand"
Landing page H1: "AI-Powered Business Intelligence Platform"
CTA: "Get started"
```

The visitor thinks "wrong page" and bounces. The ad promised a solution to their specific problem. The landing page talks about something generic.

**Rule:** Keyword → Ad copy → Landing page hero → CTA must all speak the same language about the same problem for the same person.

---

## Design Principles for Conversion

### Speed
- **1-second load = 3x conversion** vs 5-second load
- Compress images aggressively
- Minimize scripts and third-party calls
- Test on mobile network speeds

### Mobile-First
- 50%+ of traffic is mobile
- Forms must be thumb-friendly (44x44px minimum tap targets)
- Single-column layout on mobile
- CTA visible without scrolling
- Text readable without pinching

### Focus
- Single goal per page (don't serve enterprise + solo simultaneously)
- One CTA per screen (don't compete with yourself)
- Remove navigation if possible (or minimize it)
- Every element should push toward the one conversion action

### Form Design
- Minimal fields (each unnecessary field increases abandonment)
- Email-only for initial capture (ask for more later)
- Inline validation (don't wait until submit to show errors)
- Progress indicators for multi-step forms

### Visual Hierarchy
- Bold, contrasting CTA button (don't make them search for it)
- White space around CTAs (draws the eye)
- Directional cues pointing toward the CTA
- Consistent color for all CTAs (train the eye)

---

## A/B Testing Priorities

When you have enough traffic to test, test these elements in priority order (highest impact first):

| Priority | Element | Why |
|----------|---------|-----|
| 1 | CTA text | "Submit" → "Get started free" = often 20-30% lift |
| 2 | Reassurance copy near CTA | "No credit card" reduces friction significantly |
| 3 | Form field count | Each removed field lifts completion rate |
| 4 | Hero headline | Test positioning angles from VOC research |
| 5 | Price presentation | Monthly vs annual, anchored vs standalone |
| 6 | Social proof format | Testimonial vs metric vs logo |
| 7 | Page length | Short (feature overview) vs long (full story) |

**Statistical requirements:**
- 90-95% confidence for significance
- 300-1,000 sessions per variant minimum
- Run for at least 1 full business cycle (usually 1-2 weeks)
- Don't call tests early based on initial trends

---

## Landing Page Copy Checklist

Before launch, verify:

**Hero section:**
- [ ] H1 uses customer language, not builder language
- [ ] H1 would make beachhead customer think "this is for me"
- [ ] H2 expands with specific benefit or "how"
- [ ] CTA uses first-person language
- [ ] Reassurance copy is near CTA
- [ ] Above-fold section loads in < 2 seconds

**Body:**
- [ ] Benefits lead, features support (not the other way around)
- [ ] Numbers are specific (hours, dollars, percentages)
- [ ] Social proof is real and relevant to target audience
- [ ] FAQ answers real customer questions

**Technical:**
- [ ] Mobile-friendly (tested on actual phone)
- [ ] Single conversion goal (one CTA type)
- [ ] Page loads fast (< 3 seconds on mobile)
- [ ] Analytics tracking is in place (can measure conversion rate)

**Message match:**
- [ ] Primary traffic source (ad/post) aligns with H1
- [ ] CTA matches the page's primary message
- [ ] Post-conversion page (thank you / next step) continues the conversation
