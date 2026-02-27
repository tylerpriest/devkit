# UX Teardown Method

Structured methodology for analyzing how a specific feature is implemented across products — from first encounter to edge cases. This reference supports Step 3 (UX Pattern Teardown) of the feature-teardown skill.

---

## Preparation

Before starting a UX teardown, set up your analysis environment:

### Access Strategy per Product

| Access Level | What You Can Do | Approach |
|-------------|----------------|----------|
| Free account | Full feature access | Sign up, walk through the feature |
| Free trial | Time-limited access | Prioritize this product early in research |
| Freemium (feature gated) | Partial access | Observe what's available, note what's locked |
| No free access | Marketing + docs only | Use screenshots, videos, help docs, reviews |
| Open source | Full access | Run locally or use hosted demo |

**Prioritize products with free access.** For paid-only products, combine marketing materials, help documentation, YouTube walkthroughs, and review site screenshots.

### Browser Setup (with Browser/Playwright MCP)

If browser automation is available:
1. Use a fresh browser profile or incognito mode for each product — first-time experience matters
2. Take screenshots at every state transition
3. Record the full interaction flow
4. Note load times between steps
5. Check mobile responsiveness if the feature has a mobile variant

### Without Browser Access

If browser tools are not available:
1. Web search for "[product] [feature] screenshot" and "[product] [feature] walkthrough"
2. Check the product's help documentation — help docs often have annotated screenshots
3. Look for YouTube demo videos of the feature
4. Check G2/Capterra reviews for screenshots
5. Read the product's feature announcement blog post (usually includes screenshots or GIFs)
6. Check the Wayback Machine for evolution of the feature over time

---

## Feature Walk-Through Protocol

Walk through the feature in a specific order designed to capture every important dimension.

### Phase 1: First-Time Experience

The most critical phase. Users form lasting impressions in the first 30 seconds.

**What to observe:**

| Moment | What to Capture | Why It Matters |
|--------|----------------|---------------|
| First encounter | How does the user discover this feature exists? | Discoverability determines adoption |
| First click/tap | What happens when the user first engages? | Sets expectations for complexity |
| Onboarding | Is there guidance? Tooltips? A tutorial? | Reduces time-to-value |
| Empty state | What does the feature look like before any user data? | Blank slates kill engagement; good ones teach |
| Default configuration | What decisions has the product made for the user? | Reveals product philosophy (opinionated vs. flexible) |
| Time to value | How long until the user sees the feature working? | Shorter = better. Measure in clicks and seconds |

**First-time experience quality scale:**

| Rating | Description |
|--------|------------|
| Excellent | User immediately understands what to do, sees value within 30 seconds |
| Good | Clear guidance, user can self-serve, value within 2 minutes |
| Adequate | Some confusion but user can figure it out, value within 5 minutes |
| Poor | Requires documentation or trial-and-error, significant time to value |
| Hostile | Feature is discoverable but confusing, no guidance, unclear payoff |

### Phase 2: Happy Path

The primary intended flow — the interaction the product was designed around.

**Walk-through checklist:**

1. **Trigger:** What action initiates the feature flow?
   - Button click, menu selection, keyboard shortcut, contextual trigger?
   - Is the trigger contextual (appears when relevant) or persistent (always visible)?

2. **Input collection:** What information does the user provide?
   - Form fields, selections, drag-and-drop, text input, file upload?
   - How much input is required vs. optional?
   - Are there smart defaults that reduce input burden?

3. **Decision points:** Where does the user make choices?
   - How many decisions before completion?
   - Are choices reversible?
   - Is there a recommended/default option?

4. **Feedback during flow:** How does the product communicate progress?
   - Progress indicator (steps, percentage, progress bar)?
   - Inline validation (real-time error/success)?
   - Preview/live preview of changes?

5. **Completion:** How does the flow end?
   - Explicit save/submit button?
   - Auto-save?
   - Confirmation screen or message?
   - Redirect to where?

