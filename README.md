# Yindong Codex Skills

Codex skills for structured fintech mid-platform product collaboration.

These skills encode practical collaboration rules for product requirements, platform capability design, PRD review, and MVP scope control. They are designed for senior product work involving cross-system fintech platforms such as lending, payment, approval, ABS, risk, funding, configuration, and operational governance.

## Skills

### `yindong-product-operating-system`

Core operating rules for fintech mid-platform product work.

Use for:

- business problem to platform capability abstraction
- system boundary and ownership reasoning
- reuse-first design
- flow-first thinking
- operational risk analysis
- MVP boundary control
- decision support and challenge mode

### `yindong-prd-builder`

Build professional PRDs or requirement sections from rough notes.

Use for:

- rough Chinese/English notes to structured PRD
- English PRD/BRD drafting
- 0-to-1 platform requirement framing
- API/data/scenario/ops section structuring
- product-readable requirement enrichment

### `yindong-prd-reviewer`

Review PRDs for product/system completeness.

Use for:

- logic closure review
- system ownership review
- flow and state review
- data model adequacy review
- API readiness review
- operational and rollout gap review

### `yindong-scope-governor`

Assess scope, phase boundaries, and hidden complexity.

Use for:

- MVP vs future iteration decisions
- impact analysis before drafting
- include/defer/placeholder recommendations
- workflow, permission, UI, API, and operations impact checks

## Installation

Copy the desired skill folders into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

Then invoke them explicitly in Codex:

```text
Use $yindong-product-operating-system to reason through this platform requirement.
Use $yindong-prd-builder to turn these rough notes into a PRD section.
Use $yindong-prd-reviewer to check whether this PRD is logically complete.
Use $yindong-scope-governor to assess whether this change belongs in Phase 1.
```

## Design Notes

These skills intentionally avoid personal profiling. They focus on observable working behavior:

- platform thinking
- scope discipline
- ownership clarity
- flow-first product reasoning
- operational sustainability
- practical communication patterns

## License

License to be confirmed before public release.

