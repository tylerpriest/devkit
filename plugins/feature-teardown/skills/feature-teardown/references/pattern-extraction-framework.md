# Pattern Extraction Framework

Structured methodology for synthesizing individual competitor teardowns into cross-implementation patterns, scoring innovations, and producing actionable build recommendations. This reference supports Step 6 (Cross-Implementation Pattern Extraction) of the feature-teardown skill.

---

## Purpose

Individual teardowns are useful. Cross-implementation synthesis is where the real insight lives. This framework takes N competitor analyses and produces:
1. A convergence/divergence matrix showing where implementations agree and differ
2. An innovation score for novel approaches
3. Anti-pattern identification backed by user evidence
4. A "steal this" assessment of what's adoptable
5. A prioritized build recommendation using MoSCoW with evidence

---

## Step 1: Convergence / Divergence Matrix

Map every significant design decision across all analyzed competitors to identify where implementations converge (table stakes) and diverge (choice points).

### How to Build the Matrix

1. List every significant design decision from your teardowns (UX and technical)
2. For each decision, record what each competitor chose
3. Classify each decision as convergent, divergent, or unique

### Classification Rules

| Category | Definition | Threshold |
|----------|-----------|-----------|
| **Convergent** | Most implementations make the same choice | 70%+ of competitors (e.g., 5 of 7) |
| **Divergent** | Implementations split between 2-3 valid approaches | No single approach has 70%+ adoption |
| **Unique** | Only one competitor does this | 1 of N competitors |
| **Gap** | No competitor addresses this decision point | 0 of N competitors |

### Matrix Template

```markdown
## Convergence / Divergence Matrix

### UX Decisions
| Decision Point | [Prod A] | [Prod B] | [Prod C] | [Prod N] | Classification |
|---------------|---------|---------|---------|---------|---------------|
| Entry point location | | | | | Convergent / Divergent |
| Interaction pattern | | | | | |
| Default behavior | | | | | |
| Onboarding approach | | | | | |
| Error handling style | | | | | |
| Undo mechanism | | | | | |
| Mobile approach | | | | | |

### Technical Decisions
| Decision Point | [Prod A] | [Prod B] | [Prod C] | [Prod N] | Classification |
|---------------|---------|---------|---------|---------|---------------|
| API design style | | | | | |
| Data model approach | | | | | |
| Real-time strategy | | | | | |
| Scale pattern | | | | | |
```

### Interpreting the Matrix

| Classification | What It Means for Your Build |
|---------------|----------------------------|
| **Convergent** | Table stakes. Users expect this. Deviating needs strong justification. |
| **Divergent** | Choice point. Pick the approach that aligns with YOUR audience. |
| **Unique** | Potential innovation OR product-specific quirk. Evaluate carefully. |
| **Gap** | Opportunity if there's user need, or non-issue if nobody cares. |

---

## Step 2: Innovation Scoring

Not all differences are innovations. Score unique and divergent approaches to separate genuine innovations from product-specific quirks.

### Innovation Spectrum

Rate each unique or divergent approach on a 4-level spectrum:

| Level | Label | Definition | Example |
|-------|-------|-----------|---------|
| 1 | **Convention** | Standard industry approach, well-understood | Modal dialog for settings |
| 2 | **Variation** | Recognizable pattern with a meaningful twist | Side panel instead of modal, keeping context visible |
| 3 | **Innovation** | Novel approach that solves a real user problem differently | AI-suggested defaults based on usage patterns |
| 4 | **Invention** | Entirely new interaction paradigm | Gesture-based configuration with no traditional UI |

### Innovation Evaluation Criteria

For each approach rated 2+, evaluate:

| Criterion | Question | Score 1-5 |
|-----------|----------|-----------|
| **User value** | Does this measurably improve the user experience? | |
| **Evidence** | Is there evidence users prefer this? (Reviews, adoption, praise) | |
| **Adoptability** | Can this approach work outside its original product context? | |
| **Complexity** | How much does this add to implementation complexity? | |
| **Durability** | Is this a lasting improvement or a trend/gimmick? | |

