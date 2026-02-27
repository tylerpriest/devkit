# Technical Analysis Method

Structured methodology for analyzing how competitors implement a feature technically — without having access to their source code. This reference supports Step 4 (Technical Implementation Analysis) of the feature-teardown skill.

---

## Principles

Technical analysis of closed-source products is detective work. You're building a picture from publicly available clues, not reading source code. Be explicit about your confidence level for every conclusion.

**Confidence levels:**

| Level | Basis | Use |
|-------|-------|-----|
| **High** | Direct evidence: source code, official documentation, author statements | Treat as fact |
| **Medium** | Strong inference: API shape, public docs, error messages, network behavior | Treat as likely |
| **Low** | Weak inference: job postings, tech stack detectors, architectural patterns | Treat as hypothesis |
| **Speculative** | No direct evidence: reasoning from product behavior only | Label clearly as speculation |

Always label your confidence level. Medium-confidence inferences are useful. Low-confidence speculation labeled as fact is dangerous.

---

## Method 1: Public API Analysis

If the product has a public API, it's the richest source of technical insight. API design reveals backend architecture, data models, and engineering priorities.

### Where to Find API Documentation

| Source | Search Pattern | Notes |
|--------|---------------|-------|
| Developer portal | "[product] API documentation" | Most reliable |
| API reference | "[product] API reference [feature area]" | Often auto-generated from code |
| SDK repositories | GitHub "[product] SDK" or "[product] client library" | May have examples |
| Postman collections | "[product] Postman collection" | Ready-to-use API examples |
| OpenAPI/Swagger spec | "[product] openapi spec" or "[product] swagger" | Machine-readable, very detailed |
| Changelog | "[product] API changelog" | Shows evolution and priorities |

### What to Extract from API Documentation

#### Data Models
The most valuable intelligence. API endpoints reveal the entities and relationships behind the feature.

**Document for each relevant endpoint:**

```markdown
### Endpoint: [Method] [Path]

**Purpose:** [What this endpoint does]
**Key parameters:**
- [param]: [type] — [what it controls]
- [param]: [type] — [what it controls]

**Response shape (key fields):**
- [field]: [type] — [what it represents]
- [field]: [type] — [what it represents]

**What this reveals:**
- [Architectural inference]
```

**What API data model patterns reveal:**

| Pattern Observed | Architectural Inference |
|-----------------|----------------------|
| Nested objects in responses | Tightly coupled entities, loaded together |
| ID references between endpoints | Loosely coupled, separate storage |
| Polymorphic type fields | Extensible design, multiple variants |
| Pagination on all list endpoints | Designed for scale from the start |
| Cursor-based pagination | High-volume data, real-time updates |
| Offset-based pagination | Simpler implementation, less scale-ready |
| Separate create and update endpoints | Traditional CRUD, distinct operations |
| Single upsert endpoint | Idempotent design, simpler client code |
| Webhook registration endpoints | Event-driven architecture |
| Batch/bulk endpoints | Designed for power users and integrations |

#### Naming Conventions
API naming reveals how the team thinks about the domain:

| Naming Pattern | What It Suggests |
|---------------|-----------------|
| Domain-specific terms (e.g., "workspace", "channel") | Strong domain modeling |
| Generic terms (e.g., "item", "entity", "resource") | Abstract/flexible but less intuitive |
| Versioned paths (/v2/, /v3/) | Mature API, backward compatibility priority |
| Feature-namespaced paths (/notifications/preferences/) | Modular, feature-team ownership |
| Flat paths (/preferences, /notifications) | Simpler routing, possibly monolithic |

#### Rate Limits & Constraints
Rate limits and documented constraints reveal performance characteristics:

| Constraint | What It Reveals |
|-----------|----------------|
| Low rate limit on feature endpoint | Expensive operation (complex query, external call) |
| High rate limit or no limit | Efficient, cached, or low-cost operation |
| Request size limits | Data volume expectations |
| Async/polling patterns | Long-running operations |
| "Eventually consistent" language | Distributed system, not real-time |

### API Analysis Template

