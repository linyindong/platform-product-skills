# RFC Rigor Checklist

Load this for the detailed, per-dimension checks behind `platform-rfc-reviewer`. Apply proportionally to RFC scope; a small-change RFC need not satisfy every line. For each gap, name its product / operational / money / risk consequence.

## 1. Problem, goal, non-goals

- The problem and why-now are stated; the RFC is not a solution in search of a problem.
- Success criteria are explicit and testable.
- Non-goals / out-of-scope are stated so the design isn't judged against things it never intended.

## 2. Design soundness & logical closure

- The proposed design actually solves the stated problem end to end.
- No contradictions between prose, diagrams, data model, API, and examples.
- Assumptions the design rests on are stated and plausible.
- The design is proportional — not over-engineered for the problem, not too thin to hold.

## 3. State & lifecycle

- All states and transitions are enumerated; terminal states defined.
- Illegal / unexpected transitions are rejected or handled, not left undefined.
- Who owns each state change (source of truth) is clear.

## 4. Failure modes (the most common RFC gap)

- Timeout behavior defined for every remote/async call.
- Retry policy: bounded, with backoff; safe to retry (idempotent) or explicitly guarded.
- Partial failure: what state the system is left in, and how it recovers.
- Duplicate / idempotency: duplicate requests or events don't double-apply effects.
- Concurrency / races: simultaneous actors on the same entity are handled (locking, versioning, or ordering).
- Ordering / delivery: at-least-once vs exactly-once assumptions are stated and matched by the design.

## 5. Data consistency & integrity

- Source of truth for each piece of data is unambiguous.
- Transaction boundaries are correct; no cross-service "transaction" that can't hold.
- Eventual-consistency windows are named, with what a reader/consumer sees during them.
- Reconciliation exists for anything that can drift (money, status, cross-system counts).
- Migration/backfill: correct, resumable, verifiable; behavior for in-flight records defined.

## 6. API / contract rigor

- Request/response fully specified: fields, types, mandatory, validation, defaults.
- Error codes/messages enumerated; client behavior per error is clear.
- Versioning & backward compatibility: existing callers keep working, or a migration path exists.
- Downstream consumers identified and given what they need.

## 7. Rollout & reversibility

- Migration / cutover steps are ordered and safe.
- Rollback is possible and described — especially for schema or data-mutating changes.
- Feature flag / dark launch / staged rollout where risk warrants.
- Backfill safety: rate, idempotency, verification, and abort criteria.

## 8. Observability & operability

- Metrics for the new paths and their failure modes.
- Logging/tracing sufficient to debug a production incident.
- Alerts on the conditions that matter (failure rate, backlog, drift).
- Runbook / manual intervention path for the new exception modes.

## 9. Security & compliance (weight up for fintech / back-office)

- Authentication & authorization for new endpoints/actions.
- Audit trail for money/contract/approval/status-changing actions (immutable where required).
- Data sensitivity: PII/financial data handling, masking, retention.
- Regulatory / risk constraints acknowledged where relevant.

## 10. Performance & scale (only when claimed or required)

- Capacity assumptions stated; hotspots / N+1 / fan-out considered.
- SLA / latency / throughput targets, if the product needs them, are addressed.
- Degradation behavior under load.

## 11. Alternatives, dependencies, assumptions

- Alternatives considered, with why the chosen one wins.
- External dependencies and cross-team sequencing identified.
- Unstated assumptions surfaced and validated.

## Severity guide

- **Blocking / High**: design does not close; or a failure / rollback / consistency / contract / security gap that can cause money, contract, approval, status, data, or serious operational damage.
- **Tighten**: a rigor or clarity gap with a clear local fix; won't break correctness but weakens the design or its reviewability.
- **Engineering-choice**: an implementation detail (queue, DB, framework, algorithm, code structure) — raise only when it carries a stated product / operational / cost / risk consequence; otherwise leave to engineering.

## Turning gaps into WT questions

For each Blocking/High or Tighten gap, phrase a meeting-ready question:
- tie it to the concrete risk ("if the callback times out after the ledger write, what state is the ticket in?");
- make it answerable by engineering in the room;
- group by area and rank money/contract/approval/status risks first.
