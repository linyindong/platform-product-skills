---
name: yindong-scope-governor
description: Assess MVP scope, phase boundaries, change impact, and hidden complexity for complex product requirements. Use when the user asks whether a change is big, whether to include something in this phase, how to split MVP vs future iteration, or when a feature may affect data objects, permissions, workflow, UI, APIs, operations, rollout, migration, or platform consistency.
---

# Yindong Scope Governor

Use this skill before drafting when the user is exploring whether a requirement belongs in the current phase.

## When NOT to Use

Do not use this skill to write the full PRD; after the scope verdict, route to `yindong-prd-builder`. Do not use it as a final document review; use `yindong-prd-reviewer`. If the business direction itself is unclear, route to `yindong-product-operating-system` first.

## First Move

Do impact analysis before writing detailed PRD content.

Identify:

- current phase objective
- proposed change
- affected systems
- affected configuration/runtime objects
- affected UI/prototype areas
- affected API/data fields
- affected permissions and ownership
- operational and rollout impact

Classify the change before judging scope:

- Field-only / enum-only change
- API contract change
- Flow or state transition change
- Configuration surface change
- Migration / data correction change
- Operational SOP / manual handling change
- New platform capability

## Build Risk Gate

Before recommending inclusion, name the single biggest risk:

```md
Biggest Risk:
Evidence:
Verdict:
Next Validation:
Route To:
```

Use one verdict:

- Include in MVP
- Simplify for MVP
- Validate first
- Defer to future iteration
- Add compatibility placeholder
- Reject for this product layer

For feature requests, separate demand evidence from opinions:

- Weak signals: one-off ask, competitor-copy, internal anxiety, compliments
- Stronger signals: repeated workflow blocker, revenue/retention impact, manual workaround, regulatory/ops requirement, production incident

If evidence is weak but the idea may matter, recommend a low/no-build validation step before PRD drafting.

## Small Request Expansion Check

When the request sounds simple, translate it into real impact before accepting that it is small.

Examples:

- "Just add a button" may introduce permissions, status transitions, audit logs, notifications, or rollback.
- "Just add a record" may introduce a runtime object, retention rule, query permission, export need, or reconciliation path.
- "Just notify another system" may introduce callback contract, retry, timeout, idempotency, monitoring, and manual replay.
- "Just add a config" may introduce lifecycle, effective time, versioning, rollback, permission, and old-record behavior.

Ask these checks:

- Does it change any object status or lifecycle?
- Does it create a new actor, permission, or approval responsibility?
- Does it trigger callback, notification, audit, report, reconciliation, or manual handling?
- Does it affect existing data, in-flight records, or downstream consumers?
- Does it require rollback, migration, monitoring, or support SOP?
- Can it be handled by existing capability or configuration instead of new platform behavior?

## Impact Table

Use this format:

```md
## Impact Summary

| Area | Impact | Reason | Recommendation |
|---|---|---|---|
| Data Model | Low/Medium/High |  |  |
| Flow / State | Low/Medium/High |  |  |
| UI / Prototype | Low/Medium/High |  |  |
| API / Integration | Low/Medium/High |  |  |
| Permission / Ownership | Low/Medium/High |  |  |
| Operations / Rollout | Low/Medium/High |  |  |

## Recommendation
```

## Recommendation Types

Use one of these recommendations:

- Include in MVP: required for production usability or logical closure.
- Simplify for MVP: needed, but should be implemented with a narrower version.
- Validate first: possible value, but current evidence is too weak to commit delivery capacity.
- Defer to future iteration: useful, but creates disproportionate complexity now.
- Add compatibility placeholder: not implemented now, but data/model naming should not block future support.
- Reject for this product layer: belongs to another system/team or duplicates existing platform capability.

## Complexity Signals

Treat these as scope expansion signals:

- new lifecycle/status states
- new actor, role, or permission model
- group/permission logic
- new runtime object or snapshot rule
- new callback/retry/reconciliation path
- new cross-system dependency
- new portal/tenant/source-system behavior
- new migration requirement
- prototype changes across multiple pages
- operational manual process with no owner
- ambiguous source of truth

## MVP Boundary Rules

Separate:

- `In Scope`
- `Out of Scope`
- `Not Supported in This Phase`
- `Future Iteration`

Ask:

- Is this required for MVP production usability?
- Is it required for logical closure?
- Does it add long-term platform complexity?
- Can existing capability support it?
- Can it be expressed as configuration?
- Can it be represented by a future-compatible field/name without implementing behavior now?
- Who owns temporary manual work if deferred?
- Does this only update a contract, or does it introduce new flow/state/ops behavior?
- If migration or data correction is involved, what is the validation, rollback, and completion checklist?

## Output Style

- Be direct and concise.
- Give a recommendation, not only pros/cons.
- Name the biggest risk instead of producing only a long risk inventory.
- State what must change if included now.
- State what remains stable if deferred.
- Route to the next skill or artifact after the scope decision.
- Avoid drafting detailed PRD sections until the phase decision is clear.
