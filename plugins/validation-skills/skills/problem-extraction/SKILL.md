---
name: problem-extraction
description: "Validate whether your problem is real, painful, and shared by others. Triggers: validate my problem, is this a real problem, mom test, problem validation, test my assumptions, do people actually have this problem, pain point research"
---

# Problem Extraction

> Stress-tests whether your problem is real, painful, and widespread — or just YOUR problem amplified by builder bias.

## Before Starting

Read `.claude/validation-context.md` to load the current product context. If it doesn't exist, run the `validation-context` skill first.

## Purpose

The most common reason products fail is that the founder assumed their personal frustration was universal. This skill forces evidence collection: mining real communities for pain signals, scoring problem severity, cataloging workarounds, and building a language translation table between how you describe the problem and how customers describe it. The output is a Problem Validation Brief with a clear go/yellow/red assessment.

## Methodology

### Step 1: Problem Statement Audit

Take the problem statement from `validation-context.md` and stress-test it:

- **The "nod test":** Would a non-technical stranger understand this problem? If not, rewrite it.
- **The "so what" test:** What happens if nobody ever solves this? If the answer is "mild inconvenience," that's a red flag.
- **The "builder trap" check:** Does the problem statement describe a FEATURE you want to build, or a PAIN someone experiences? Features fail. Pains sell.

Rewrite the problem statement if needed. A good problem statement sounds like a complaint, not a product pitch.

**Bad:** "Small businesses need AI-powered inventory optimization."
**Good:** "Small retailers waste 3-5 hours per week manually counting stock and still run out of bestsellers."

### Step 2: Workaround Audit

Search for how people currently solve this problem. Workarounds are the strongest evidence of real pain — if people have cobbled together solutions, the problem is worth solving.

**Search queries to run (execute at least 5-8 of these):**
- `"tired of [problem]" site:reddit.com`
- `"looking for a tool" [problem domain] site:reddit.com`
- `"how do you handle" [problem] site:reddit.com`
- `"alternative to" [current solution] site:reddit.com`
- `[problem domain] workaround OR hack OR "what I do" site:reddit.com`
- `[problem] site:news.ycombinator.com`
- `[problem] frustrated OR "looking for" site:reddit.com`
- `"wish there was" [problem domain]`
- `[problem] "spreadsheet" OR "manual" OR "by hand" site:reddit.com`
- `[competitor name] alternative OR replacement`

**For each workaround found, document:**
- What they're doing (spreadsheet, manual process, competitor tool, custom script, VA)
- How much time/money it costs them
- What they hate about it
- Exact language they use to describe it

**Workaround severity ladder (from weak to strong evidence):**

| Workaround Type | Pain Signal Strength | Implication |
|----------------|---------------------|-------------|
| "I just live with it" | Weak | Problem is annoying but not painful enough to act |
| "I Google it each time" | Moderate | Recurring problem, no committed solution |
| "I use a spreadsheet" | Good | Problem is real and recurring, no good tool exists |
| "I cobbled together [Tool A + Tool B + Zapier]" | Strong | High pain, willing to invest time in solving it |
| "I hired someone to do it" | Strong | Budget exists, willing to spend money |
| "I built my own script/tool" | Very strong | Technical pain, invested significant effort |
| "I'm paying $X/month for [competitor] but hate it" | Strongest | Budget, pain, AND switching intent |

**Workaround cost calculation:**
When people describe time-based workarounds, convert to dollar cost:
- Hours per week x estimated hourly rate = weekly cost
- Weekly cost x 4.3 = monthly cost
- This becomes your price anchor — your product should cost less than the workaround

### Step 3: Pain Severity Scoring

Rate the problem across two dimensions:

**Frequency spectrum:**
| Score | Frequency | Example |
|-------|-----------|---------|
| 1 | Rarely (once a year) | Annual tax filing frustration |
| 2 | Occasionally (monthly) | Monthly report compilation |
| 3 | Regularly (weekly) | Weekly inventory counts |
| 4 | Frequently (daily) | Daily data entry drudgery |
| 5 | Constantly (multiple daily) | Every customer interaction has friction |