**Total score ranges:**
- 20-25: Strong innovation. Seriously consider adopting.
- 14-19: Worth evaluating. May be good for your specific context.
- 8-13: Situational. Only adopt if it aligns with your differentiation strategy.
- 5-7: Likely product-specific. Probably not worth the complexity.

### Innovation Scoring Template

```markdown
## Innovation Scores

| Approach | Product | Spectrum Level | User Value | Evidence | Adoptability | Complexity | Durability | Total |
|----------|---------|---------------|-----------|----------|-------------|-----------|-----------|-------|
| | | /4 | /5 | /5 | /5 | /5 | /5 | /25 |
```

---

## Step 3: Anti-Pattern Detection

Anti-patterns are design decisions that consistently produce negative outcomes. Identifying them is as valuable as identifying best practices — knowing what NOT to do saves time and prevents user frustration.

### How to Identify Anti-Patterns

An anti-pattern requires two things:
1. **A design decision** observed in one or more competitors
2. **Evidence of negative outcome** from user feedback, reviews, or your own teardown observation

Without evidence of harm, it's just a different approach, not an anti-pattern.

### Common Feature Anti-Pattern Categories

| Category | Anti-Pattern | Evidence Sources |
|----------|-------------|-----------------|
| **Complexity** | Exposing every option to every user (settings overload) | Reviews mentioning "overwhelming", "confusing" |
| **Discoverability** | Burying the feature in deep navigation | Support threads asking "where is X?" |
| **Defaults** | No defaults, forcing users to configure everything before first value | High drop-off rates, "complicated setup" complaints |
| **Feedback** | Silent failures — action completes (or fails) with no indication | Bug reports that are actually feedback gaps |
| **Consistency** | Feature works differently than similar features in same product | User confusion, "I expected it to work like..." |
| **Performance** | Feature loads slowly or blocks the UI during operations | "Slow", "laggy", "freezes" in reviews |
| **Mobile** | Desktop feature crammed into mobile without adaptation | Mobile-specific negative reviews |
| **Undo** | Destructive actions with no undo or confirmation | "I accidentally deleted..." threads |
| **Onboarding** | No guidance for first-time use, blank slate with no direction | "How do I..." support tickets and threads |
| **Error recovery** | Error messages that don't explain how to fix the problem | Support volume, user frustration |

### Anti-Pattern Evidence Template

```markdown
## Anti-Pattern: [Name]

**Observed in:** [Product(s)]
**The decision:** [What they did]
**The negative outcome:** [What went wrong]
**Evidence:**
- [Source 1: quote or observation]
- [Source 2: quote or observation]
**Severity:** [High — causes user churn / Medium — causes frustration / Low — minor annoyance]
**How to avoid:** [Alternative approach]
```

### Anti-Pattern Confidence

| Evidence Level | Confidence | Action |
|---------------|-----------|--------|
| Multiple reviews + your observation | High | Definitely avoid |
| Community threads about the issue | Medium-High | Avoid unless you have a mitigation |
| Your observation only, no user evidence | Medium | Note it, but it might be acceptable to users |
| Theoretical concern, no evidence | Low | Don't flag as anti-pattern — it's just an opinion |

---

## Step 4: "Steal This" Framework

Competitive intelligence should inform your build. But not everything is appropriate to adopt. This framework distinguishes between what's fair game and what's not.

### What You CAN Adopt

| Category | Examples | Why It's Fair Game |
|----------|---------|-------------------|
| **Interaction patterns** | Wizard flow, inline editing, side panel | Patterns are not owned; they're shared conventions |
| **Information architecture** | Tab structure, grouping, hierarchy | Organizational approaches are common knowledge |
| **UX heuristics** | Progressive disclosure, smart defaults, undo windows | These are usability principles, not IP |
| **Feature scope decisions** | What to include in v1 vs. v2 | Strategy informed by market research |
| **Technical approaches** | API design patterns, data model shapes, architecture choices | Engineering patterns are shared knowledge |
| **Micro-copy patterns** | Error message structure, CTA patterns | Tone and structure, not specific wording |

