# AI Prospecting & Outreach Playbook

An AI-driven B2B sales prospecting system built as a **Claude Project** — a structured set of instructions, qualification rules, and drafting guidelines that turn Claude into an autonomous (but human-supervised) BDR assistant.

This isn't a traditional application with source files. It's a documented prompt architecture: a defined ICP, a CRM workflow, and a set of drafting rules that Claude follows to research prospects, check them against an existing CRM, enrich qualifying records, and draft personalized outreach — with a human approving every send.

## Why this exists

Manual prospecting is repetitive and inconsistent: hours spent searching for qualified leads, manually checking the CRM for duplicates, and writing outreach emails from scratch for each one. This system offloads the repetitive, low-judgment steps (search, cross-referencing, first-draft writing) so the human rep spends time on what actually requires judgment — qualifying fit, personalizing the ask, and having the conversation.

## The workflow

1. **[ICP & qualification rules](docs/icp-criteria.md)** — how prospects are identified and filtered before any outreach is drafted
2. **[CRM dedup & enrichment](docs/hubspot-workflow.md)** — how new prospects are checked against existing CRM records and enriched
3. **[Drafting & tone guidelines](docs/tone-and-drafting-guidelines.md)** — the rules that shape how each outreach email is written
4. **Human review** — every email is generated as a draft, never auto-sent; a person always reviews before anything goes out

## Design principles

- **Human-in-the-loop by default** — the system drafts, it never sends
- **Factual accuracy guardrails** — no inflated or fabricated claims about product capability or business terms in generated copy
- **CRM hygiene first** — cross-referencing happens before drafting, so existing relationships are never re-contacted
- **Research-driven personalization** — generic outreach is treated as a failure mode; every draft is expected to reference something specific about the prospect

## Status

Actively used in a live sales workflow. This repo documents the actual rules and logic behind that system — the real qualification criteria, CRM workflow, and drafting guidelines — with any company-specific or CRM-identifying details generalized for public sharing.
