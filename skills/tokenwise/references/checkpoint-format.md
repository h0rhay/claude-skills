# Checkpoint Format Reference

## The State Block Template

```
## Session State — [Topic] — [YYYY-MM-DD]

**Goal:** [1 sentence]

**Key Decisions:**
- [Decision]: [1-sentence rationale]

**Current Understanding:**
[2-4 dense sentences]

**Open Questions:**
- [Question 1]

**Next Step:** [Specific next action]
```

## Examples

### Example 1: Technical Research Session

```
## Session State — React Server Components Migration — 2026-03-31

**Goal:** Migrate our Next.js 13 app from client-side rendering to RSC where it makes sense.

**Key Decisions:**
- Keep auth components client-side (need browser APIs)
- Move data-fetching pages to RSC first (biggest perf win)
- Use streaming for dashboard page (multiple data sources)

**Current Understanding:**
RSC eliminates the client bundle for data-heavy pages, cutting load time ~40%. The migration can be incremental — no big bang rewrite needed. Main risk is third-party libraries that assume client context. We'll audit dependencies before touching each route.

**Open Questions:**
- Does our analytics SDK work in server context?

**Next Step:** Audit the /dashboard route's dependency tree for client-only packages.
```

### Example 2: Business Strategy Session

```
## Session State — Pricing Model Redesign — 2026-03-31

**Goal:** Shift from per-seat to usage-based pricing without losing enterprise clients.

**Key Decisions:**
- Hybrid model: base platform fee + usage tiers
- Grandfather existing contracts for 12 months
- Usage metric = API calls, not storage (better aligns with value)

**Current Understanding:**
Usage-based pricing increases expansion revenue but needs clear cost predictability for enterprises. A committed-use discount (like cloud providers) solves the predictability concern. Sales team needs a simple calculator tool. Finance wants 90-day runway before launch.

**Open Questions:**
- What's the minimum committed tier that makes the unit economics work?

**Next Step:** Model three tier structures and compare margin impact.
```

## Compression Tips

When generating a checkpoint, prioritize:

1. **Decisions over discussions** — capture what was decided, not the debate
2. **Conclusions over reasoning** — the "what" matters more than the "why" for reloading context
3. **Specifics over generalities** — "use PostgreSQL" not "decided on a database"
4. **Next action over wish list** — one clear next step, not five possibilities

Target: under 150 words for the state block. If it's longer, you're including too much narrative.

## Using a Checkpoint in a New Session

When starting a new chat, paste the state block at the top followed by your question:

```
[paste state block]

Question: [your specific question for this session]
```

This gives Claude the minimum viable context to answer well without re-explaining the whole project.
