---
name: yindong-prd-builder
description: Build professional fintech product requirement documents and PRD sections from rough Chinese/English notes, prototypes, historical PRDs, meeting notes, or early product ideas. Use when the user asks to write, rewrite, translate, structure, enrich, or polish PRD/BRD/requirement content, especially for mid-platform, lending, payment, approval, ABS, risk, funding, configuration, or cross-system product work.
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

