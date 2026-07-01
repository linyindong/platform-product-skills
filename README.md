# Platform Product Skills

<a id="english"></a>

Language: [English](#english) | [中文](#中文)

Platform Product Skills is a Codex skills library for platform, back-office, workflow, and fintech product teams working on PRD writing, PRD review, MVP scope control, and cross-system product collaboration.

It is especially useful for product teams working on complex requirements, platform capabilities, workflow products, internal tools, back-office systems, fintech/platform products, and engineering-readiness review.

The repository currently includes four core Codex skills and one specialist flow-modeling skill:

- `platform-product-guide`
- `platform-prd-builder`
- `platform-scope-checker`
- `platform-prd-reviewer`
- `platform-flow-modeler`

The goal is not to generate generic PM documentation. The goal is to help AI collaborate with a more stable product operating logic:

- abstract business problems into platform capabilities
- clarify system boundaries and ownership
- prefer reuse before new build
- model flows before writing prose
- cover states, data models, APIs, edge cases, and operational closure
- protect MVP boundaries
- actively challenge gaps during PRD review

## Quick Start: Which Skill Should I Use?

Use these skills at different stages of a product requirement:

| Situation | Use this skill | What it helps with |
|---|---|---|
| You have not figured out the direction yet | `platform-product-guide` | Clarify the business problem, system boundary, reusable platform capability, flow, ownership, and operating model. |
| You are ready to write the document | `platform-prd-builder` | Turn rough notes, ideas, meeting notes, or prototypes into a structured PRD/BRD or requirement section. |
| You are unsure whether something belongs in the current phase | `platform-scope-checker` | Assess MVP scope, hidden complexity, include/defer decisions, and phase boundaries. |
| The document is written and needs review | `platform-prd-reviewer` | Check logic closure, ownership, flow, data/API readiness, edge cases, operations, rollout risk, and open questions. |
| You need to model flows, states, or exception paths | `platform-flow-modeler` | Model main flows, exception flows, state transitions, callbacks, rollback, reconciliation, and manual fallback. |

In short:

- Not clear on direction yet: use `platform-product-guide`
- Ready to write: use `platform-prd-builder`
- Unsure whether to include it now: use `platform-scope-checker`
- Finished writing and need a review: use `platform-prd-reviewer`
- Need to model flow/state paths: use `platform-flow-modeler`

## What You Get From Each Skill

| Skill | How to use it | Expected output |
|---|---|---|
| `platform-product-guide` | Use it when the problem is still blurry or the system direction needs shaping. Provide the business context, rough idea, or stakeholder ask. | A structured product direction: business problem, platform capability, system boundary, ownership, flow, key tradeoffs, open decisions, and next recommended artifact. |
| `platform-prd-builder` | Use it when you already want to write or improve a PRD. Provide notes, meeting summaries, prototypes, existing drafts, or section goals. | A product-readable and engineering-ready PRD or requirement section, with scope, actors/systems, flows, requirements, API/data impact, edge cases, operations, risks, and open questions. |
| `platform-scope-checker` | Use it before committing a change to the current phase. Provide the proposed change, current phase goal, and known constraints. | A clear include/simplify/validate/defer/reject recommendation, plus impact table, biggest risk, MVP boundary, and next validation or documentation step. |
| `platform-prd-reviewer` | Use it after a PRD or draft exists. Provide the document and the desired review depth. | A product-logic-first review with overall readiness, blocking issues if any, must-fix product gaps, nice-to-improve items, RFC follow-up, open questions, and score/readiness judgment. |
| `platform-flow-modeler` | Use it directly when flows are complex, or let the other skills call it for flow-heavy sections. Provide the scenario, systems, states, and known exceptions. | A flow model with actors/systems, main flow, exception flows, state transitions, callback/retry/timeout behavior, rollback, reconciliation, manual fallback, and open flow questions. |

For best results, tell Codex the artifact type and review goal. For example: "This is a short feature PRD, please review for product logic and engineering readiness" or "This is a 0-to-1 platform PRD, please review strictly."

## Use Cases

This skill library is useful for:

- writing PRDs from rough product notes, meeting notes, or prototypes
- reviewing PRDs before product or engineering review
- separating MVP scope from future iterations
- modeling flows, states, callbacks, rollback, reconciliation, and manual fallback
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
flow-modeling
state-management
```

## Skills

### `platform-product-guide`

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

### `platform-prd-builder`

Build professional PRDs or requirement sections from rough Chinese/English notes, prototypes, meeting notes, or early ideas.

Use for:

- structured PRD drafting
- English PRD / BRD writing
- 0-to-1 platform requirement framing
- API / Data / Scenario / Ops section structuring
- product-readable requirement enrichment

### `platform-prd-reviewer`

Review PRDs for product and system completeness.

Use for:

- logic closure review
- ownership review
- flow and state review
- data model review
- API readiness review
- operational gap review
- rollout risk review

### `platform-scope-checker`

Assess MVP scope, phase boundaries, change impact, and hidden complexity.

Use for:

- MVP vs future iteration decisions
- impact analysis before drafting
- include / defer / placeholder recommendations
- workflow, permission, UI, API, operations, and migration impact checks

### `platform-flow-modeler`

Model cross-system flows, states, exception paths, and operational closure.

Use for:

- main flow and exception flow modeling
- lifecycle and state transition tables
- callback / retry / timeout clarification
- rollback / cancellation / resubmission semantics
- reconciliation, migration, and manual fallback paths
- flow evidence for PRD writing, scope decisions, and PRD review

## Installation

Clone this repository:

```bash
git clone https://github.com/linyindong/platform-product-skills.git
cd platform-product-skills
```

Copy the desired skill folders into your local Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/platform-product-guide ~/.codex/skills/
cp -R skills/platform-prd-builder ~/.codex/skills/
cp -R skills/platform-prd-reviewer ~/.codex/skills/
cp -R skills/platform-scope-checker ~/.codex/skills/
cp -R skills/platform-flow-modeler ~/.codex/skills/
```

You can install all skills, or only copy the ones you want to use.

## How to Use

In Codex, explicitly mention the skill name with `$skill-name`.

Examples:

```text
Use $platform-product-guide to reason through this platform requirement.
Use $platform-prd-builder to turn these rough notes into a PRD section.
Use $platform-prd-reviewer to check whether this PRD is logically complete.
Use $platform-scope-checker to assess whether this change belongs in Phase 1.
Use $platform-flow-modeler to model the main flow, exception flows, state transitions, callbacks, rollback, and reconciliation.
```

Chinese prompts also work:

```text
用 $platform-product-guide 帮我从业务问题到平台能力梳理这个需求。
用 $platform-prd-builder 把下面内容整理成英文 PRD。
用 $platform-prd-reviewer 检查这份 PRD 是否逻辑闭环。
用 $platform-scope-checker 判断这个能力是否应该进 Phase 1。
用 $platform-flow-modeler 梳理 main flow、exception flow、状态流转、callback、rollback 和 reconciliation。
```

## Example Prompts

```text
Use $platform-product-guide to clarify this cross-system requirement before we write a PRD.
Use $platform-prd-builder to turn these meeting notes into a platform PRD.
Use $platform-scope-checker to decide whether this workflow change belongs in MVP.
Use $platform-prd-reviewer to review this PRD for product logic and engineering readiness.
Use $platform-flow-modeler to model the lifecycle, exception paths, callbacks, rollback, and manual fallback for this cross-system workflow.
```

For stronger results, include the product context, current phase, target audience, and whether you want a quick pass or a strict review.

## Works With

This repo is Codex-native. The skills are written in Codex `SKILL.md` format and can be installed into `~/.codex/skills`.

They can also be reused as structured markdown instructions in other AI agents that support custom skills, project instructions, or file-based context. In those environments, load or paste the relevant `SKILL.md` and ask the agent to follow it.

## Suggested Workflow

This is the recommended sequence for a new complex platform requirement, from ambiguity to reviewed PRD. Steps 2 and 4 are optional, and you can enter at any step.

```text
Step 1  Direction unclear?
        -> platform-product-guide
        Clarify business problem, system boundary, reusable capability,
        flow direction, ownership, and rollout considerations.
        Output: decision brief, assumption list, or flow sketch.

Step 2  Need to model flows before writing?
        -> platform-flow-modeler
        Model main flow, exception flows, state transitions, callbacks,
        rollback, reconciliation, and open flow questions.
        Output: flow tables, state transition, open decisions.
        Skip if the requirement has no meaningful cross-system flow complexity.

Step 3  Ready to write the PRD?
        -> platform-prd-builder
        Turn flow model, notes, prototypes, or meeting inputs into a
        structured PRD or requirement section.
        Output: product-readable, engineering-reviewable PRD with
        scenarios, acceptance criteria, and open questions.

Step 4  Unsure whether to include something in this phase?
        -> platform-scope-checker
        Get a verdict: Include / Simplify / Validate / Defer / Reject,
        with impact table and MVP boundary.
        Use before Step 3 or mid-draft when scope questions arise.

Step 5  PRD written and needs a quality check?
        -> platform-prd-reviewer
        Review for document quality, logic closure, ownership, flow
        completeness, data/API readiness, operations, and RFC follow-up.
        Output: Overall Assessment, Fatal Issues, Must Improve, Score.
```

Quick reference:

| Situation | Skill |
|---|---|
| Direction and system framing unclear | `platform-product-guide` |
| 3+ systems, callbacks, or state transitions involved | `platform-flow-modeler` |
| Ready to draft a PRD or requirement section | `platform-prd-builder` |
| Unsure whether this belongs in the current phase | `platform-scope-checker` |
| PRD written; need a review before product or engineering review | `platform-prd-reviewer` |

Typical prompts:

Direction:

```text
Use $platform-product-guide to clarify the business problem, system boundary, reusable platform capability, flow, runtime objects, API/data changes, and rollout considerations.
```

Flow:

```text
Use $platform-flow-modeler to model the main flow, exception flows, state transitions, callbacks, rollback, reconciliation, and open flow questions before we write the PRD.
```

PRD:

```text
Use $platform-prd-builder to turn the following notes into a structured PRD. Do not simply translate; reorganize and enrich the content where needed.
```

Scope:

```text
Use $platform-scope-checker to assess whether this change should be included in the current phase. Give an impact table and a clear include/defer/placeholder recommendation.
```

Review:

```text
Use $platform-prd-reviewer to review this PRD. Focus on logic closure, ownership, flow, data model, edge cases, operations, rollout, and open questions.
```

## Updating

To update an installed skill after this repository changes:

```bash
git pull
cp -R skills/platform-product-guide ~/.codex/skills/
cp -R skills/platform-prd-builder ~/.codex/skills/
cp -R skills/platform-prd-reviewer ~/.codex/skills/
cp -R skills/platform-scope-checker ~/.codex/skills/
cp -R skills/platform-flow-modeler ~/.codex/skills/
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

# 中文说明：平台型产品 Skills

语言：[English](#english) | [中文](#中文)

Platform Product Skills 是一组面向平台型产品、中后台、流程产品和金融科技产品团队的 Codex skills，用于结构化产品协作、PRD 编写、PRD Review、MVP 范围控制和跨系统协作。

这个仓库目前包含 4 个核心 skills 和 1 个专项 flow skill：

- `platform-product-guide`
- `platform-prd-builder`
- `platform-scope-checker`
- `platform-prd-reviewer`
- `platform-flow-modeler`

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

这些 skills 对应一个需求从想清楚到写出来、控范围、建模 flow、再 review 的不同阶段：

| 场景 | 使用哪个 skill | 它主要帮你做什么 |
|---|---|---|
| 还没想清楚方向 | `platform-product-guide` | 梳理业务问题、系统边界、平台能力、flow、ownership 和运营闭环。 |
| 已经要写文档 | `platform-prd-builder` | 把粗略想法、会议记录、原型或零散笔记整理成结构化 PRD/BRD。 |
| 不确定要不要做、或本期做多少 | `platform-scope-checker` | 判断 MVP 范围、隐藏复杂度、include/defer、阶段边界。 |
| 文档写完要检查 | `platform-prd-reviewer` | 检查逻辑闭环、owner、flow、API/data、edge cases、运营和 rollout 风险。 |
| 需要梳理 flow、状态或异常路径 | `platform-flow-modeler` | 梳理 main flow、exception flow、state transition、callback、rollback、reconciliation 和 manual fallback。 |

简单记：

- 还没想清楚方向：用 `platform-product-guide`
- 已经要写文档：用 `platform-prd-builder`
- 不确定要不要做/本期做多少：用 `platform-scope-checker`
- 文档写完要检查：用 `platform-prd-reviewer`
- 需要梳理 flow/state 路径：用 `platform-flow-modeler`

## 每个 Skill 使用后会得到什么？

| Skill | 怎么使用 | 预期输出 |
|---|---|---|
| `platform-product-guide` | 当问题还没想清楚，或系统方向需要梳理时使用。提供业务背景、粗略想法或 stakeholder ask。 | 一份结构化产品方向：业务问题、平台能力、系统边界、ownership、flow、关键 tradeoff、开放决策和下一步建议产物。 |
| `platform-prd-builder` | 已经准备写 PRD 或优化文档时使用。提供笔记、会议记录、原型、已有草稿或章节目标。 | 一份产品可读、研发可评审的 PRD 或 requirement section，包含 scope、actors/systems、flows、requirements、API/data impact、edge cases、operations、risks 和 open questions。 |
| `platform-scope-checker` | 在决定某个改动是否进入当前 phase 前使用。提供 proposed change、当前 phase goal 和已知约束。 | 一个明确的 include/simplify/validate/defer/reject 建议，并附 impact table、biggest risk、MVP boundary 和下一步验证或文档动作。 |
| `platform-prd-reviewer` | 已经有 PRD 或草稿后使用。提供文档和希望 review 的深度。 | 一份 product-logic-first review，包含 overall readiness、blocking issues、must-fix product gaps、nice-to-improve、RFC follow-up、open questions 和 score/readiness judgment。 |
| `platform-flow-modeler` | flow 比较复杂时直接使用，也可以被其他 skills 在 flow-heavy 章节中调用。提供场景、系统、状态和已知异常。 | 一份 flow model，包含 actors/systems、main flow、exception flows、state transitions、callback/retry/timeout、rollback、reconciliation、manual fallback 和 open flow questions。 |

效果更好的做法：告诉 Codex 文档类型和 review 目标。例如：“这是一个短小功能 PRD，重点看产品逻辑和研发评审准备度”，或者“这是一个 0-to-1 平台 PRD，请严格 review”。

## 主要使用场景

这组 skills 适合用于：

- 从零散产品笔记、会议记录、原型整理 PRD
- 在产品评审或研发评审前 Review PRD
- 拆分 MVP 范围和 future iteration
- 梳理跨系统 flow、状态流转、callback、rollback、reconciliation 和 manual fallback
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
flow-modeling
state-management
```

## Skills

### `platform-product-guide`

复杂产品协作的核心操作系统。

适用于：

- 从业务问题抽象平台能力
- 梳理系统边界和 ownership
- 判断复用已有能力还是新建能力
- 进行 flow-first 产品思考
- 分析运营风险和 rollout 风险
- 做 MVP 范围控制
- 做决策支持和 challenge review

### `platform-prd-builder`

把粗颗粒度想法、中文/英文笔记、会议记录或原型内容整理成专业 PRD 或 requirement section。

适用于：

- rough notes 到结构化 PRD
- 英文 PRD / BRD 起草
- 0-to-1 平台能力需求框架搭建
- API / Data / Scenario / Ops 章节整理
- 产品可读、研发可执行的需求文档补全

### `platform-prd-reviewer`

审查 PRD 是否具备产品和系统层面的完整性。

适用于：

- 检查逻辑是否闭环
- 检查系统 ownership 是否清晰
- 检查 flow、状态机和 edge cases
- 检查数据模型是否支撑前端/运营/下游需要
- 检查 API readiness
- 检查 reconciliation、audit、rollout、manual fallback 等运营缺口

### `platform-scope-checker`

判断需求是否应进入当前 phase，并评估隐藏复杂度。

适用于：

- MVP vs future iteration 判断
- 写 PRD 前先做影响分析
- 判断 include / defer / placeholder
- 评估 workflow、permission、UI、API、operations、migration 影响

### `platform-flow-modeler`

梳理跨系统 flow、状态、异常路径和运营闭环。

适用于：

- main flow 和 exception flow 建模
- lifecycle 和 state transition 表格
- callback / retry / timeout 梳理
- rollback / cancellation / resubmission 语义定义
- reconciliation、migration 和 manual fallback 路径
- 为 PRD 编写、范围判断、PRD review 提供 flow evidence

## 安装方式

先 clone 这个仓库：

```bash
git clone https://github.com/linyindong/platform-product-skills.git
cd platform-product-skills
```

把需要的 skill 文件夹复制到本机 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R skills/platform-product-guide ~/.codex/skills/
cp -R skills/platform-prd-builder ~/.codex/skills/
cp -R skills/platform-prd-reviewer ~/.codex/skills/
cp -R skills/platform-scope-checker ~/.codex/skills/
cp -R skills/platform-flow-modeler ~/.codex/skills/
```

可以全部安装，也可以只复制自己需要的 skill。

## 使用方法

在 Codex 中，通过 `$skill-name` 显式调用对应 skill。

示例：

```text
Use $platform-product-guide to reason through this platform requirement.
Use $platform-prd-builder to turn these rough notes into a PRD section.
Use $platform-prd-reviewer to check whether this PRD is logically complete.
Use $platform-scope-checker to assess whether this change belongs in Phase 1.
Use $platform-flow-modeler to model the main flow, exception flows, state transitions, callbacks, rollback, and reconciliation.
```

中文请求也可以直接使用：

```text
用 $platform-product-guide 帮我从业务问题到平台能力梳理这个需求。
用 $platform-prd-builder 把下面内容整理成英文 PRD。
用 $platform-prd-reviewer 检查这份 PRD 是否逻辑闭环。
用 $platform-scope-checker 判断这个能力是否应该进 Phase 1。
用 $platform-flow-modeler 梳理 main flow、exception flow、状态流转、callback、rollback 和 reconciliation。
```

## 示例 Prompt

```text
Use $platform-product-guide to clarify this cross-system requirement before we write a PRD.
Use $platform-prd-builder to turn these meeting notes into a platform PRD.
Use $platform-scope-checker to decide whether this workflow change belongs in MVP.
Use $platform-prd-reviewer to review this PRD for product logic and engineering readiness.
Use $platform-flow-modeler to model the lifecycle, exception paths, callbacks, rollback, and manual fallback for this cross-system workflow.
```

效果更好的做法：同时提供产品背景、当前 phase、目标读者，以及你希望快速看一遍还是严格 review。

## 支持哪些工具？

这个仓库是 Codex-native 的。Skills 使用 Codex `SKILL.md` 格式，可以安装到 `~/.codex/skills`。

如果其他 AI 工具支持 custom skills、project instructions 或基于文件的上下文，也可以复用这些 skills。使用方式是读取或粘贴对应的 `SKILL.md`，并要求 AI 按其中规则执行。

## 推荐使用场景

这是一个复杂平台型需求从模糊到 PRD review 的推荐流程。Step 2 和 Step 4 可选，也可以从任意步骤进入。

```text
Step 1  方向还不清楚？
        -> platform-product-guide
        梳理业务问题、系统边界、可复用平台能力、
        flow 方向、ownership 和 rollout 考虑。
        输出：decision brief、assumption list 或 flow sketch。

Step 2  写 PRD 前需要先建模 flow？
        -> platform-flow-modeler
        梳理 main flow、exception flow、state transition、
        callback、rollback、reconciliation 和 open questions。
        输出：flow tables、state transition、open decisions。
        如果没有明显跨系统 flow 复杂度，可以跳过。

Step 3  已经准备写 PRD？
        -> platform-prd-builder
        把 flow model、笔记、原型或会议输入整理成
        结构化 PRD 或 requirement section。
        输出：产品可读、研发可评审的 PRD，包含 scenarios、
        acceptance criteria 和 open questions。

Step 4  不确定是否放进当前 phase？
        -> platform-scope-checker
        得到 Include / Simplify / Validate / Defer / Reject 判断，
        并附 impact table 和 MVP boundary。
        可在 Step 3 前使用，也可在写 PRD 中途使用。

Step 5  PRD 写完需要质量检查？
        -> platform-prd-reviewer
        检查文档质量、逻辑闭环、ownership、flow 完整度、
        data/API readiness、operations 和 RFC follow-up。
        输出：Overall Assessment、Fatal Issues、Must Improve、Score。
```

快速参考：

| 场景 | Skill |
|---|---|
| 方向和系统框架还不清楚 | `platform-product-guide` |
| 涉及 3+ 系统、callback 或状态流转 | `platform-flow-modeler` |
| 准备写 PRD 或 requirement section | `platform-prd-builder` |
| 不确定是否进入当前 phase | `platform-scope-checker` |
| PRD 已写完，需要产品/研发评审前检查 | `platform-prd-reviewer` |

典型 prompt：

方向：

```text
Use $platform-product-guide to clarify the business problem, system boundary, reusable platform capability, flow, runtime objects, API/data changes, and rollout considerations.
```

Flow：

```text
Use $platform-flow-modeler to model the main flow, exception flows, state transitions, callbacks, rollback, reconciliation, and open flow questions before we write the PRD.
```

PRD：

```text
Use $platform-prd-builder to turn the following notes into a structured PRD. Do not simply translate; reorganize and enrich the content where needed.
```

Scope：

```text
Use $platform-scope-checker to assess whether this change should be included in the current phase. Give an impact table and a clear include/defer/placeholder recommendation.
```

Review：

```text
Use $platform-prd-reviewer to review this PRD. Focus on logic closure, ownership, flow, data model, edge cases, operations, rollout, and open questions.
```

## 更新方式

当 GitHub 仓库后续更新后，可以这样更新本机已安装的 skills：

```bash
git pull
cp -R skills/platform-product-guide ~/.codex/skills/
cp -R skills/platform-prd-builder ~/.codex/skills/
cp -R skills/platform-prd-reviewer ~/.codex/skills/
cp -R skills/platform-scope-checker ~/.codex/skills/
cp -R skills/platform-flow-modeler ~/.codex/skills/
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
