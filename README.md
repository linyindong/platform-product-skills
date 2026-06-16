# Yindong Codex Skills

用于结构化金融科技中台产品协作的 Codex Skills。

Codex skills for structured fintech mid-platform product collaboration.

## 中文说明

这个仓库沉淀了一组 Codex skills，用于支持复杂产品需求、平台能力设计、PRD 编写与审查、MVP 范围控制等工作。

这些 skills 主要适用于金融科技中台类产品场景，例如：

- Lending / Credit
- Payment / Repayment
- Approval Center
- ABS / Funding
- Risk
- Configuration Platform
- Cross-system Product Governance

它们的目标不是生成通用 PM 文档，而是帮助 AI 按照更稳定的产品操作逻辑进行协作：

- 从业务问题抽象到平台能力
- 明确系统边界和 owner
- 优先复用已有能力
- 先梳理 flow，再写需求
- 关注状态、数据模型、API、edge cases 和运营闭环
- 控制 MVP 范围，避免隐藏 scope expansion
- 在 PRD review 中主动挑战逻辑缺口

## Skills

### `yindong-product-operating-system`

金融科技中台产品协作的核心操作系统。

适用于：

- 从业务问题抽象平台能力
- 梳理系统边界和 ownership
- 判断复用已有能力还是新建能力
- 进行 flow-first 产品思考
- 分析运营风险和 rollout 风险
- 做 MVP 范围控制
- 做决策支持和 challenge review

### `yindong-prd-builder`

把粗颗粒度想法、中文/英文笔记、会议记录或原型内容整理成专业 PRD 或 requirement section。

适用于：

- rough notes 到结构化 PRD
- 英文 PRD / BRD 起草
- 0-to-1 平台能力需求框架搭建
- API / Data / Scenario / Ops 章节整理
- 产品可读、研发可执行的需求文档补全

### `yindong-prd-reviewer`

审查 PRD 是否具备产品和系统层面的完整性。

适用于：

- 检查逻辑是否闭环
- 检查系统 ownership 是否清晰
- 检查 flow、状态机和 edge cases
- 检查数据模型是否支撑前端/运营/下游需要
- 检查 API readiness
- 检查 reconciliation、audit、rollout、manual fallback 等运营缺口

### `yindong-scope-governor`

判断需求是否应进入当前 phase，并评估隐藏复杂度。

适用于：

- MVP vs future iteration 判断
- 写 PRD 前先做影响分析
- 判断 include / defer / placeholder
- 评估 workflow、permission、UI、API、operations、migration 影响

## 安装方式

把需要的 skill 文件夹复制到本机 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

在 Codex 中可以显式调用：

```text
Use $yindong-product-operating-system to reason through this platform requirement.
Use $yindong-prd-builder to turn these rough notes into a PRD section.
Use $yindong-prd-reviewer to check whether this PRD is logically complete.
Use $yindong-scope-governor to assess whether this change belongs in Phase 1.
```

中文请求也可以直接使用：

```text
用 $yindong-product-operating-system 帮我从业务问题到平台能力梳理这个需求。
用 $yindong-prd-builder 把下面内容整理成英文 PRD。
用 $yindong-prd-reviewer 检查这份 PRD 是否逻辑闭环。
用 $yindong-scope-governor 判断这个能力是否应该进 Phase 1。
```

## 设计原则

这些 skills 刻意避免个人画像或性格分析，只关注可观察的工作行为和协作模式：

- 平台化思考
- 范围控制
- ownership 清晰
- flow-first 产品推理
- 运营可持续性
- 实用、直接、结构化的沟通

## English

This repository contains Codex skills for complex fintech mid-platform product work, including product requirements, platform capability design, PRD drafting and review, and MVP scope control.

They are designed for cross-system product scenarios such as lending, payment, approval, ABS, funding, risk, configuration platforms, and product governance.

The goal is not to generate generic PM documentation. The goal is to help AI collaborate with a more stable product operating logic:

- abstract business problems into platform capabilities
- clarify system boundaries and ownership
- prefer reuse before new build
- model flows before writing prose
- cover states, data models, APIs, edge cases, and operational closure
- protect MVP boundaries
- actively challenge gaps during PRD review

## English Skill Summary

### `yindong-product-operating-system`

Core operating rules for fintech mid-platform product collaboration.

Use for platform capability abstraction, system-boundary reasoning, reuse-first design, flow-first thinking, operational risk analysis, MVP boundary control, decision support, and challenge mode.

### `yindong-prd-builder`

Build professional PRDs or requirement sections from rough Chinese/English notes, prototypes, meeting notes, or early ideas.

Use for structured PRD drafting, English PRD/BRD writing, 0-to-1 platform requirement framing, API/data/scenario/ops section structuring, and product-readable requirement enrichment.

### `yindong-prd-reviewer`

Review PRDs for product and system completeness.

Use for logic closure review, ownership review, flow/state review, data model review, API readiness review, operational gap review, and rollout risk review.

### `yindong-scope-governor`

Assess MVP scope, phase boundaries, change impact, and hidden complexity.

Use before drafting when deciding whether a change belongs in the current phase, should be simplified, deferred, or represented as a future-compatible placeholder.

## License

No license has been added yet.

