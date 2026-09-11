# CRM Dedup & Enrichment Workflow

A CRM-agnostic pattern for making sure an agent never creates duplicate outreach or contacts a prospect someone else already owns — regardless of which CRM platform sits underneath it.

## The workflow

1. **Identify a candidate prospect** from the ICP-driven research step
2. **Cross-reference against the existing CRM** to check whether the organization or any of its known contacts already exists as a record
3. **If a match exists** — the prospect is excluded from new outreach entirely, preventing redundant or conflicting contact
4. **If the CRM is shared across multiple reps or teams**, also check ownership — a technically-unmatched prospect that's already assigned to another rep is still excluded, not just a literal duplicate record
5. **If no match or ownership conflict exists** — a new, enriched contact record is created with the available verified fields

## Working patterns that generalize across CRMs

- **Collision-checking happens before an account enters any outreach batch**, not as cleanup afterward — the exclusion should be a gate, not a correction
- **Direct-source verification beats general search** for contact accuracy — fetching an organization's own staff directory or "about" page is more reliable than a generic web search for current names and titles
- **Unverified fields stay `unknown`** rather than being populated with a best guess — bad data compounds every time it's read back by a later step in the pipeline
- **Recovering context after a gap** (e.g., resuming a batch after time away) should rely on structured CRM queries filtered by owner and date, not on re-deriving state from memory or conversation history alone

## Applying this

The specific query syntax and field names will differ by CRM platform, but the sequencing — qualify, dedup, check ownership, then and only then enrich — holds regardless of which system sits underneath it.
