# RFC Review Checklist (product / function / logic lens)

Load this for the detailed checks behind `platform-rfc-reviewer`. This is a PRODUCT skill: every check is about function, logic, or the user/ops-visible outcome — not about the engineering mechanism. Apply proportionally to RFC scope. For each gap, name its product / business consequence.

## 1. Delivers the function

- The design actually produces the required behavior/outcome, end to end.
- Nothing required is silently missing, dropped, or quietly changed.
- It doesn't over-deliver (unrequested behavior sneaking in) or under-deliver vs the intent.

## 2. Logic closure

- The described behavior is internally consistent — prose, diagrams, and examples agree.
- Every state/action maps to a real business result; no contradictions.
- Assumptions the behavior rests on are stated and plausible.

## 3. Functional flow & states

- The end-to-end flow works and matches how the business actually operates.
- States and transitions correspond to meaningful business outcomes; terminal outcomes defined.
- Who is responsible for each outcome / decision (source of truth at the business level) is clear.

## 4. Failure outcomes (WHAT the user/ops sees, not HOW it's handled)

- When a step fails, the user/ops-visible result is defined: what status, what message, what next.
- Duplicate submission / re-submit / cancel produce a sensible functional result.
- Someone owns resolving a stuck/failed case; there's a path back to a good state.
- (Do not evaluate retry/idempotency mechanics — only whether the outcome is defined.)

## 5. Impact on existing behavior

- Existing functionality isn't broken or silently changed.
- In-flight / existing records have defined behavior after the change.
- Downstream/other teams that rely on current behavior are considered.

## 6. Rollout & fallback (outcome level)

- There's a way to turn it off, fall back, or handle manually so the business keeps running.
- For a risky or data-changing change, the product-continuity story is clear (not the migration script).

## 7. Operability & audit (product/compliance need)

- Ops/support can handle the new cases (visibility, a manual path).
- Audit / traceability exists where money, contract, approval, or status changes.

## 8. Scope vs intent (and PRD alignment if provided)

- The RFC's scope matches the requirement; note silent additions/removals.
- If a PRD is provided, flag deviations, gaps (a requirement with no design), or changed behavior. Comparison, not a gate.

## Severity guide

- **Blocking**: a required function isn't delivered; logic doesn't close; a failure/edge case has no defined business outcome; existing behavior breaks — i.e. the business result (money / contract / approval / status / user experience) is at risk.
- **Should clarify**: a functional gap or ambiguity with a clear product answer; won't break the outcome but leaves it underspecified.
- **Engineering's call**: an implementation detail (idempotency, concurrency, transactions, DB/queue/framework, performance, schema) — raise ONLY if a functional/product outcome depends on it, and frame it as the outcome question, never as a critique of the mechanism.

## Turning gaps into WT questions

For each Blocking / Should-clarify gap, phrase a meeting-ready, product-language question:
- tie it to the business consequence ("if notifying the portal fails after approval, what status does the applicant see and who fixes it?");
- make it answerable by engineering in the room;
- group by area and rank money / contract / approval / status / user-facing risks first;
- never ask about implementation trivia.
