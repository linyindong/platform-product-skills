---
name: yindong-prd-reviewer
description: Review PRDs, product requirement drafts, platform designs, prototypes, and requirement sections for logic closure, system ownership, flow completeness, data model adequacy, edge cases, operational handling, rollout risk, and implementation readiness. Use when the user asks to check, review, validate, find gaps, see if logic is closed-loop, or assess whether a PRD is ready.
---

# Yindong PRD Reviewer

Use this skill in review mode. Prioritize product/system risks over wording polish. Do not rewrite the document unless the user asks.

First calibrate the review depth. A short feature PRD, implementation note, API change note, one-page alignment doc, and large 0-to-1 platform PRD should not be judged by the same completeness standard.

## Review Stance

Start with a brief review calibration:

```md
Document type:
Expected review depth:
Readiness judgment:
```

Then lead with findings, ordered by practical impact.

For each finding, include:

```md
Issue:
Why it matters:
Affected area:
Recommended handling:
```

Then add open questions and optional improvement suggestions.

## Review Calibration

Classify the artifact before applying the checklist.

### Short feature PRD / small functional change

Expected standard:

- Clear business scenario and goal.
- Clear in-scope behavior.
- Clear owner for each changed system.
- Clear API/data contract if any interface changes.
- Key happy path and major exception path.
- Rollout or compatibility note if existing users/data are affected.

Do not over-penalize for missing full platform governance sections if the change is genuinely small.

### Implementation note / API change note

Expected standard:

- Exact changed field/API/enum/contract is defined.
- Source system and persistence owner are clear.
- Validation/default/backward compatibility behavior is clear.
- Downstream consumers and migration impact are clear.
- Examples are sanitized and aligned with the contract.

Call out when the artifact is closer to an implementation note than a complete PRD.

### One-page PRD / BRD / stakeholder alignment doc

Expected standard:

- Concise problem, goal, scope, value, decision points, and high-level flow.
- Avoid excessive implementation detail.
- Identify which details must live in a separate PRD or tech spec.

Do not require full API tables unless the one-pager is being used as the only delivery artifact.

### Migration PRD

Expected standard:

- Source and target systems are clear.
- Migration trigger, sequence, and completion criteria are defined.
- Data mapping and validation checklist are present.
- Cutover, rollback, retry, and manual handling are addressed.
- Ownership for each migration step is explicit.

### Configuration UI PRD

Expected standard:

- Page path or entry point is clear.
- List fields, filters, create/edit behavior, validation rules, and empty/error states are defined.
- Permission, audit, and operation logging are covered when the UI changes operational data.
- Configuration object and runtime effect are not confused.

### Formula / rule logic PRD

Expected standard:

- Rule format and field definitions are explicit.
- Processing sequence is deterministic.
- Examples cover normal and edge cases.
- Backward compatibility and default behavior are clear.
- Data source and owner of reference data are defined.

### Operational SOP / issue-handling note

Expected standard:

- Trigger condition and owner are clear.
- Status transition and closure criteria are explicit.
- Manual handling, audit trail, and exception queue are covered where relevant.
- The SOP does not hide product/system gaps that should be fixed later.

### External integration PRD

Expected standard:

- System boundary, request/response contract, callback, timeout/retry, idempotency, and error handling are clear.
- Sandbox/production differences and rollout plan are covered when relevant.
- Ownership between internal systems and external partner is explicit.

### Large 0-to-1 platform PRD

Expected standard:

- Business problem to reusable platform capability is clear.
- System boundary and ownership are explicit.
- Configuration objects and runtime objects are separated.
- Main flows, state machine, callback/retry/rollback/reconciliation paths are covered.
- API/data changes, edge cases, rollout, operations, audit, and open questions are complete.
- MVP, out of scope, not supported in this phase, and future iteration are explicit.

Apply the full checklist strictly.

## Output Severity

Prefer product-review language over abstract severity labels:

- Blocking before engineering review: must fix before meaningful review or implementation.
- Should fix before launch: does not block discussion but creates delivery, data, ops, or rollout risk.
- Nice to improve: clarity, structure, or maintainability improvement.
- Open questions: decisions or ownership confirmations still needed.

Use Critical/High/Medium/Low only if the user asks for severity labels or the team format requires them.

## Review Checklist

Check business and scope:

- Background states the real business pain and platform need.
- Goal matches current phase.
- `In Scope`, `Out of Scope`, `Not Supported in This Phase`, and `Future Iteration` are explicit.
- Future-phase content does not leak into current requirements.

Check ownership and boundaries:

- Actors/systems are listed.
- Decision-maker, source of truth, persistence owner, validation owner, pass-through system, operational owner, downstream consumer, callback/event owner, and status-transition owner are clear.
- System responsibilities do not overlap ambiguously.

Check flow completeness:

- Main flow is modeled before detailed prose.
- Creation, query, callback, update, timeout, retry, rollback, reconciliation, migration, and manual exception paths are covered when relevant.
- Persistence points and state changes are visible.

Check data model adequacy:

- Configuration objects and runtime objects are separated.
- Snapshot behavior is explicit.
- Dynamic resolution fields are not confused with final resolved values.
- Field naming reflects lifecycle and cardinality.
- UI/prototype needs can be supported by available data.

Check API and implementation readiness:

- API/data-field changes include field name, mandatory flag, example, description, owner system, and change type when needed.
- Error codes/messages, idempotency, optimistic locking, retry, and timeout behavior are defined where relevant.
- Downstream consumers have enough data to act.

Check operational reality:

- Reconciliation, settlement timing, audit logs, monitoring, exception queues, manual fallback, rollout, and support handling are addressed.
- Migration compatibility and old/new platform behavior are considered.
- Finance/ops ownership is clear for temporary manual work.

Check artifact consistency:

- The draft follows provided prototypes, existing PRD files, Jira/prototype links, and latest source material.
- Product taxonomy and system names are accurate.
- One-page documents are concise; full PRDs are complete.

## Severity Guide

- Critical: blocks correct implementation, creates money/status/data inconsistency, or leaves ownership/source-of-truth unclear.
- High: creates major operational burden, edge-case failure, rollout risk, or scope leakage.
- Medium: makes review/implementation harder but has a clear local fix.
- Low: wording, formatting, or minor clarity improvement.

## Avoid

- Do not focus on wording before logic.
- Do not turn review into a full rewrite.
- Do not over-index on compliance unless the user frames the work as compliance-related.
- Do not infer personal traits from document style.
