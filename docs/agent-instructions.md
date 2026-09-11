# Core Agent Instructions

This is the top-level pipeline that ties the ICP rules, CRM workflow, pitch angles, and drafting guidelines together into a single agent. Everything else in `docs/` is a detail this file references — this is the file you'd hand to an agent (or a new team member) to explain the whole system in one pass.

## Pipeline

1. **Identify candidates** against the [ICP criteria](icp-criteria.md) for the active vertical. Reject anything that doesn't clear the hard qualifying tests — do not pass a weak-fit prospect downstream and try to compensate for it later in the email copy.
2. **Research before anything else gets generated.** Pull the prospect's current setup, recent news, and business model. A prospect with no research behind it does not get a draft.
3. **Check the CRM.** Cross-reference the prospect — and, in shared-CRM environments, the owning rep — before creating any new record. See [crm-workflow.md](crm-workflow.md) for the exact dedup and ownership-collision logic. If a match or collision exists, stop.
4. **Enrich the record** only after the CRM check clears. Populate only verified fields; leave anything unconfirmed as `unknown`.
5. **Select the pitch angle** for the prospect's vertical from [pitch-angles.md](pitch-angles.md), then fold in the prospect-specific research from step 2. The vertical sets the frame; the research supplies the specifics.
6. **Draft multiple variants** with genuinely different strategic angles, following the tone and CTA rules in [drafting-guidelines.md](drafting-guidelines.md).
7. **Save as a draft. Never send.** This is the one non-negotiable constraint in the entire pipeline — every other step exists to make the draft good; this step exists to make sure a human always decides it's ready.

## Failure modes this is designed to prevent

- **Generic outreach** — solved by making research a hard gate before drafting, not an optional enhancement
- **Duplicate/colliding outreach** — solved by making the CRM check a gate before enrichment, not a cleanup step after
- **Overpromising in copy** — solved by an explicit accuracy constraint on generated claims
- **One-size-fits-all pitching** — solved by routing every prospect through a vertical-specific angle rather than a single master template
- **Unreviewed sends** — solved by making draft-only a hard constraint on the output mechanism itself, not a policy that relies on the agent remembering to ask

## Adapting this for a different company or vertical set

Nothing in this pipeline is hardcoded to a specific product or CRM. To redeploy it:
1. Rewrite `icp-criteria.md` with your own hard tests and exclusions
2. Rewrite `pitch-angles.md` with your own verticals, hooks, and competitive positioning
3. Swap the CRM-specific query syntax in `crm-workflow.md` for your actual platform, keeping the qualify → dedup → ownership-check → enrich sequencing
4. `drafting-guidelines.md` and this file typically need little to no change — they're the most product-agnostic layer of the system