```markdown
## [Product Name] — API Analysis

**API type:** REST / GraphQL / gRPC / Other
**Authentication:** API key / OAuth / JWT / Other
**Documentation quality:** [Excellent / Good / Adequate / Poor]

### Feature-Relevant Endpoints
| Endpoint | Method | Purpose | Key Fields |
|----------|--------|---------|-----------|
| | | | |

### Inferred Data Model
[Describe the entities and relationships you can infer from the API]

### Notable API Design Decisions
- [Decision 1 and what it implies]
- [Decision 2 and what it implies]

### Limitations & Constraints
- [Limit 1 and what it reveals about architecture]
- [Limit 2 and what it reveals about architecture]
```

---

## Method 2: Developer Documentation Mining

Product documentation, SDK guides, and integration docs often reveal implementation details that marketing pages don't.

### What to Search For

| Document Type | Search Pattern | What It Reveals |
|--------------|---------------|----------------|
| Integration guides | "[product] [feature] integration guide" | How the feature connects to external systems |
| Webhook docs | "[product] webhooks [feature]" | Event model, what triggers notifications |
| SDK examples | "[product] SDK [feature] example" | Expected usage patterns and data shapes |
| Migration guides | "[product] migration guide [feature]" | How the feature has evolved, breaking changes |
| Limits/quotas page | "[product] limits" or "[product] quotas" | System constraints and scaling boundaries |
| Status page | "[product] status" or "status.[product].com" | Infrastructure architecture signals |
| Security docs | "[product] security whitepaper" | Infrastructure, encryption, compliance |

### Configuration & Settings Documentation

Feature configuration docs reveal the decision space the engineering team designed:

| Configuration Aspect | What to Document | What It Reveals |
|---------------------|-----------------|----------------|
| Available options | All settings/toggles for the feature | Feature complexity and flexibility |
| Default values | What's pre-configured | Product philosophy (opinionated vs. blank slate) |
| Constraints | Min/max values, format requirements | Engineering boundaries and tradeoffs |
| Dependencies | "Requires X to be enabled first" | Feature coupling and prerequisites |
| Tier gating | "Available on Pro plan and above" | Feature value perception |

### Documentation Quality as a Signal

The quality and completeness of documentation itself is a signal:

| Documentation Quality | What It Suggests |
|----------------------|-----------------|
| Comprehensive, up-to-date, with examples | Well-resourced engineering team, developer focus |
| Auto-generated, sparse | API-first but may lack developer empathy |
| Outdated, contradicts behavior | Fast-moving product, docs are secondary |
| No developer docs | Not targeting developers/integrators |

---

## Method 3: Open-Source Code Review

For open-source competitors, you have direct access to implementation details. This is the highest-confidence source.

### How to Navigate an Unfamiliar Codebase

**Step 1: Orientation**
- Read the README for architecture overview
- Check for an `ARCHITECTURE.md` or `docs/` directory
- Look at the project's directory structure for feature organization
- Check `package.json` / `Cargo.toml` / `go.mod` for dependencies

**Step 2: Find the Feature**
- Search for the feature name in the codebase
- Look for feature-specific directories or modules
- Check route definitions for feature-related paths
- Search for UI component names related to the feature

**Step 3: Analyze the Implementation**

| Layer | What to Look At | What to Document |
|-------|----------------|-----------------|
| Data model | Schema definitions, migrations, types | Entities, relationships, constraints |
| API layer | Route handlers, controllers | Endpoints, validation, authorization |
| Business logic | Services, use cases, domain logic | Core algorithms, decision trees |
| State management | Store/state definitions, reducers | How feature state is managed client-side |
| UI components | Feature-specific components | Component structure, props, composition |

**Step 4: Check the History**
- Git log for the feature directory: when was it built? How has it evolved?
- Pull requests: what design decisions were debated?
- Issues: what bugs have been reported? What improvements requested?
- Release notes: how was the feature announced and iterated?

### Open-Source Analysis Template

```markdown
## [Product Name] — Source Code Analysis

**Repository:** [URL]
**Language/Framework:** [Tech stack]
**Feature location:** [Directory/module path]

### Data Model
| Entity | Key Fields | Relationships |
|--------|-----------|--------------|
| | | |

### Architecture Pattern
[MVC / CQRS / Event-sourced / Microservice / Monolith / etc.]

### Key Implementation Details
- [Detail 1 — file path and line reference]
- [Detail 2 — file path and line reference]

### Dependencies Used for This Feature
| Dependency | Purpose | Why They Chose It |
|-----------|---------|------------------|
| | | |

### Evolution History
- [Date]: [Major change and why (from PR/commit messages)]
- [Date]: [Major change and why]

### Known Issues & Limitations
- [Issue from GitHub issues tracker]
- [Limitation from code comments or docs]
```

