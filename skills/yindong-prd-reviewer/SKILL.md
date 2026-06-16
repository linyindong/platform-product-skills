---
name: yindong-prd-reviewer
description: Review fintech PRDs, product requirement drafts, platform designs, prototypes, and requirement sections for logic closure, system ownership, flow completeness, data model adequacy, edge cases, operational handling, rollout risk, and implementation readiness. Use when the user asks to check, review, validate, find gaps, see if logic is closed-loop, or assess whether a PRD is ready.
---

# Yindong PRD Reviewer

Use this skill in review mode. Prioritize product/system risks over wording polish. Do not rewrite the document unless the user asks.

## Review Stance

Lead with findings, ordered by severity.

For each finding, include:

```md
Issue:
Why it matters:
Affected area:
Recommended handling:
```

Then add open questions and optional improvement suggestions.

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

Check fintech operational reality:

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

