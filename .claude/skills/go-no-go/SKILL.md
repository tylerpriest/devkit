---
name: go-no-go
description: "Make a structured GO/PIVOT/KILL decision with weighted scoring, evidence synthesis, and risk assessment across all validation dimensions. Triggers: go or no go, should I continue, kill or pivot, is this worth pursuing, final decision, validation verdict, score my idea, assess viability"
---

# Go / No-Go Decision

> Synthesize all validation evidence into a weighted score (0-100), produce a definitive GO/PIVOT/KILL verdict, and outline concrete next steps -- ending the analysis phase with a clear decision.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

This skill should be run AFTER completing earlier phases (especially demand discovery, positioning, pricing, smoke test, and distribution). It can also be used as a standalone checkpoint at any point when the founder needs a reality check.

## Purpose

This is the final phase of the validation process. It exists because founders systematically avoid making clear kill/continue decisions due to sunk cost fallacy, IKEA effect (overvaluing what you built), and ambiguity aversion. This skill replaces emotional attachment with a structured, evidence-weighted scoring system that produces a definitive verdict. The goal is not to be encouraging or discouraging -- it is to be accurate.

## Methodology

### Step 1: Gather Evidence Across All Dimensions

Before scoring, compile evidence from each validation phase. For each dimension, note what is KNOWN (evidence-based) vs ASSUMED (hypothetical).

**Dimension 1: Problem Severity**
- From Phase 1 (Problem Extraction):
  - Is the problem hair-on-fire, moderate, or mild?
  - How many people actively search for solutions?
  - Are people paying for workarounds already?
  - Early Adopter criteria met (have problem, know it, have budget, cobbled a workaround)?

**Dimension 2: Demand Evidence**
- From Phase 2 (Demand Discovery):
  - Search volume for problem keywords
  - CPC (commercial intent indicator)
  - Community discussions: volume, recency, intensity
  - Trend direction (growing, stable, declining)

**Dimension 3: Competitive Gap**
- From Phase 2 and Phase 4:
  - Number of direct competitors
  - Quality of existing solutions (reviews, complaints)
  - Your differentiation (clear, weak, or nonexistent)
  - Feature/experience gaps you fill

**Dimension 4: Audience Clarity**
- From Phase 3 (Audience Identification):
  - Can you describe the ideal customer specifically (not "everyone")?
  - Do you know WHERE they congregate?
  - Do you have evidence they match your problem hypothesis?
  - Segment size estimate

**Dimension 5: Positioning Resonance**
- From Phase 4 (Positioning):
  - Does the H1 pass the "built for me" test?
  - VOC language alignment (using their words vs your words)
  - Smoke test headline performance (if tested)

**Dimension 6: Pricing Viability**
- From Phase 5 (Pricing Discovery):
  - Is the price defensible (competitor-anchored, value-justified)?
  - Do unit economics work (LTV:CAC >= 3:1, payback < 12 months)?
  - Breakeven feasible at realistic customer counts?
  - Price sensitivity signals from reviews/conversations

**Dimension 7: Demand Validation**
- From Phase 6 (Smoke Test):
  - Landing page conversion rate vs benchmarks
  - Traffic source quality (cold vs warm)
  - Commitment level of converters (email, trial, payment)
  - Any pre-payments or deposits?

**Dimension 8: Distribution Feasibility**
- From Phase 7 (Distribution Plan):
  - Can you reach target customers without paid ads?
  - Are there active communities where they discuss the problem?
  - Outreach response rates from 30-day plan
  - Built-in virality mechanics (or lack thereof)

**Dimension 9: Founder-Market Fit**
- Cross-cutting assessment:
  - Do you personally experience the problem?
  - Do you have domain expertise or credibility?
  - Are you willing to do 30-45 min/day of distribution for 6+ months?
  - Is this the kind of product you can iterate on for years?

**Dimension 10: Risk Assessment**
- Identify specific risks across categories:
  - **Market risk**: Market too small, timing wrong, declining demand
  - **Execution risk**: Technical complexity, team gaps, time constraints
  - **Competitive risk**: Well-funded incumbents, low switching costs, platform risk
  - **Financial risk**: High CAC, low margins, long payback period
  - **Technology risk**: Dependence on third-party APIs, scaling challenges
  - **Regulatory risk**: Compliance requirements, data handling, industry regulations

### Step 2: Score Each Dimension

Use the weighted scoring matrix. Score each dimension 1-5, then multiply by its weight.

