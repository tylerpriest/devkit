---
name: validation-context
description: "Capture product/idea context for all validation skills. Triggers: start validation, set up context, new product idea, initialize validation, capture my idea, begin validation process"
---

# Validation Context

> Captures your product or idea's core attributes and writes `.claude/validation-context.md` so every other validation skill has shared context to work from.

## Purpose

This is the starting point for the validation skills suite. Before any research, positioning, or testing can happen, every skill needs to know what you're building, who it's for, and what problem it solves. This skill asks targeted questions, synthesizes the answers, and writes a structured context file that all other skills read automatically.

Run this skill once at the beginning. Re-run it whenever the product direction changes significantly.

## How It Works

### Step 1: Gather Core Information

Ask the user the questions below. If they've already provided some answers in their initial message, acknowledge what you have and only ask what's missing.

**Required (must have all of these):**

1. **What does it do?** — One sentence describing the product/tool/service. Push for plain language, not marketing speak.
2. **Who is it for?** — The specific person or role who uses this. Not "everyone" — the person who would care most.
3. **What problem does it solve?** — The pain point, frustration, or unmet need. Frame as the customer's problem, not a feature description.
4. **What exists today?** — Current stage: idea only, prototype, working product, product with users. Be specific about what's built.

**Optional but valuable (ask if the user seems knowledgeable about their market):**

5. **How do people solve this now?** — Existing workarounds, competitor tools, manual processes, or "they don't."
6. **Who have you talked to about this?** — Customers, prospects, friends, nobody. What did they say?
7. **What evidence do you have?** — Waitlist signups, pre-orders, usage data, conversations, search traffic, nothing.
8. **What's your unfair advantage?** — Domain expertise, existing audience, technical moat, first-mover, distribution access, or none.
9. **Business model hypothesis** — How you plan to make money: subscription, one-time, freemium, marketplace, ads, unsure.
10. **Target geography** — Where your customers are: global, US, specific country/region, local.

### Step 2: Synthesize and Validate

Before writing the context file, process the raw input through these filters:

**Problem statement rewrite:**
Translate the user's description into customer language. Founders describe their products in builder language. Customers describe their problems in pain language. These are almost never the same.

| Builder Language (Input) | Customer Language (Output) |
|-------------------------|---------------------------|
| "AI-powered workflow optimization" | "I waste hours every week on repetitive tasks I shouldn't have to do manually" |
| "Real-time analytics dashboard" | "I never know what's actually working until the end of the month" |
| "Automated inventory management" | "I'm constantly running out of stock because I can't keep track of what's selling" |
| "Collaborative project tracking" | "My team has no idea what anyone else is working on and things keep falling through the cracks" |

The customer language version should sound like something a frustrated person would type into Google at 11pm or post on Reddit. If it sounds like a product description, rewrite it again.

**Product category identification:**
What mental bucket would a customer put this in? The category sets expectations for features, pricing, and competitors. Getting the category wrong means constant explaining.

Common categories and signals:
- If people would search for "[thing] software" or "[thing] tool" → that's the category
- If existing competitors use a consistent category label → adopt it
- If no clear category exists → describe the outcome, not the mechanism

**Gap analysis:**
For each of the 10 questions, assess: did the user provide a clear, specific answer or a vague one?

| Quality | Example | Action |
|---------|---------|--------|
| Clear and specific | "Freelance graphic designers with 5+ clients" | Use as-is |
| Somewhat vague | "Small businesses" | Push back — ask for role, industry, size |
| Missing entirely | [No answer provided] | Write "Unknown — to be validated" in context file |
| Contradictory | Target audience doesn't match the problem | Flag the contradiction explicitly |

**Read-back and confirmation:**
Summarize what you captured in 3-4 sentences, covering: what the product does, who it's for, what problem it solves, and what stage it's at. Ask the user: "Does this accurately capture what you're building and who it's for?" Adjust before writing.

**Stage assessment:**
Determine the validation starting point based on the user's current stage:

| Stage | What Exists | Suggested Starting Path |
|-------|------------|------------------------|
| Idea only | Nothing built, concept in head | Start at problem-extraction, be thorough |
| Prototype | Mockup or basic demo, no users | Start at problem-extraction, validate quickly |
| Working product | Built and functional, no/few users | Start at demand-discovery, some problem validation done by building |
| Product with users | Active users but unclear market | Start at audience-identification or positioning |
| Revenue but stuck | Paying customers but growth stalled | Start at positioning or market-sizing |