---

## Method 4: Engineering Blog & Conference Talk Mining

Companies often share implementation details in blog posts and conference talks when they've solved hard problems.

### Search Strategies

| Source | Search Pattern | Best For |
|--------|---------------|---------|
| Company blog | "[company] engineering blog [feature]" | Official deep dives |
| Medium/Dev.to | "[company] [feature] implementation" | Team member posts |
| Conference talks | "[company] [feature] architecture" site:youtube.com | Detailed walkthroughs |
| Podcast interviews | "[company CTO/founder] [feature] podcast" | Candid technical discussions |
| Hacker News | "site:news.ycombinator.com [company] [feature]" | Technical community discussion |

### What Engineering Content Reveals

| Content Type | Typical Revelations |
|-------------|-------------------|
| "How we built X" blog post | Architecture, tech stack, key tradeoffs, scale numbers |
| Conference talk | Design decisions, what failed first, lessons learned |
| Incident report / postmortem | Infrastructure, failure modes, monitoring approach |
| Migration story | Old architecture, new architecture, why they changed |
| Open-source announcement | Which components they consider commodity vs. proprietary |

### Extraction Template

```markdown
## [Product Name] — Engineering Content Analysis

### Source: [Title and URL]
**Type:** Blog post / Conference talk / Podcast / Other
**Date:** [Publication date — important for relevance]
**Author role:** [Engineer / CTO / Product / etc.]

### Key Technical Revelations
- [Revelation 1]
- [Revelation 2]

### Architecture Details Shared
- [Detail with direct quote or timestamp]

### Problems They Encountered
- [Problem 1 and their solution]
- [Problem 2 and their solution]

### What They'd Do Differently
- [If mentioned — these are gold]
```

---

## Method 5: Job Posting Analysis

Job postings reveal what a company is building next and what technology they use.

### Search Strategies

| Source | Search Pattern |
|--------|---------------|
| Company careers page | "[company] careers" or "[company] jobs" |
| LinkedIn | "[company] [feature-related role]" |
| Job boards | "[company]" on Greenhouse, Lever, Ashby, etc. |

### What Job Postings Reveal

| Posting Element | What It Reveals |
|----------------|----------------|
| Required tech stack | Current implementation technology |
| "Experience with X" | Technologies actively in use |
| "Migrating from X to Y" | Architectural evolution in progress |
| Team size (hire count) | Investment level in this feature area |
| Seniority level | Complexity of the work (senior = hard problems) |
| "Greenfield" language | Building new, not maintaining |
| "Scale" emphasis | Growth-stage challenges |
| Specific feature mentions | Current development priorities |

### Job Posting Analysis Template

```markdown
## [Product Name] — Job Posting Analysis

### Relevant Postings Found
| Role | Posted | Key Technologies | What It Reveals |
|------|--------|-----------------|-----------------|
| | | | |

### Tech Stack Inference
**Frontend:** [Based on job requirements]
**Backend:** [Based on job requirements]
**Infrastructure:** [Based on job requirements]
**Data:** [Based on job requirements]

### Investment Signals
- [Signal 1: e.g., "Hiring 3 engineers for notifications team = heavy investment"]
- [Signal 2]

### Confidence:** Low — job postings indicate intent and current stack, not necessarily how the specific feature is built
```

---

## Synthesis: Technical Comparison

After analyzing all competitors, create a technical comparison:

```markdown
## Technical Architecture Comparison: [Feature Name]

### Architecture Approaches
| Dimension | [Product A] | [Product B] | [Product C] |
|-----------|------------|------------|------------|
| Primary architecture | | | |
| Data storage pattern | | | |
| API design | | | |
| Real-time capability | | | |
| Scale approach | | | |
| Key dependency | | | |
| Evidence confidence | | | |

### Common Technical Patterns
- [Pattern seen across multiple implementations]

### Divergent Technical Choices
| Decision Point | Approach A (Products) | Approach B (Products) | Tradeoff |
|---------------|----------------------|----------------------|----------|
| | | | |

### Technical Recommendations
Based on the analysis:
1. [Recommended approach with rationale]
2. [Key dependency to evaluate]
3. [Architecture decision to make early]
```
