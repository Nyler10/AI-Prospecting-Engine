# AI Prospecting & Outreach Framework

A methodology for turning Claude into an autonomous (but human-supervised) prospecting agent for any B2B sales org — not a single-company tool, but a reusable pattern for defining the rules an AI agent needs to prospect responsibly.

This isn't a traditional application with source files. It's a documented prompt architecture: a set of design decisions about how an AI agent should qualify prospects, avoid duplicate outreach, choose a pitch angle, and draft outreach — with a human approving every send, regardless of what company or vertical it's deployed for.

## Why this exists

Manual prospecting is repetitive and inconsistent: hours spent searching for qualified leads, manually checking the CRM for duplicates, and writing outreach emails from scratch for each one. This framework offloads the repetitive, low-judgment steps (search, cross-referencing, first-draft writing) so the human rep spends time on what actually requires judgment — qualifying fit, personalizing the ask, and having the conversation. The framework itself is company-agnostic; only the inputs (your ICP, your verticals, your CRM) change.

## The framework

| Doc | What it defines |
|---|---|
| [`docs/icp-criteria.md`](docs/icp-criteria.md) | How to write hard qualifying tests and exclusion rules for any ICP |
| [`docs/pitch-angles.md`](docs/pitch-angles.md) | How to structure a distinct pitch angle per vertical or segment |
| [`docs/crm-workflow.md`](docs/crm-workflow.md) | A CRM-agnostic dedup, enrichment, and ownership-collision pattern |
| [`docs/drafting-guidelines.md`](docs/drafting-guidelines.md) | Tone, variant strategy, CTA rules, and the draft-only safety constraint |
| [`docs/agent-instructions.md`](docs/agent-instructions.md) | The pipeline that ties all four together into one agent |

## Worked example

[`examples/streaming-media-sales/`](examples/streaming-media-sales) shows this framework fully instantiated for a real use case — OTT/streaming platform sales across four verticals (live events/sports orgs, content-first creators, existing VOD operators, and government access TV). It's the concrete proof that the abstract framework actually holds up in a live sales motion.

## Design principles

- **Human-in-the-loop by default** — the agent drafts, it never sends
- **Factual accuracy guardrails** — no inflated or fabricated claims about product capability or business terms in generated copy
- **CRM hygiene first** — cross-referencing happens before drafting, so existing relationships are never re-contacted
- **Research-driven personalization** — generic outreach is treated as a failure mode; every draft is expected to reference something specific about the prospect
- **Portable by construction** — every rule in `docs/` is written as a pattern to fill in, not a hardcoded value, so the same agent instructions can be redeployed against a different ICP, CRM, or set of verticals

## Status

The framework and the worked example are both actively used in a live sales workflow. Company-specific identifiers (CRM portal IDs, real prospect names, internal client data) have been generalized or removed — what's shown here is the reusable logic, not proprietary data.