### Step 3: Write the Context File

Write the file to `.claude/validation-context.md` using the template below.

## Output Template

Write this exact structure to `.claude/validation-context.md`:

```markdown
# Validation Context

*Last updated: [date]*
*Stage: [idea | prototype | working product | product with users]*

## Product Overview
**One-liner:** [Plain language description of what it does]
**Product category:** [Mental bucket customers would use]
**Business model:** [Subscription / one-time / freemium / marketplace / unsure]
**Target geography:** [Where customers are]

## The Problem
**Problem statement:** [Written in customer language — what a frustrated person would say]
**Who has this problem:** [Specific role/person, not "everyone"]
**How they solve it now:** [Current workarounds, tools, manual processes]
**Cost of the problem:** [Time, money, risk, frustration — quantified if possible]

## The Solution
**What you've built (or plan to build):** [Description focused on what it does for the user]
**Current state:** [What exists today — idea, mockup, MVP, launched product]
**Key differentiator:** [What makes this different from how they solve it now]

## Evidence So Far
**Conversations:** [Who you've talked to and key takeaways, or "none yet"]
**Signals:** [Waitlist, pre-orders, usage data, search traffic, or "none yet"]
**Unfair advantage:** [Domain expertise, audience, technical moat, or "none identified"]

## Open Questions
- [Key unknowns that validation should answer]
- [Gaps in knowledge flagged during context capture]
- [Assumptions that need testing]

## Language Notes
**Your words:** [How the founder describes the product]
**Customer words:** [How customers might describe the problem — to be refined in problem-extraction]
```

## Important Notes

- **Do not fabricate information.** If the user doesn't know something, write "Unknown — to be validated" rather than making assumptions. An honest "unknown" is infinitely more useful than a fabricated answer that downstream skills treat as fact.
- **Push for specificity.** "Small businesses" is too broad. "Freelance graphic designers managing 5-10 client projects" is useful. Every vague field produces vague research results in downstream skills.
- **The problem statement is the most important field.** Spend time getting it right. A bad problem statement poisons every downstream skill. If the user describes their product's features instead of the customer's pain, rewrite it. If they can't articulate the pain clearly, that itself is a signal worth noting.
- **This file is the single source of truth.** Every other validation skill reads it. Keep it accurate and update it when significant new information emerges.
- **Create the .claude directory** if it doesn't exist before writing the file.
- **Preserve existing context.** If `.claude/validation-context.md` already exists, read it first. Ask the user whether they want to update specific sections or start fresh. Don't overwrite previous research findings without confirmation.
- **Multiple products.** If the user has multiple products or ideas to validate, create one context file per product. Name them: `validation-context.md` for the primary, `validation-context-[name].md` for additional ones. Each skill run should specify which context file to use.

## Updating the Context File

The context file is a living document. It should be updated when:

| Trigger | What to Update | Who Initiates |
|---------|---------------|---------------|
| problem-extraction completes | Problem statement, customer language, open questions | Claude suggests, user confirms |
| demand-discovery completes | Evidence section (search data), open questions | Claude suggests, user confirms |
| audience-identification completes | Target audience specifics, personas | Claude suggests, user confirms |
| User conducts real interviews | Conversations section, evidence, problem statement refinement | User provides new data |
| Product pivot or direction change | Most sections — treat as near-fresh start | User initiates |
| Pricing/model change | Business model, evidence | User provides new data |

When updating, preserve the original context in a "Previous" section at the bottom so the evolution of thinking is traceable.

## When to Re-Run From Scratch

- The target audience has fundamentally changed based on research findings (not just refined — changed)
- The product has pivoted to solve a different problem
- The original context was captured with incomplete information and subsequent skills produced unreliable results
- More than 3 months have passed and the market landscape has shifted

## Related Skills

- **Next:** [problem-extraction](/skills/problem-extraction) — Validates whether the problem is real and painful beyond your own experience
- **Cross-cutting:** [builder-psychology](/skills/builder-psychology) — Run bias audit at any checkpoint to catch IKEA effect and sunk cost patterns