**Intensity spectrum:**
| Score | Intensity | Signals |
|-------|-----------|---------|
| 1 | Mild annoyance | Mentions in passing, no emotional language |
| 2 | Noticeable frustration | Some venting, but people cope |
| 3 | Significant pain | Detailed complaints, people asking for solutions |
| 4 | Acute problem | Emotional language, people describing dollar costs |
| 5 | Hair-on-fire | People already paying for bad solutions, urgent language |

**Pain Severity = Frequency x Intensity** (max 25)
- 20-25: Hair-on-fire problem. Strong signal.
- 12-19: Real pain with market potential. Worth pursuing.
- 6-11: Mild pain. Needs strong differentiation or niche focus.
- 1-5: Not painful enough. Reconsider.

### Step 4: Early Adopter 4/4 Check

All 4 criteria must be true for a genuine early adopter to exist. Search for evidence of each:

1. **HAVE the problem** — Actively experiencing it right now, not theoretically
   - Evidence: recent posts, current complaints, active discussion threads
2. **KNOW they have the problem** — They've articulated it to themselves or others
   - Evidence: specific language describing the pain, questions asked in communities
3. **Have BUDGET/AUTHORITY** — Can make purchasing decisions
   - Evidence: mentions of spending on alternatives, professional context, business use
4. **Already COBBLED a workaround** — Spreadsheets, manual processes, duct-tape solutions
   - Evidence: shared templates, described workflows, recommendations of partial solutions

**Score: X/4.** Flag which criteria lack evidence.

### Step 5: Complainer vs Customer Distinction

Not everyone who talks about a problem will pay to solve it. Distinguish between:

**Complainers** talk about problems but never act:
- "I wish someone would build..." but have never searched for a solution
- Enthusiastic about the idea but zero behavioral evidence of need
- Found in founder/builder communities, not user communities

**Customers** demonstrate behavioral evidence:
- Have already searched for solutions (ask: "What have you tried?")
- Have spent money on imperfect alternatives
- Have built their own workaround
- Can describe the cost of the problem in specific terms

**Red flag:** If all your signal comes from people saying "great idea!" rather than people describing their own attempts to solve the problem, you have complainers, not customers.

### Step 6: Simulated Customer Objections

Role-play as a skeptical target customer responding to the problem statement. Generate 5-7 realistic objections:

- "I already handle this with [workaround], why would I switch?"
- "This isn't painful enough for me to change my workflow."
- "My current tool does this well enough."
- "I don't trust a new tool with [sensitive data/process]."
- "Who are you? Why should I believe you can solve this better?"
- "The switching cost is higher than the pain."
- "I tried something like this before and it didn't work."

For each objection, assess: does the evidence from Steps 2-5 provide a strong counter, or does the objection stand? Unresolved objections are risks to flag.

### Step 7: Cross-Source Pattern Recognition

Look for the same complaint appearing independently across multiple sources. Cross-source repetition is the strongest possible signal — it means the problem isn't an artifact of one community's culture or one platform's bias.

**Check these source types:**
- Reddit (multiple subreddits — not just one)
- G2 or Capterra reviews of adjacent/competitor products
- App Store or Play Store reviews
- Hacker News threads
- Industry-specific forums or Slack/Discord communities
- Amazon reviews of books in the problem domain
- GitHub issues for related tools (if technical)
- Quora questions about the problem
- Twitter/X complaint threads

**Pattern strength assessment:**

| Cross-Source Count | Strength | Interpretation |
|-------------------|----------|---------------|
| 1 source only | Anecdotal | Not reliable — could be one person's issue or community artifact |
| 2-3 sources independently | Emerging signal | Worth investigating further, but not conclusive |
| 4-5 sources independently | Validated pain point | Strong evidence — the problem is real and widespread |
| 6+ sources independently | High-confidence validation | Proceed with confidence — this is a known, established pain |

**What "independently" means:** The same complaint surfacing in communities that don't cross-pollinate. A complaint on Reddit AND Hacker News is weaker than a complaint on Reddit AND G2 AND a Facebook group — because Reddit and HN share significant user overlap, while G2 reviewers and Facebook group members are more likely to be independent populations.

**Pattern recognition checklist:**
- [ ] Same core complaint (even if described differently) in 3+ sources
- [ ] Complaint spans at least 2 different platform types (e.g., review site + community)
- [ ] Complaint is recent (within last 12 months) in at least 2 sources
- [ ] People in different roles or industries describe the same pain
- [ ] The complaint isn't just about one competitor — it's about the problem category

