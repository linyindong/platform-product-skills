---
name: yindong-scope-governor
description: Assess MVP scope, phase boundaries, change impact, and hidden complexity for complex product requirements. Use when the user asks whether a change is big, whether to include something in this phase, how to split MVP vs future iteration, or when a feature may affect data objects, permissions, workflow, UI, APIs, operations, rollout, migration, or platform consistency.
---

# Yindong Scope Governor

Use this skill before drafting when the user is exploring whether a requirement belongs in the current phase.

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

## Output Style

- Be direct and concise.
- Give a recommendation, not only pros/cons.
- State what must change if included now.
- State what remains stable if deferred.
- Avoid drafting detailed PRD sections until the phase decision is clear.
