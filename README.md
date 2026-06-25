# Product Management Agent Skills for PRD, Scope, and Platform Product Work

<a id="english"></a>

Language: [English](#english) | [中文](#中文)

Yindong Skills is a Codex skills library for product managers working on PRD writing, PRD review, MVP scope control, platform product design, and cross-system product collaboration.

It is especially useful for product teams working on complex requirements, platform capabilities, workflow products, internal tools, back-office systems, fintech/platform products, and engineering-readiness review.

The repository currently includes four Codex skills under the Yindong Skills name:

- `yindong-product-operating-system`
- `yindong-prd-builder`
- `yindong-scope-governor`
- `yindong-prd-reviewer`

The goal is not to generate generic PM documentation. The goal is to help AI collaborate with a more stable product operating logic:

- abstract business problems into platform capabilities
- clarify system boundaries and ownership
- prefer reuse before new build
- model flows before writing prose
- cover states, data models, APIs, edge cases, and operational closure
- protect MVP boundaries
- actively challenge gaps during PRD review

## Quick Start: Which Skill Should I Use?

Use these four skills at different stages of a product requirement:

| Situation | Use this skill | What it helps with |
|---|---|---|
| You have not figured out the direction yet | `yindong-product-operating-system` | Clarify the business problem, system boundary, reusable platform capability, flow, ownership, and operating model. |
| You are ready to write the document | `yindong-prd-builder` | Turn rough notes, ideas, meeting notes, or prototypes into a structured PRD/BRD or requirement section. |
| You are unsure whether something belongs in the current phase | `yindong-scope-governor` | Assess MVP scope, hidden complexity, include/defer decisions, and phase boundaries. |
| The document is written and needs review | `yindong-prd-reviewer` | Check logic closure, ownership, flow, data/API readiness, edge cases, operations, rollout risk, and open questions. |

In short:

- Not clear on direction yet: use `product-operating-system`
- Ready to write: use `prd-builder`
- Unsure whether to include it now: use `scope-governor`
- Finished writing and need a review: use `prd-reviewer`

## Use Cases

This skill library is useful for:

- writing PRDs from rough product notes, meeting notes, or prototypes
- reviewing PRDs before product or engineering review
- separating MVP scope from future iterations
- turning business requirements into reusable platform capabilities
- clarifying ownership, source of truth, status, flow, and operational risk
- preparing requirement documents for engineering, QA, operations, risk, finance, or partner review
- working on internal tools, workflow products, back-office systems, and fintech/platform product scenarios

## Best Fit

Best suited for:

- product managers
- platform product managers
- fintech product teams
- internal tool and back-office product teams
- teams working on workflow, approval, configuration, risk, finance, operations, or cross-system products
- product leaders who want AI to support structured thinking, decision quality, and requirement governance

## Not Designed For

These skills are not optimized for:

- consumer marketing copy
- pure UI visual critique
- pure engineering implementation plans
- generic startup idea brainstorming without product or system grounding
- personal profiling or personality analysis

## What This Library Optimizes For

The skills are designed as reusable workflows rather than long prompts. Each skill now emphasizes:

- clear trigger and non-use boundaries
- operating modes for different request types
- explicit output contracts
- quality checks before final output
- routing to the next suitable skill or artifact
- progressive disclosure through optional `references/` files for detailed rubrics and templates

## Keywords

Codex skills, agent skills, product management, product manager AI, PRD, BRD, PRD review, product requirements, MVP scope, scope management, platform product, fintech product, internal tools, back-office systems, workflow systems, product operations, product governance, AI product management.

Suggested GitHub topics:

```text
codex-skills
agent-skills
product-management
prd
prd-review
product-requirements
platform-product
scope-management
mvp
fintech
internal-tools
workflow
back-office
product-ops
```

## Skills

### `yindong-product-operating-system`

Core operating rules for complex product collaboration.

Use for:

- platform capability abstraction
- system-boundary reasoning
- reuse-first design
- flow-first thinking
- operational risk analysis
- MVP boundary control
- decision support
- challenge mode

### `yindong-prd-builder`

Build professional PRDs or requirement sections from rough Chinese/English notes, prototypes, meeting notes, or early ideas.

Use for:

- structured PRD drafting
- English PRD / BRD writing
- 0-to-1 platform requirement framing
- API / Data / Scenario / Ops section structuring
- product-readable requirement enrichment

### `yindong-prd-reviewer`

Review PRDs for product and system completeness.

Use for:

- logic closure review
- ownership review
- flow and state review
- data model review
- API readiness review
- operational gap review
- rollout risk review

### `yindong-scope-governor`

Assess MVP scope, phase boundaries, change impact, and hidden complexity.

Use for:

- MVP vs future iteration decisions
- impact analysis before drafting
- include / defer / placeholder recommendations
- workflow, permission, UI, API, operations, and migration impact checks

## Installation

Clone this repository:

```bash
git clone https://github.com/linyindong/Yindong-skills.git
cd Yindong-skills
```

Copy the desired skill folders into your local Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

You can install all skills, or only copy the ones you want to use.

## How to Use

In Codex, explicitly mention the skill name with `$skill-name`.

Examples:

```text
Use $yindong-product-operating-system to reason through this platform requirement.
Use $yindong-prd-builder to turn these rough notes into a PRD section.
Use $yindong-prd-reviewer to check whether this PRD is logically complete.
Use $yindong-scope-governor to assess whether this change belongs in Phase 1.
```

Chinese prompts also work:

```text
用 $yindong-product-operating-system 帮我从业务问题到平台能力梳理这个需求。
用 $yindong-prd-builder 把下面内容整理成英文 PRD。
用 $yindong-prd-reviewer 检查这份 PRD 是否逻辑闭环。
用 $yindong-scope-governor 判断这个能力是否应该进 Phase 1。
```

## Suggested Workflow

For a new complex requirement:

```text
Use $yindong-product-operating-system to clarify the business problem, system boundary, reusable platform capability, flow, runtime objects, API/data changes, and rollout considerations.
```

For drafting:

```text
Use $yindong-prd-builder to turn the following notes into a structured PRD. Do not simply translate; reorganize and enrich the content where needed.
```

For review:

```text
Use $yindong-prd-reviewer to review this PRD. Focus on logic closure, ownership, flow, data model, edge cases, operations, rollout, and open questions.
```

For scope decisions:

```text
Use $yindong-scope-governor to assess whether this change should be included in the current phase. Give an impact table and a clear include/defer/placeholder recommendation.
```

## Updating

To update an installed skill after this repository changes:

```bash
git pull
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

If you only use one skill, copy only that folder.

## Design Principles

These skills intentionally avoid personal profiling. They focus on observable working behavior and collaboration patterns:

- platform thinking
- scope discipline
- clear ownership
- flow-first product reasoning
- operational sustainability
- direct and structured communication

## License

No license has been added yet.

---

<a id="中文"></a>

# 中文说明：产品经理 Agent Skills，用于 PRD、范围控制和平台型产品协作

语言：[English](#english) | [中文](#中文)

Yindong Skills 是一组面向产品经理的 Codex skills，用于结构化产品协作、PRD 编写、PRD Review、MVP 范围控制、平台型产品设计和跨系统协作。

这个仓库目前包含 4 个 skills：

- `yindong-product-operating-system`
- `yindong-prd-builder`
- `yindong-scope-governor`
- `yindong-prd-reviewer`

这些 skills 主要适用于复杂产品和平台型产品场景，例如：

- 复杂需求从 0 到 1 梳理
- 平台能力抽象
- 跨系统协作
- PRD 编写与审查
- MVP 范围控制
- 产品决策支持
- 产品治理和长期知识沉淀

它们的目标不是生成通用 PM 文档，而是帮助 AI 按照更稳定的产品操作逻辑进行协作：

- 从业务问题抽象到平台能力
- 明确系统边界和 owner
- 优先复用已有能力
- 先梳理 flow，再写需求
- 关注状态、数据模型、API、edge cases 和运营闭环
- 控制 MVP 范围，避免隐藏 scope expansion
- 在 PRD review 中主动挑战逻辑缺口

## 快速理解：什么时候用哪个 Skill？

这 4 个 skills 对应一个需求从想清楚到写出来、控范围、再 review 的不同阶段：

| 场景 | 使用哪个 skill | 它主要帮你做什么 |
|---|---|---|
| 还没想清楚方向 | `yindong-product-operating-system` | 梳理业务问题、系统边界、平台能力、flow、ownership 和运营闭环。 |
| 已经要写文档 | `yindong-prd-builder` | 把粗略想法、会议记录、原型或零散笔记整理成结构化 PRD/BRD。 |
| 不确定要不要做、或本期做多少 | `yindong-scope-governor` | 判断 MVP 范围、隐藏复杂度、include/defer、阶段边界。 |
| 文档写完要检查 | `yindong-prd-reviewer` | 检查逻辑闭环、owner、flow、API/data、edge cases、运营和 rollout 风险。 |

简单记：

- 还没想清楚方向：用 `product-operating-system`
- 已经要写文档：用 `prd-builder`
- 不确定要不要做/本期做多少：用 `scope-governor`
- 文档写完要检查：用 `prd-reviewer`

## 主要使用场景

这组 skills 适合用于：

- 从零散产品笔记、会议记录、原型整理 PRD
- 在产品评审或研发评审前 Review PRD
- 拆分 MVP 范围和 future iteration
- 从业务需求抽象平台能力
- 梳理 ownership、source of truth、状态、flow 和运营风险
- 为研发、QA、运营、风控、财务或外部合作方评审准备需求材料
- 中后台、内部工具、流程产品、金融科技或平台型产品场景

## 最适合的人群和团队

适合：

- 产品经理
- 平台产品经理
- 金融科技产品团队
- 中后台 / 内部工具产品团队
- 做审批、配置、风控、财务、运营、流程或跨系统协作的团队
- 希望 AI 不只是写文档，而是参与结构化思考、决策支持和需求治理的产品负责人

## 不适合的场景

这组 skills 不主要用于：

- 消费品营销文案
- 纯 UI 视觉评审
- 纯研发实现方案
- 没有产品或系统背景的泛创业点子 brainstorming
- 个人画像或性格分析

## 这组 Skills 优化的重点

这组 skills 不是单纯的长 Prompt，而是可复用的工作流。当前版本重点强化：

- 清晰的触发条件和不适用边界
- 针对不同请求类型的 operating modes
- 明确的 output contract
- 输出前的质量检查
- 到下一个合适 skill 或 artifact 的路由
- 通过 `references/` 做渐进式加载，把详细 rubric 和模板放在需要时再读

## 关键词

Codex skills、agent skills、产品经理、AI 产品经理、PRD、BRD、PRD Review、产品需求、MVP 范围控制、scope management、平台型产品、金融科技产品、中后台、内部工具、流程系统、产品运营、产品治理、AI 产品协作。

建议 GitHub topics：

```text
codex-skills
agent-skills
product-management
prd
prd-review
product-requirements
platform-product
scope-management
mvp
fintech
internal-tools
workflow
back-office
product-ops
```

## Skills

### `yindong-product-operating-system`

复杂产品协作的核心操作系统。

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

先 clone 这个仓库：

```bash
git clone https://github.com/linyindong/Yindong-skills.git
cd Yindong-skills
```

把需要的 skill 文件夹复制到本机 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

可以全部安装，也可以只复制自己需要的 skill。

## 使用方法

在 Codex 中，通过 `$skill-name` 显式调用对应 skill。

示例：

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

## 推荐使用场景

新复杂需求从 0 到 1：

```text
Use $yindong-product-operating-system to clarify the business problem, system boundary, reusable platform capability, flow, runtime objects, API/data changes, and rollout considerations.
```

写 PRD：

```text
Use $yindong-prd-builder to turn the following notes into a structured PRD. Do not simply translate; reorganize and enrich the content where needed.
```

审 PRD：

```text
Use $yindong-prd-reviewer to review this PRD. Focus on logic closure, ownership, flow, data model, edge cases, operations, rollout, and open questions.
```

判断范围：

```text
Use $yindong-scope-governor to assess whether this change should be included in the current phase. Give an impact table and a clear include/defer/placeholder recommendation.
```

## 更新方式

当 GitHub 仓库后续更新后，可以这样更新本机已安装的 skills：

```bash
git pull
cp -R skills/yindong-product-operating-system ~/.codex/skills/
cp -R skills/yindong-prd-builder ~/.codex/skills/
cp -R skills/yindong-prd-reviewer ~/.codex/skills/
cp -R skills/yindong-scope-governor ~/.codex/skills/
```

如果只使用某一个 skill，只复制对应文件夹即可。

## 设计原则

这些 skills 刻意避免个人画像或性格分析，只关注可观察的工作行为和协作模式：

- 平台化思考
- 范围控制
- ownership 清晰
- flow-first 产品推理
- 运营可持续性
- 实用、直接、结构化的沟通

## License

暂未添加 license。
