---
name: yindong-prd-reviewer
description: Review PRDs, product requirement drafts, platform designs, prototypes, and requirement sections with product-logic-first judgment, then assess system ownership, flow completeness, state consistency, data/API readiness, edge cases, operational handling, rollout risk, and RFC/engineering follow-up needs. Use when the user asks to check, review, validate, find gaps, see if logic is closed-loop, score a PRD, or assess whether a PRD is ready for product or engineering review.
---

# Yindong PRD Reviewer

Use this skill in review mode. Prioritize product logic, business closure, scope clarity, ownership, and user/ops outcomes over wording polish or engineering checklist detail. Do not rewrite the document unless the user asks.

First calibrate the review depth. A short feature PRD, implementation note, API change note, one-page alignment doc, and large 0-to-1 platform PRD should not be judged by the same completeness standard.

## Review Stance

Start by judging whether the PRD works as a product document:

- Is the requirement goal clear?
- Is the main flow logically closed?
- Is scope clear?
- Are there logic conflicts?
- Are there fatal product gaps?
- Is it ready for product review, engineering review, or only early discussion?

Keep API fields, error codes, idempotency design, callback retry implementation, storage, queue, job scheduling, and monitoring implementation visible, but classify them as RFC/engineering follow-up unless the missing detail breaks product logic, status consistency, money/contract/approval results, or ownership/source-of-truth decisions.

## Default Output Structure

Use this structure by default:

1. Overall Assessment
2. Fatal Issues / Blocking Items
3. Must Improve
4. Nice to Improve
5. Mid-platform / Engineering RFC Follow-up
6. Open Questions
7. Score / Readiness Judgment

### Overall Assessment

Briefly cover:

- requirement goal clarity
- main-flow closure
- scope clarity
- logic conflicts
- fatal gaps, if any
- product/engineering review readiness
- current score or readiness level when useful

### Fatal Issues / Blocking Items

Use this section only for severe product problems:

- product logic does not close
- business flow breaks
- key owner/source of truth is unclear
- status, money, contract, approval, or operational results may become inconsistent
- core scope is impossible to review because current-phase boundaries are missing

Do not classify every missing API field, error code, or engineering detail as blocking.

### Must Improve

List product-side decisions that must be clarified. Use clear mini-headings instead of making `Issue:` the visual structure.

Preferred format:

```md
**1. Returned resubmission semantics need to be clarified**
Problem:
Why it matters:
Suggested product decision:
```

Suggestions should define business semantics, user/ops-visible behavior, status meaning, source of truth, ownership, acceptance criteria, and manual handling. Do not prescribe engineering implementation unless the user asks.

### Nice to Improve

Use for non-blocking improvements such as clearer scope expression, acceptance scenarios, button/copy naming, future-phase marking, QA cases, table formatting, and reader navigation.

### Mid-platform / Engineering RFC Follow-up

Separate items that should be defined in RFC or engineering design, such as:

- API contract details
- error codes and messages
- idempotency implementation
- callback retry technical strategy
- field tables and schema details
- audit log storage
- snapshot storage design
- permission implementation
- database, queue, job, monitoring, or alerting implementation

Phrase these as follow-up ownership, not PRD failure, unless product semantics depend on them.

### Open Questions

Ask decision-driving questions for product, business, engineering, risk, legal, finance, ops, or external partners. Avoid generic questions.

### Score / Readiness Judgment

When scoring, give a score out of 10 and explain what would move it to the next band. Anchor the score to product logic and review readiness, not writing polish.

## Audience Mode

Choose the output mode based on the user's request and likely audience.

PM-friendly review:

- Use when the document is early, written by a less technical PM, or the user asks for overall quality.
- Start with whether the product logic is understandable and what the next concrete fixes are.
- Translate technical gaps into business consequences.
- Avoid overwhelming the author with a long engineering checklist unless the risk is blocking.

Engineering readiness review:

- Use when the PRD is preparing for engineering review or implementation.
- Be strict about ownership, states, source of truth, business status meaning, data/API readiness, compatibility, migration, rollout, audit, and operational handling.
- Keep findings actionable enough for PM, engineering, QA, and ops to align on what must change.
- Put implementation-specific details into RFC follow-up unless they change product behavior or acceptance.

If the user asks for a score, give a score out of 10 only after judging product logic, business closure, and review readiness. Do not anchor the score to writing polish or RFC-level implementation detail.

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

## Product PRD / Engineering RFC Boundary

PRD should define:

- business semantics
- user/ops-visible result
- business meaning of status changes
- system responsibility boundary
- source of truth
- exception behavior and manual handling policy
- acceptance criteria

RFC or engineering design should define:

- exact API fields and error code list
- database schema
- idempotency implementation
- retry technical strategy
- concrete state-machine implementation
- storage, queue, job scheduling, monitoring, and alerting implementation

During review, point out when RFC must carry an item, but do not treat RFC-level details as PRD blocking items unless the missing decision affects business closure.

## Output Severity

Prefer product-review language over abstract severity labels:

- Fatal / blocking: product logic, core flow, source of truth, owner, or critical status/money/contract/approval result is broken or ambiguous.
- Must improve: product decision must be clarified before engineering can confidently implement.
- Nice to improve: clarity, structure, QA, acceptance, or future-phase improvement.
- RFC follow-up: engineering/design details that should be owned outside the PRD.
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
- Missing API/error-code/storage/retry details are classified as RFC follow-up unless product semantics, status consistency, or acceptance depends on them.

Check operational reality:

- Reconciliation, settlement timing, audit logs, monitoring, exception queues, manual fallback, rollout, and support handling are addressed.
- Migration compatibility and old/new platform behavior are considered.
- Finance/ops ownership is clear for temporary manual work.

Check artifact consistency:

- The draft follows provided prototypes, existing PRD files, Jira/prototype links, and latest source material.
- Product taxonomy and system names are accurate.
- One-page documents are concise; full PRDs are complete.

Check PM accessibility:

- Missing technical concepts are translated into business questions the PM can answer.
- Feedback distinguishes "you must decide the business behavior" from "engineering should design the implementation."
- Review does not punish a simple PRD for lacking platform-level sections when the scope is genuinely simple.

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
- Do not make `Issue / Why it matters / Affected area / Recommended handling` the default visual structure, though you may use those dimensions internally.
- Do not over-penalize a business PRD for missing RFC-level implementation detail.
- Do not prescribe API, database, queue, retry job, or monitoring implementation unless the user explicitly asks for engineering design.
