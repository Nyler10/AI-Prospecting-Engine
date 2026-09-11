# CRM Dedup & Enrichment Workflow

## Why this step exists

Prospecting without CRM hygiene leads to duplicate outreach — cold-emailing organizations that are already contacts, leads, or clients. This step runs before any drafting happens, not after.

## The workflow

1. **Identify a candidate prospect** from the ICP-driven research step
2. **Cross-reference against the existing CRM** to check whether the organization or any of its known contacts already exists as a record
3. **If a match exists** — the prospect is excluded from new outreach entirely, preventing redundant or conflicting contact from a rep who doesn't own that relationship
4. **If no match exists** — a new, enriched contact record is created with the available fields: name, title, company, email, phone

## Working patterns

- In a multi-rep shared CRM, ownership collisions are checked *before* an account is added to any outreach batch — an account already owned by another rep is flagged and excluded, not contacted
- Direct verification (e.g., fetching an organization's own staff directory page) is treated as more reliable than general web search for finding accurate current contact names and titles
- Fields that can't be verified are left as `unknown` rather than populated with a guess — unverified data is not entered into the CRM