### What You Should NOT Copy

| Category | Examples | Why Not |
|----------|---------|--------|
| **Visual design** | Color schemes, typography, illustrations, layout specifics | Copyright, trademark, design IP |
| **Specific copy/brand voice** | Exact wording, taglines, branded terminology | Copyright, brand identity |
| **Proprietary algorithms** | Specific recommendation logic, ranking formulas | Trade secrets, potentially patented |
| **Code** | Actual source code from closed-source products | Copyright, license violations |
| **Branding elements** | Icons, logos, mascots, brand-specific UI elements | Trademark |

### "Steal This" Assessment Template

For each idea worth adopting:

```markdown
## Steal This: [Idea Name]

**Source product:** [Product]
**What to adopt:** [The pattern, approach, or concept]
**What NOT to copy:** [The specific implementation details to avoid]
**Adaptation needed:** [How to make it your own]
**Expected benefit:** [Why this improves your implementation]
**Implementation effort:** [Low / Medium / High]
```

---

## Step 5: Build Priority Matrix (MoSCoW with Evidence)

Combine all findings into a prioritized build plan. Every priority must be backed by evidence from the teardown, not gut feel.

### MoSCoW Framework

| Priority | Definition | Evidence Required |
|----------|-----------|------------------|
| **Must Have** | Without this, the feature feels broken or incomplete | Convergent pattern (70%+ of competitors) OR user expectation evidence |
| **Should Have** | Missing this generates "why doesn't it do X?" feedback | Present in 40-70% of competitors AND positive user feedback |
| **Could Have** | Nice-to-have that differentiates but isn't expected | Innovation with evidence of user value (score 14+) |
| **Won't Have (this version)** | Explicitly out of scope for v1 | Complex to build AND no evidence of user urgency |

### Building the Priority Matrix

For each potential feature element from your teardown:

```markdown
## Build Priority Matrix

### Must Have
| Element | Evidence | Source |
|---------|---------|--------|
| [Feature element] | [Why it's must-have] | [Convergent in 5/7 products + user expectation] |

### Should Have
| Element | Evidence | Source |
|---------|---------|--------|
| [Feature element] | [Why it's should-have] | [Present in 3/7 products + positive reviews] |

### Could Have (Differentiation)
| Element | Evidence | Source |
|---------|---------|--------|
| [Feature element] | [Why it could differentiate] | [Innovation score X/25 from Product Y] |

### Won't Have (v1)
| Element | Why Not Now | Revisit When |
|---------|-----------|-------------|
| [Feature element] | [Complexity vs. evidence] | [Trigger for reconsideration] |
```

### Evidence Quality for Prioritization

| Evidence Type | Strength for Must-Have | Strength for Should-Have |
|--------------|----------------------|------------------------|
| Universal across competitors (convergent) | Strong | N/A — it's must-have |
| Majority of competitors + user praise | Strong | Strong |
| Some competitors + no user complaints about absence | Medium | Strong |
| Single competitor + high innovation score | Weak | Medium |
| Your own preference with no market evidence | Do not use | Do not use |

---

## Synthesis Output Template

Combine all framework outputs into a single synthesis section:

```markdown
## Cross-Implementation Synthesis

### Pattern Summary
- **Convergent patterns identified:** [N] (these are your must-haves)
- **Divergent choice points:** [N] (these require decisions)
- **Innovations scored:** [N] (these are differentiation candidates)
- **Anti-patterns flagged:** [N] (these are your avoid list)

### Key Insight
[One paragraph: the single most important finding from cross-implementation analysis. What does looking across all competitors reveal that looking at any one alone would miss?]

### Build Strategy
[2-3 sentences: Based on the analysis, what's the recommended approach? Lead with must-haves from convergent patterns, differentiate through the highest-scored innovation, and avoid the flagged anti-patterns.]
```