6. **Post-completion:** What happens immediately after?
   - Celebration moment (confetti, success message)?
   - Next step suggestion?
   - Return to previous context?

### Phase 3: Edge Cases & Error States

Where products reveal their maturity and engineering quality.

**Edge cases to test:**

| Category | Specific Tests |
|----------|---------------|
| Empty inputs | Submit with nothing filled in. What happens? |
| Maximum inputs | Enter extremely long text, upload large files, add many items |
| Invalid inputs | Wrong format, special characters, SQL injection attempts |
| Concurrent use | Two tabs with same feature open. Conflicts? |
| Network interruption | Slow connection, offline. Graceful degradation? |
| Browser back/forward | Mid-flow, press back. State preserved or lost? |
| Abandon and return | Leave mid-flow, come back later. Resume or restart? |
| Permission boundaries | What happens when the feature needs permissions not yet granted? |

**Error state analysis:**

For each error encountered, document:

| Dimension | What to Record |
|-----------|---------------|
| Error trigger | What user action caused the error |
| Error display | How the error is shown (inline, modal, toast, page-level) |
| Error message | Exact text (is it helpful? Actionable? Blaming?) |
| Recovery path | Can the user fix it? How? How many clicks? |
| Data preservation | Is user input preserved or lost after the error? |
| Prevention | Did the UI try to prevent the error (validation, constraints)? |

### Phase 4: Undo & Recovery

How the product handles mistakes and changes of mind.

**Undo mechanisms to check:**

| Mechanism | Implementation | User Experience |
|-----------|---------------|----------------|
| Undo button | Explicit action reversal | Clear, discoverable |
| Undo toast | Timed toast with "Undo" link | Quick but can be missed |
| Edit/modify | Change settings after initial setup | Flexible, ongoing |
| Version history | Revert to previous state | Powerful but complex |
| Delete and recreate | Remove and start over | Heavy-handed fallback |
| No undo | Changes are permanent | Friction, anxiety |

**Document the undo window:** How long does the user have to undo? Is it clear?

---

## State Inventory Template

For each competitor, catalog every visual state the feature can be in.

```markdown
### [Product Name] — State Inventory

| State | Exists? | Quality | Screenshot/Description |
|-------|---------|---------|----------------------|
| Empty (no data) | Y/N | [Rating] | [Description] |
| Loading (initial) | Y/N | [Rating] | [Skeleton / Spinner / Progressive] |
| Loading (action) | Y/N | [Rating] | [How the UI responds during saves/updates] |
| Populated (normal) | Y/N | [Rating] | [The standard view with data] |
| Populated (many items) | Y/N | [Rating] | [Pagination / Virtual scroll / Load more] |
| Error (validation) | Y/N | [Rating] | [Inline / Summary / Toast] |
| Error (system) | Y/N | [Rating] | [How system errors are communicated] |
| Success (confirmation) | Y/N | [Rating] | [How success is communicated] |
| Disabled/locked | Y/N | [Rating] | [Permission-gated or plan-gated states] |
| Mobile/responsive | Y/N | [Rating] | [How the feature adapts to small screens] |
```

**Quality ratings:** Excellent / Good / Adequate / Poor / Missing

---

## Micro-Copy Audit

The words a product uses at key moments reveal its personality and priorities.

**Capture micro-copy at these moments:**

| Moment | What to Record | What Good Copy Does |
|--------|---------------|-------------------|
| Call-to-action | Button text, link text | Clear verb that sets expectations |
| Empty state | Headline, description, CTA | Motivates first action, not just describes emptiness |
| Error message | Title, description, recovery | Explains what happened AND how to fix it |
| Success message | Confirmation text | Confirms what happened and suggests next step |
| Tooltip/help text | Inline guidance | Explains without condescending |
| Placeholder text | Input field placeholders | Shows expected format or provides example |
| Loading state | Loading message (if any) | Sets expectations for wait time |
| Destructive action | Warning text, confirmation | Makes consequences clear, not scary |

