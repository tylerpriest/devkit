# Community Signal Mining

Methodology for finding and evaluating demand signals in online communities where potential customers discuss their problems.

---

## Reddit Deep Dive

Reddit is the single richest source for unfiltered customer language and pain point signals. People are anonymous, which means they're honest in ways they aren't on LinkedIn or in surveys.

### Finding Relevant Subreddits

**Method 1: Direct search**
Search Reddit for your problem keywords. Note which subreddits the results come from. These are your primary research targets.

**Method 2: Community tab**
Switch to the "Communities" tab in Reddit search to find subreddits directly related to your problem domain.

**Method 3: r/findareddit**
Post or search in r/findareddit — humans will recommend relevant communities.

**Method 4: Competitor mentions**
Search `site:reddit.com "[competitor name]"` to find where people discuss existing solutions. Those communities are your audience.

**Method 5: Identity-based discovery**
Your audience may not be where you expect. Subreddits organize by IDENTITY, not category:
- Fitness app users might be in r/ADHD (exercise as coping mechanism)
- Productivity tool users might be in r/digitalminimalism (not r/productivity)
- Accounting software users might be in r/freelance (not r/accounting)
- B2B tool users might be in identity communities like r/startups, r/smallbusiness, r/sysadmin

**Method 6: Sidebar links**
Check the sidebars of subreddits you've found — "related communities" reveals the broader network.

### Search Queries Within Subreddits

For each relevant subreddit, run these searches:

| Query Pattern | What It Finds |
|---------------|---------------|
| `[problem keyword]` | Direct pain point mentions |
| `"looking for" [category]` | Active seekers — highest-value signal |
| `"alternative to" [competitor]` | Switching intent — they want something better |
| `"how do you" [task]` | Workaround discovery |
| `"willing to pay"` or `"take my money"` | Explicit payment signals |
| `"hate" [existing tool]` or `"frustrating"` | Pain point mining |
| `"I wish" [category/tool]` | Unmet needs |
| `"anyone else" [problem]` | Shared pain validation |
| `"switched from" [tool]` | Migration patterns and triggers |
| `"best" [category] "for" [audience]` | Buying-stage evaluation |

### Grading Individual Threads

| Signal | Score | Meaning |
|--------|-------|---------|
| 50+ upvotes on a problem thread | Strong | Real pain shared by many |
| 10+ comments with specific details | Strong | Validated need with depth |
| People sharing workarounds | Very strong | No good solution exists |
| Thread 1+ years old, still getting comments | Very strong | Persistent problem |
| "Willing to pay" or price discussion | Very strong | Payment intent confirmed |
| OP and commenters describe problem differently | Moderate | Multiple entry points for positioning |
| Only 1-2 comments, low engagement | Weak | May be niche or poorly phrased |
| All responses are "cool idea!" | Weak | Enthusiasm without substance |
| Thread only in founder/builder communities | Red flag | May not reflect real user demand |

### Red Flags in Community Research

- **Builder echo chamber:** All discussion is in r/SideProject, r/startups, r/indiehackers — these are founders, not customers.
- **Theoretical interest:** Comments are "someone should build..." not "I deal with this daily."
- **Prompted responses:** Problem only surfaces when someone asks about it, never organically.
- **Solution-resistant:** Heavy engagement on the problem but zero interest in any proposed solutions.
- **Stale threads:** Last activity was 2+ years ago with no recent discussion.

### Green Flags in Community Research

- **Active and recent:** Threads from the last 6 months with ongoing engagement.
- **Dollar amounts mentioned:** "I'm spending $X/month on [workaround]."
- **Independent discovery:** Same problem surfaces in multiple unrelated communities.
- **DIY solutions shared:** People posting their spreadsheet templates, scripts, or hacks.
- **Competitor review threads:** Active discussions comparing existing tools with specific complaints.
- **"Just switched" stories:** People describing migration from one solution to another.

---

## Beyond Reddit

### Hacker News

`site:news.ycombinator.com "[problem keyword]"`

HN has a strong BS filter — comments tend to be substantive and technical. Useful for:
- Developer tool validation
- Technical infrastructure problems
- B2B SaaS where technical people influence buying
- Trend identification (what's getting attention from sophisticated users)

**HN-specific signals:**
- "Show HN" posts about competitors = market is attracting builders
- "Ask HN: How do you handle [problem]" = active need
- Comments describing custom solutions = high pain, no good product

### Twitter/X

Search for problem keywords and complaint language:
- Complaint threads from practitioners
- "Day in the life" posts describing the pain
- Threads comparing tools
- Hot takes about the industry

Less reliable than Reddit (shorter, more performative) but useful for:
- Influencer sentiment
- Real-time reactions to competitor changes
- Professional context and identity signals

### GitHub Issues (For Technical Products)

If the problem is technical, GitHub issues on related repos are pure gold:
- Feature requests = unmet needs
- Bug reports = pain points with existing approaches
- "Help wanted" labels = problems people will invest time in
- Long issue threads with many participants = widespread need

### Product Hunt

Search for similar products and read the comments:
- What early adopters praise and criticize
- Feature requests in comments
- Maker responses revealing roadmap and positioning
- Upvote counts for category validation

### Industry-Specific Forums

Niche communities often have the richest signal because participants self-select for expertise:
- Professional association forums
- Industry Slack/Discord communities
- Vertical-specific Q&A sites
- Trade publication comment sections

### Facebook Groups

Particularly strong for non-technical audiences:
- Local business owners
- Tradespeople and service providers
- Hobbyist communities
- Parent and education communities

Signal quality can vary — look for specific pain descriptions over generic complaints.

---

## Using Reddit Research Tools

### Dialog Reddit Research MCP (If Available)

When the Dialog MCP is available, it provides semantic search across Reddit — more powerful than keyword matching:
- Search by concept rather than exact phrases
- Find threads discussing the problem even when they don't use your keywords
- Discover subreddits you wouldn't have found through manual search

**Best queries for Dialog MCP:**
- Describe the problem as a user would experience it
- Ask for threads about workarounds and frustrations
- Search for competitor discussion threads

### Manual Reddit Research (Fallback)

When no Reddit tools are available, use web search:
- `"[problem]" site:reddit.com` for direct matching
- `"[keyword]" subreddit:[name]` for targeted subreddit search
- `"[competitor]" review OR frustrating site:reddit.com` for pain mining
- Sort by "Top" in relevant timeframes to find highest-signal threads

---

## Synthesizing Community Evidence

After mining all sources, create a Community Signal Summary:

```markdown
### Community Signal Summary

**Subreddits checked:** [list with subscriber counts]
**Other sources checked:** [HN, Twitter, GitHub, forums]
**Total relevant threads found:** [count]
**Threads with 50+ engagement:** [count]
**Distinct pain points identified:** [count]

**Strongest signals:**
1. [Quote + source + engagement level]
2. [Quote + source + engagement level]
3. [Quote + source + engagement level]

**Cross-source patterns:** (same complaint in 2+ sources)
- [Pattern 1: description + sources]
- [Pattern 2: description + sources]

**Workarounds discovered:**
- [Workaround 1: what + who + cost]
- [Workaround 2: what + who + cost]

**Language patterns collected:**
- Pain phrases: "[exact quotes]"
- Outcome phrases: "[exact quotes]"
- Category language: "[how they name the solution type]"

**Confidence level:** [High / Medium / Low]
**Basis for confidence:** [Why you rate it this way]
```
