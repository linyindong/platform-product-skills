---
name: platform-rfc-reviewer
description: Review an engineering RFC / technical design doc from a PRODUCT MANAGER / product-owner lens — focused on FUNCTION and LOGIC, not engineering internals. Checks whether the design delivers the required functionality, whether its behavior holds together logically, what users/ops see when things go wrong, impact on existing behavior, product-level fallback, and (only when a PRD is provided) alignment with product intent. Produces sharp, product-oriented questions to raise in an RFC working-team (WT) review. Use when the user asks to review / evaluate an RFC or technical design, or prepare for an RFC review meeting. Works with or without a source PRD. This is a product skill: do not dig into technical mechanics. Invoked internally by platform-product-orchestrator, or directly when the user names this skill; for a natural-language request that does not name a skill, platform-product-orchestrator is the entry point.
---

# Platform RFC Reviewer

Review an engineering RFC as a **product manager / product owner**. You care about **function and logic** — does the design actually deliver the required functionality, does its behavior hold together, and are the user/ops-visible outcomes defined. You are **not** the implementing engineer: do not evaluate technical mechanics.

This is a product skill. Staying on function and logic is the point — going deep into engineering internals is off-topic.

Works with or without a source PRD. Many RFCs are engineering-initiated and have no PRD — never demand one or penalize its absence.

## The lens: what you review vs what you leave to engineering

**Review (product / function / logic):**
- Does the design deliver the required function? Nothing needed is silently missing, dropped, or changed.
- Logic closure: the described behavior is internally consistent; states, actions, and outcomes make sense; no contradictions across sections.
- Functional flow & states: the end-to-end behavior works; each state/outcome maps to a real business result; terminal outcomes are defined.
- Failure OUTCOMES (not mechanisms): when a step fails, is the user/ops-visible result defined — what status, what the user sees, who fixes it. Duplicate/re-submit/cancel produce a sensible functional result.
- Impact on existing behavior: does it change or break current functionality; are existing/in-flight cases handled at the behavior level.
- Product-level fallback & rollout: can it be turned off / fall back / be handled manually so the business keeps running — at the outcome level.
- Ownership / source of truth at the business level: who owns each outcome and decision.
- Operability for ops/support: can they handle the new cases; is there audit/traceability where money/approval/status changes (a product/compliance need).
- Scope vs intent: the RFC quietly over- or under-delivers vs the requirement; if a PRD is provided, note deviations.

**Leave to engineering (do NOT evaluate the mechanism):**
- Idempotency/retry implementation, concurrency/locking, transaction boundaries, consistency-algorithm details, DB/queue/framework/algorithm choices, schema, performance internals.
- Touch these ONLY by asking whether the **functional/product outcome** is defined (e.g. "if the same request comes twice, does the user end up with one ticket or two?"), never by critiquing or prescribing the technical approach.

## Operating Modes

- Function & logic review (default): does the design deliver the function and hold together.
- WT prep: focus the output on the product-oriented questions to ask in the meeting.
- PRD-alignment pass: only when the user supplies a PRD — compare against product intent (a comparison, not a gate).
- Calibration: a small-change RFC and a 0-to-1 / cross-system RFC are not held to the same bar.

## Step 0: Calibration

- RFC type/scope: small change, feature, cross-system, migration/data change, integration.
- Is a source PRD provided? If yes → add the alignment pass. If no → review on its own merits; do not say "missing PRD."
- Review goal: function/logic, risk surfacing, WT prep, or PRD alignment.

## When NOT to Use

- To author or rewrite the RFC — engineering's job.
- Pure PRD review → `platform-prd-reviewer`. Current-phase / MVP scope → `platform-scope-checker`. Flow/state closure specialist pass → `platform-flow-modeler`.

## Output Structure

1. **Overall Assessment** — does the design deliver the function and hold together logically? ready / needs clarification / has gaps, calibrated to scope. Name the single biggest product risk.
2. **Blocking Gaps** — the design doesn't deliver a required function, the logic doesn't close, a failure has no defined user/ops outcome, or existing behavior would break — anything that hits the business result (money / contract / approval / status / user experience).
3. **Should Clarify** — functional edge cases, undefined outcomes, ownership, scope drift; fixable without redesign.
4. **PRD Alignment Notes** — only if a PRD was provided.
5. **Questions for the RFC WT** — the key output. Sharp, product-oriented, decision-driving questions grouped by area, each tied to a functional/business risk (see below).
6. **Open Questions / Risks** — with owner or decision role where known.

## Questions for the RFC WT

Give the user a ready-to-use question set for the meeting, in product language:

- Each ties to a functional/business risk and is answerable in the room — prefer "if the callback to the portal fails, what status does the applicant see and who resolves it?" over anything about retry mechanics.
- Group by area: functionality coverage / logic & states / failure outcomes / impact on existing users / rollout & fallback / ownership & audit.
- Rank by impact; put money / contract / approval / status / user-facing risks first.
- Do not ask about implementation trivia (idempotency keys, queue choice, schema) — that's engineering's call.

## Severity

- Blocking: a required function isn't delivered, logic doesn't close, a failure/edge case has no defined business outcome, or existing behavior breaks.
- Should clarify: a functional gap or ambiguity with a clear product answer.
- Engineering's call: an implementation detail — mention only if a functional/product outcome depends on it, framed as the outcome question.

## Common Mistakes to Flag in the RFC (product lens)

- Happy-path only: no defined outcome when a step fails (what does the user/ops see?).
- Logic that doesn't close: states/actions/outcomes contradict across the doc.
- A required function silently missing, dropped, or quietly changed vs the intent.
- Existing behavior or in-flight cases not addressed.
- No product-level fallback / off-switch for a risky change.
- Ambiguous ownership / source of truth for a business outcome.
- No audit/traceability where money / approval / status changes.

## Common Mistakes for the Reviewer to Avoid

- Do NOT dig into technical mechanics (idempotency, concurrency, transactions, DB/queue/perf) — this is a product skill; that's off-topic and engineering's domain.
- Do not demand a PRD or penalize its absence.
- Do not drown the WT in nitpicks — lead with the few product-risk items and the sharpest questions.
- Do not rewrite the RFC; review it.
- Do not overclaim "missing" when the detail may be in a diagram/appendix/linked doc not provided.

## Routing

- `platform-prd-reviewer` for the product-document side · `platform-scope-checker` for scope questions the RFC exposes · `platform-flow-modeler` when flow/state closure needs a specialist pass · `platform-product-guide` when the RFC exposes unresolved product direction/ownership.

## References

- `references/rfc-rigor-checklist.md`: load for the detailed function/logic checklist and severity guidance.