**Micro-copy quality signals:**
- Uses "you/your" (user-centered) vs. "we/our" (company-centered)
- Active voice vs. passive voice
- Specific vs. vague ("Your file was saved" vs. "Operation complete")
- Helpful vs. blaming ("That email format isn't right" vs. "Invalid input")
- Consistent tone across all states

---

## Interaction Pattern Classification

Classify the core interaction pattern used by each competitor. This helps compare approaches systematically.

### Common Feature Interaction Patterns

| Pattern | Best For | Tradeoffs |
|---------|---------|-----------|
| **Wizard/Stepper** | Complex setup, multi-step processes | Guided but slower; can feel heavy for simple tasks |
| **Modal/Dialog** | Quick edits, confirmations, focused tasks | Focused but interrupts context; bad for complex forms |
| **Inline edit** | Direct manipulation, quick changes | Fast but can lack structure; harder to validate |
| **Side panel/Drawer** | Context-preserving edits, detail views | Keeps context visible but reduces editing space |
| **Full-page form** | Complex configuration, many fields | Lots of space but full context switch |
| **Settings page** | Persistent preferences, configuration | Familiar but can become a dumping ground |
| **Drag-and-drop** | Ordering, organizing, spatial relationships | Intuitive for spatial tasks but poor accessibility |
| **Command palette** | Power users, keyboard-driven workflows | Fast for experts but hidden from new users |
| **Contextual menu** | Actions on specific items | Discoverable on right-click but hidden otherwise |
| **Floating action** | Primary creation actions (mobile) | Visible but only supports 1-2 actions |

### Pattern Selection Criteria

When evaluating which pattern a competitor chose, consider:

| Factor | Question |
|--------|----------|
| Complexity | How many inputs/decisions does the interaction require? |
| Frequency | How often does the user perform this action? |
| Context dependency | Does the user need to see other content while interacting? |
| Reversibility | How easy should it be to undo? |
| User expertise | Are users power users or occasional visitors? |
| Mobile support | Does this need to work on small screens? |

---

## Accessibility & Performance Quick Checks

Not a full accessibility audit, but quick checks that reveal implementation quality.

### Accessibility Quick Check

| Check | How to Test | What It Reveals |
|-------|-----------|-----------------|
| Keyboard navigation | Tab through the feature without a mouse | Whether keyboard-only users can access it |
| Focus indicators | Are focused elements visually distinct? | Whether the product cares about accessibility |
| Screen reader labels | Check aria-labels on interactive elements | Whether assistive tech was considered |
| Color contrast | Are text and controls readable? | Visual accessibility |
| Motion sensitivity | Are there animations? Can they be disabled? | Whether reduced-motion preferences are respected |

### Performance Quick Check

| Check | How to Test | What It Reveals |
|-------|-----------|-----------------|
| Initial load | How long does the feature take to appear? | Frontend optimization quality |
| Action response | How long after clicking before something happens? | Backend/API performance |
| Data loading | How does it handle loading large datasets? | Pagination/virtualization strategy |
| Optimistic updates | Does the UI update before the server confirms? | Modern vs. legacy architecture signal |
| Offline behavior | What happens with no network? | Progressive web app maturity |

---

## Comparative UX Analysis Template

After teardowns are complete for all competitors, use this template to compare:

```markdown
## UX Comparison: [Feature Name]

### Approach Comparison
| Dimension | [Prod A] | [Prod B] | [Prod C] | [Prod N] |
|-----------|---------|---------|---------|---------|
| Interaction pattern | | | | |
| Steps to complete | | | | |
| Time to first value | | | | |
| Default philosophy | | | | |
| Error handling | | | | |
| Undo mechanism | | | | |
| Mobile support | | | | |
| Accessibility | | | | |

### Standout Moments
- **Best first-time experience:** [Product] because [reason]
- **Best error handling:** [Product] because [reason]
- **Best power-user flow:** [Product] because [reason]
- **Best mobile adaptation:** [Product] because [reason]

### Common Friction Points
- [Friction seen across multiple products — likely hard to solve]
- [Friction unique to one approach — avoidable with different approach]
```
