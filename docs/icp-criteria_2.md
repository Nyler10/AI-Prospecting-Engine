# Defining ICP Criteria

A pattern for writing qualification rules an AI agent can apply consistently, rather than leaving "is this a good prospect?" to case-by-case judgment calls.

## The two-part structure

**1. Hard qualifying tests** — binary pass/fail conditions a prospect must clear before any research or drafting happens. These should be checkable from public information (company size, industry, an observable gap in their current setup, etc.), not require a conversation to determine. A prospect that fails a hard test is rejected immediately — it does not get passed downstream in hopes that a well-written email compensates for a poor fit.

**2. Priority signals** — softer indicators that don't disqualify a prospect on their own but help rank qualified prospects against each other (e.g., recent funding, a public award or recognition, a specific technology gap visible in their current stack). Use these to sequence outreach, not to gate it.

## Exclusions

Explicitly list what *doesn't* qualify, not just what does. Two exclusion types matter most:

- **Segment exclusions** — categories of organization that look superficially similar to your ICP but have a fundamentally different buying process (different budget cycle, different decision-maker, different sales motion) and should be routed differently or skipped entirely
- **Ownership exclusions** — in any environment with multiple reps sharing a CRM, an otherwise-qualified prospect that's already owned by another rep is excluded from new outreach, full stop

## Verification discipline

Any field used to qualify a prospect that can't be confirmed from a reliable source should be marked `unknown` rather than guessed. An agent that fabricates qualifying data to force a prospect through the funnel is a bigger risk than an agent that's occasionally too conservative.

## Applying this

See [`examples/streaming-media-sales/icp-criteria.md`](../examples/streaming-media-sales/icp-criteria.md) for this pattern filled in with a real ICP, real qualifying tests, and real exclusions.