| # | Dimension | Weight | Score (1-5) | Weighted |
|---|-----------|--------|-------------|----------|
| 1 | Problem Severity | 15% | ___ | ___ |
| 2 | Demand Evidence | 15% | ___ | ___ |
| 3 | Competitive Gap | 10% | ___ | ___ |
| 4 | Audience Clarity | 10% | ___ | ___ |
| 5 | Positioning Resonance | 5% | ___ | ___ |
| 6 | Pricing Viability | 10% | ___ | ___ |
| 7 | Demand Validation (Smoke Test) | 15% | ___ | ___ |
| 8 | Distribution Feasibility | 10% | ___ | ___ |
| 9 | Founder-Market Fit | 5% | ___ | ___ |
| 10 | Risk Profile (inverted) | 5% | ___ | ___ |
| | **TOTAL** | **100%** | | **___/100** |

See `references/scoring-matrix.md` for detailed rubrics for each score level.

**Scoring guidelines:**
- **1 = No evidence / Red flag**: No data found, or evidence directly contradicts viability
- **2 = Weak**: Some signal but insufficient or concerning
- **3 = Moderate**: Baseline evidence exists, neither strong nor weak
- **4 = Strong**: Clear positive evidence, minor gaps
- **5 = Exceptional**: Overwhelming evidence, multiple confirming signals

**For Risk Profile (Dimension 10):** Score is inverted. 5 = low risk (few/manageable risks), 1 = high risk (multiple critical risks).

### Step 3: Determine Verdict

| Score Range | Verdict | Meaning |
|------------|---------|---------|
| 75-100 | **GO** | Strong evidence across dimensions. Proceed to active growth. Focus on scaling distribution and iterating on product. |
| 55-74 | **CONDITIONAL GO** | Promising but gaps exist. Identify the 1-2 lowest-scoring dimensions and address them before scaling. Safe to continue building with awareness of risks. |
| 40-54 | **PIVOT** | Core product or audience needs fundamental change. Evidence suggests value exists but current approach is not connecting. Change target audience, positioning, pricing, or core feature set. |
| Below 40 | **KILL** | Insufficient evidence of viability. Either abandon or accept this is a personal tool, not a business. Killing is not failure -- it is wisdom. |

**Calibration note:** Research on AI validation tools shows the average score across all assessed ideas is approximately 67/100, and only about 7% of validated ideas result in the founder taking action. Most ideas land in the "Conditional Go" range. This is expected -- truly strong signals are rare, and most products require iteration to reach GO status.

### Step 4: Apply Kill/Pivot/Persist Heuristics

Beyond the score, check these pattern-based heuristics:

**Kill signals (any 2+ of these warrants serious reconsideration):**
- Zero search demand AND zero community evidence of the problem
- Smoke test conversion < 1% at 500+ cold sessions after 2+ positioning tests
- Every customer conversation reveals a DIFFERENT problem (no pattern convergence)
- No one has completed a single transaction (trial, demo, payment) after 30 days of effort
- The only people excited are other founders (not target customers)
- You cannot describe your ideal customer in specific terms after completing all phases

**Pivot signals (the product may be right, but the approach is wrong):**
- Users use the product differently than you intended
- A side feature gets more attention than the core product
- The "wrong" audience loves it while the target audience is indifferent
- Demos go well but deals stall (positioning/pricing problem, not demand problem)
- One specific segment retains dramatically better than others

**Persist signals (stay the course even when progress feels slow):**
- Early signals are positive but growth is slow (3-year average to indie full-time is normal)
- One segment genuinely loves it, even if the broad market does not
- Sean Ellis test: 40%+ "very disappointed" from even a small sample
- Organic referrals happening without prompting
- Users are doing Collison-like behavior (setting it up for colleagues without being asked)

### Step 5: Market Attractiveness Assessment

Calculate a market attractiveness score as a secondary check:

**Growth rate component (30 points max):**
- Market growing > 15% CAGR: 30 points
- Market growing 5-15%: 20 points
- Market growing < 5%: 10 points
- Market declining: 0 points

**Market size component (30 points max):**
- TAM > $10B: 30 points
- TAM $1B-10B: 20 points
- TAM < $1B: 10 points

**Competition component (20 points max):**
- Low competition (few players, clear gaps): 20 points
- Medium competition (several players, differentiation possible): 10 points
- High competition (dominated by well-funded incumbents): 5 points

**Market maturity component (20 points max):**
- Emerging market: 20 points
- Growing market: 15 points
- Mature market: 5 points

**Market attractiveness score = sum of components (0-100)**

This score supplements the primary weighted scoring matrix. A high market attractiveness score with a low validation score suggests the MARKET is right but your APPROACH needs work.

### Step 6: Synthesize the Decision

For the final verdict, consider:

1. **The weighted score** (primary signal)
2. **Kill/pivot/persist heuristics** (pattern check)
3. **Market attractiveness** (secondary signal)
4. **Founder conviction** (important but must be checked against evidence)

