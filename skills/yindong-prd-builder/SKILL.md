---
name: yindong-prd-builder
description: Build professional product requirement documents and PRD sections from rough Chinese/English notes, prototypes, historical PRDs, meeting notes, or early product ideas. Use when the user asks to write, rewrite, translate, structure, enrich, or polish PRD/BRD/requirement content, especially for complex product, platform capability, workflow, configuration, governance, or cross-system product work.
---

# Yindong PRD Builder

Use this skill to convert rough input into structured, implementation-ready product requirements. Do not simply translate. Understand, reorganize, enrich, and preserve precise scope.

## First Move

Briefly identify:

- business scenario
- platform capability
- involved systems
- current phase and exclusions
- artifact type: full PRD, PRD section, one-page BRD, bilingual draft, English rewrite, table, or flow description

If the user only asks for impact or feasibility, do not draft the PRD yet; use impact analysis first.

## PM Input Normalizer

When input is vague, non-technical, or written as scattered notes, first translate it into engineering-readable product decisions before drafting. Do not require the user to use technical vocabulary.

Use this lightweight output when decisions are missing:

```md
Known Decisions
- ...

Missing Decisions
- ...

Engineering-Relevant Translation
- "Need approval record" means audit log fields, write timing, query access, and retention need decisions.
- "Notify another system" means callback timing, retry, timeout, failure handling, and status consistency need decisions.
```

Ask business-language questions instead of technical-label questions:

- Instead of "What is the idempotency key?", ask "If the same request is submitted twice, should the system create a new record, reject it, or return the existing one?"
- Instead of "What is the callback retry strategy?", ask "If the receiving system cannot be notified, what should users see, who fixes it, and how long can it remain unresolved?"
- Instead of "Who is the source of truth?", ask "If two systems show different statuses, which one should be trusted?"
- Instead of "What is the compatibility strategy?", ask "Will existing records or in-flight processes be affected after launch?"
- Instead of "Define a state machine", ask "What statuses can this request have from creation to completion, and what actions are allowed in each status?"

## Template Selection

Choose the template by artifact type instead of forcing one heavy structure.

Short feature PRD:

- Background
- Objective
- Scope
- Requirements
- API / Data Changes
- Edge Cases
- Attachment / Links

API / field change note:

- Background
- Changed Contract
- Field Table
- Validation / Default Behavior
- Backward Compatibility
- Downstream Consumers
- Examples

Configuration UI PRD:

- Background
- Goal
- Page Path / Entry
- List Fields
- Filter / Query Behavior
- Create / Edit Behavior
- Validation Rules
- Permission / Audit
- Attachment / Prototype

Migration PRD:

- Background
- Scope
- Source / Target Systems
- Migration Flow
- Data Mapping
- Validation / Reconciliation Checklist
- Cutover / Rollback
- Open Questions

Formula / rule logic PRD:

- Background
- Rule Format
- Field Definitions
- Processing Logic
- Examples
- Edge Cases
- Backward Compatibility

## Default PRD Structure

Use this structure unless the user gives a different template:

1. Background
2. Goal
3. Scope
4. Actors / Systems
5. Overall Flow
6. Flow Details
7. Requirements by System
8. API / Data Changes
9. Scenarios & Edge Cases
10. Rollout / Operations
11. Open Questions
12. Dependencies / Risks

For short sections, keep only the relevant headings but preserve the same thinking order.

## API / Data Table Style

For API or data changes, default to tables with:

- Field
- Data Type / Type
- Mandatory
- Value / Validation
- Description
- Example
- Change Type: new / existing / removed, when relevant
- Owner / Consumer, when ownership matters

## 0-to-1 Platform PRD Additions

For new platform/infrastructure capabilities, add:

- platform direction and design principles
- configuration objects vs runtime objects
- ownership/source-of-truth table
- lifecycle/state machine
- versioning and snapshot behavior
- callback, retry, timeout, and idempotency behavior
- audit/event logging
- permission and source-system isolation
- MVP exclusions and future iteration
- UI/workspace model by role, data scope, and operational region

## Writing Rules

- Convert rough notes into professional English when English output is requested.
- Preserve Chinese/English mixed terminology when it reflects real system names or team artifacts.
- Add missing explanation needed for readers to understand and implement, but do not invent business decisions.
- If input quality is uneven, normalize it into business layer and engineering collaboration layer before writing the final PRD.
- Use numbered hierarchy for reviewability.
- Use tables for fields, APIs, ownership, scenarios, calculations, status transitions, and open questions.
- Separate requirements by system when multiple systems change.
- Keep product-readable sections product-readable; move low-level details into API/data sections or open questions.
- Follow provided prototypes or existing PRD structure when the user says to base work on them.

## Scope Discipline

Always separate:

- `In Scope`
- `Out of Scope`
- `Not Supported in This Phase`
- `Future Iteration`

Do not include future-phase features in current-phase requirements except as explicit exclusions, compatibility notes, or future iteration.

## Flow and Data Requirements

For cross-system work:

- describe creation/query/callback/update/settlement/reconciliation flows separately when relevant
- identify persistence points and status changes
- define configuration-time fields separately from runtime fields
- distinguish snapshot fields from dynamically resolved fields
- use field names carefully; singular/plural naming may encode scope, such as `portalCode` vs `portalCodes`

## Guardrails

- Treat historical PRDs as learning/reference material unless the user asks to rewrite them.
- Do not inject unrelated context from previous projects.
- Do not output code when the user asks for requirements.
- Do not over-polish into marketing language.
- Do not hide open decisions; list them clearly with owner/dependency when known.