### Step 8: Language Translation Table

Build a table mapping how YOU describe the problem versus how CUSTOMERS describe it. This is essential for all downstream positioning and copy. The language gap between builders and customers kills more products than bad features.

| Your words | Their words | Source |
|-----------|-------------|--------|
| [technical/builder language] | [emotional/plain language] | [where you found it] |

**How to populate:**
- Pull exact phrases from Reddit posts, reviews, forum threads
- Focus on emotional language: "I'm so tired of...", "I hate that...", "I wish I could just..."
- Note the specific words they use for the product category ("a simple tracker" not "analytics dashboard")
- Capture "before state" language (how they describe life with the problem)
- Capture "dream state" language (what they wish existed)

**Common translation patterns for itch products:**

| Builder Says | Customer Says |
|-------------|---------------|
| "AI-powered analytics" | "show me what's working" |
| "Workflow automation" | "stop doing the same thing over and over" |
| "Real-time data sync" | "numbers that are actually current" |
| "Centralized platform" | "everything in one place" |
| "Intelligent scheduling" | "stop the back-and-forth" |
| "Document intelligence" | "stop typing things in from PDFs" |

**Minimum translation table size:** Aim for at least 8-10 rows. If you can't find enough customer language, that's a signal you need more community research before proceeding.

**Where this table goes next:** The language translation table feeds directly into the positioning skill (VOC phrase bank) and the smoke-test skill (landing page copy). Getting this right here saves significant effort later.

> For detailed Mom Test methodology and interview techniques, read `references/mom-test-method.md`
> For a branching interview script template, read `references/interview-script.md`

## Output: Problem Validation Brief

Produce this deliverable:

```markdown
## Problem Validation Brief

### Problem Statement
[Refined statement in customer language]

### Pain Severity Score
**Frequency:** X/5 — [justification]
**Intensity:** X/5 — [justification]
**Overall:** X/25

### Workaround Audit
| Workaround | Cost (time/money) | Complaints | Source |
|------------|-------------------|------------|--------|
| [what they do now] | [hours/week or $/mo] | [what they hate] | [link/source] |

### Evidence Summary
**Community threads found:** [count]
**Sources checked:** [list]
**Cross-source patterns:** [complaints appearing in 2+ sources]
**Strongest evidence:** [most compelling finding with quote]
**Weakest area:** [where evidence was thin or absent]

### Early Adopter Check
- [ ] HAVE the problem — [evidence or gap]
- [ ] KNOW they have the problem — [evidence or gap]
- [ ] BUDGET/AUTHORITY to solve — [evidence or gap]
- [ ] Already COBBLED a workaround — [evidence or gap]
**Score: X/4**

### Language Translation Table
| Your words | Their words | Source |
|-----------|-------------|--------|
| | | |

### Simulated Objections
| Objection | Evidence-Based Counter | Resolved? |
|-----------|----------------------|-----------|
| | | Yes/No/Partial |

### Assessment
**GREEN:** Active community discussions, people paying for workarounds, 4/4 early adopter criteria, pain score 15+, cross-source patterns confirmed
**YELLOW:** Some discussion but low urgency, free workarounds exist, 2-3/4 early adopter criteria, pain score 8-14
**RED:** No evidence of searching, no workarounds, only founder's own experience, pain score <8

**Verdict:** [GREEN / YELLOW / RED]
**Key risks:** [What could invalidate this assessment]
**Recommended next step:** [What to do with this information]
```

## Tools

### Required
- Web search, web fetch

### Optional (Enhanced Results)
- **Dialog Reddit Research MCP** — for deeper Reddit semantic search across subreddits. Fallback: use web search with `site:reddit.com` queries.
- **Ahrefs MCP** — `keywords-explorer-overview` can validate whether people search for solutions. Fallback: check Google autocomplete suggestions manually.

## Related Skills

- **Previous:** [validation-context](/skills/validation-context) — Provides the product context this skill reads
- **Next:** [demand-discovery](/skills/demand-discovery) — Quantifies the market demand with search data and competitive intelligence
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit to check for IKEA effect inflating your perception of the problem