If the score says PIVOT but the founder has strong conviction, the recommendation should be: "Your conviction is noted. Here is what the evidence shows. Test [specific hypothesis] within [timeframe] to reconcile the gap. If [specific metric] does not improve, revisit the decision."

Never tell a founder to "just follow your gut." The entire point of this skill is to replace gut feelings with evidence.

## Output

Deliver a **Go/No-Go Decision Report**:

```markdown
## Go/No-Go Decision Report: [Product Name]

### Verdict: [GO / CONDITIONAL GO / PIVOT / KILL]
### Weighted Score: [X]/100

[2-3 sentence summary explaining the verdict and the primary factors driving it]

### Scoring Breakdown

| # | Dimension | Weight | Score | Weighted | Key Evidence |
|---|-----------|--------|-------|----------|-------------|
| 1 | Problem Severity | 15% | X/5 | X.X | [1-sentence summary] |
| 2 | Demand Evidence | 15% | X/5 | X.X | [1-sentence summary] |
| 3 | Competitive Gap | 10% | X/5 | X.X | [1-sentence summary] |
| 4 | Audience Clarity | 10% | X/5 | X.X | [1-sentence summary] |
| 5 | Positioning Resonance | 5% | X/5 | X.X | [1-sentence summary] |
| 6 | Pricing Viability | 10% | X/5 | X.X | [1-sentence summary] |
| 7 | Demand Validation | 15% | X/5 | X.X | [1-sentence summary] |
| 8 | Distribution Feasibility | 10% | X/5 | X.X | [1-sentence summary] |
| 9 | Founder-Market Fit | 5% | X/5 | X.X | [1-sentence summary] |
| 10 | Risk Profile | 5% | X/5 | X.X | [1-sentence summary] |
| | **TOTAL** | **100%** | | **X.X/100** | |

### Strongest Dimensions
- [Dimension]: [Why it scored high, specific evidence]
- [Dimension]: [Why it scored high, specific evidence]

### Weakest Dimensions (Action Required)
- [Dimension]: [Why it scored low, what would improve it]
- [Dimension]: [Why it scored low, what would improve it]

### Market Attractiveness: [X]/100
- Growth: [X]/30
- Size: [X]/30
- Competition: [X]/20
- Maturity: [X]/20

### Risk Summary
| Risk Category | Level | Specific Risk | Mitigation |
|--------------|-------|---------------|------------|
| Market | [H/M/L] | [Description] | [Action] |
| Execution | [H/M/L] | [Description] | [Action] |
| Competitive | [H/M/L] | [Description] | [Action] |
| Financial | [H/M/L] | [Description] | [Action] |
| Technology | [H/M/L] | [Description] | [Action] |

### Heuristic Check
- Kill signals present: [List or "None"]
- Pivot signals present: [List or "None"]
- Persist signals present: [List or "None"]

### Recommended Next Steps

**If GO:**
1. [Specific growth action]
2. [Specific product action]
3. [Specific metric to track]

**If CONDITIONAL GO:**
1. [Specific gap to address]
2. [Experiment to run with timeline]
3. [Threshold that would upgrade to full GO]

**If PIVOT:**
1. [What to keep from current approach]
2. [What to change and why]
3. [New hypothesis to test]

**If KILL:**
1. [What was learned that carries forward]
2. [Adjacent opportunities identified during research]
3. [Clean shutdown steps]

### Bias Check
Before accepting this verdict, honestly answer:
- Am I building because the market wants this, or because I want to build?
- Would I pursue this if I had not already invested [X] months?
- Am I avoiding sales conversations because they are uncomfortable?
- Am I adding features to delay the moment of market truth?
```

## Tools

### Required
- Web search, web fetch (for any final research gaps, competitor updates)

### Optional (Enhanced Results)
- **Ahrefs MCP**: Use for any demand/competitive data gaps that need filling before scoring. Without Ahrefs, rely on evidence already gathered in earlier phases.

## Related Skills

- **Previous:** [distribution-plan](/skills/distribution-plan) -- Distribution results provide the last critical evidence dimension
- **Next:** If GO, begin executing the distribution plan at scale. If PIVOT, return to [problem-extraction](/skills/problem-extraction) or [audience-identification](/skills/audience-identification) with the new hypothesis. If KILL, document learnings and move on.
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) -- The go/no-go decision is the moment most susceptible to cognitive bias; always run bias audit before finalizing

## Reference Files

Read these for detailed methodology:
- `references/scoring-matrix.md` -- Full weighted scoring matrix with rubrics, thresholds, and calibration data
- `references/pmf-measurement.md` -- Sean Ellis Test, PMF indicators, and post-launch measurement methodology
