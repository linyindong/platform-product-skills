# Platform Product Skills

<a id="english"></a>

Language: [English](#english) | [中文](#中文)

**Your AI product deputy for platform & back-office work — describe what you need, and it takes you from a rough idea to a reviewed PRD.**

Writing PRDs, reviewing them, drawing MVP boundaries, untangling cross-system flows, chasing down ownership and edge cases — mid-platform product work is heavy, fragmented, and easy to get wrong. This is a skill system that carries that load with you.

You don't pick tools or learn commands. You talk to one **product deputy** in plain language (the `platform-product-orchestrator` skill); it works out what you need, asks only the questions that actually change the decision, and drives the right specialist skills behind the scenes. Works in both **Codex** and **Claude Code** (CLI, desktop, claude.ai/code).

## See it work

```text
You: Write a PRD for the approval center — add a feature: when the applicant
     cancels, notify the approvers currently reviewing it.

It:  A few things to confirm (I'll assume sensible defaults for the rest):
     1. Notify only the active level, or the downstream pending levels too?
     2. Is a cancellation reason required?
     3. Which section of the parent PRD does this hang off?
     -> Once you answer: a lean first draft -> an automatic review with a
        readiness score and must-fix items -> we iterate to final.
```

Hand it an existing PRD instead and ask "what does this mainly cover, and which functions would it change?" — it reads and gives you a digest plus an impact analysis. Same entry, different job.

(Talk to it in whatever language you work in — the examples here are illustrative.)

## What it does for you

- **Turns a rough idea into a PRD** — clarify → draft → review → iterate, without the blank-page start.
- **Reviews a PRD like a strict lead** — readiness score, concrete contradictions, must-fix gaps, what's PRD vs RFC.
- **Explains an existing PRD** — what it covers, in seconds.
- **Analyzes impact** — which systems and functions a change actually touches, and the hidden complexity.
- **Guards your MVP** — should this be in scope now? include / simplify / defer, with the boundary drawn.
- **Models the hard flows** — state, callbacks, rollback, reconciliation, ownership — before they bite you in review.
- **Frames a fuzzy requirement** — into something you can actually write.

Built for the messy realities of platform, workflow, approval, configuration, risk, finance, and fintech back-office products — not generic PM advice. It scales itself: lean output for a small enhancement, full rigor for a 0-to-1 platform build. And it gets smoother the more you use it — it remembers your style and your systems (kept in your own private space, never in this repo), so over time it asks less and drafts closer to what you'd write.

## Quick start

**1. Install** — clone once, copy into your tool's skills directory:

```bash
git clone https://github.com/linyindong/platform-product-skills.git
cd platform-product-skills

# Claude Code → ~/.claude/skills   |   Codex → ~/.codex/skills
DEST=~/.claude/skills
mkdir -p "$DEST"
cp -R skills/platform-product-orchestrator "$DEST"/
cp -R skills/platform-product-guide        "$DEST"/
cp -R skills/platform-prd-builder          "$DEST"/
cp -R skills/platform-prd-reviewer         "$DEST"/
cp -R skills/platform-scope-checker        "$DEST"/
cp -R skills/platform-flow-modeler         "$DEST"/
```

**2. Just say what you want.** No skill to pick, nothing to configure — your product deputy is the default entry:

```text
Write a PRD for the approval center — add a feature: notify the active approvers when the applicant cancels.
Read this PRD and tell me what it mainly covers and which functions it would change. [paste/attach PRD]
Should this change go in the current phase? [change]
```

**3. (Optional) enforce deputy-first.** It's already the default out of the box. If you want a hard guarantee, add this to your `~/.claude/CLAUDE.md` (Claude Code) or your agent's project instructions:

```md
For platform / back-office / workflow / fintech product tasks described in
natural language, use `platform-product-orchestrator` as the default entry
point; it drives the specialist skills internally. Use a specialist skill
directly only when I name it or invoke it with `/`.
```

## How it works

```text
You (natural language)
  -> platform-product-orchestrator   (understands intent, routes, controls the flow)
       -> specialist skills           (each does one kind of work well)
  -> your private memory / context    (your style & domain — makes it smoother over time)
```

The product deputy is the entry brain; the specialists are the capabilities it calls; your personalization lives in your own private memory (never in this repo) and is read at runtime. You can also call any specialist directly when you already know what you want.

## The specialist skills

You normally don't call these yourself. Name one (or use `/skill-name`) when you want it directly.

| Skill | Does |
|---|---|
| `platform-product-orchestrator` | Your product deputy — the entry layer; classifies intent and drives the rest. |
| `platform-product-guide` | Direction framing, platform-capability abstraction, ownership/source-of-truth reasoning. |
| `platform-prd-builder` | Draft or rewrite PRDs / requirement sections from rough input. |
| `platform-prd-reviewer` | Review PRDs — readiness, document-specific findings, consistency, RFC boundary. |
| `platform-scope-checker` | MVP scope, hidden complexity, impact analysis, include / simplify / defer. |
| `platform-flow-modeler` | Cross-system flows, state, callback / rollback / reconciliation, ownership. |

## Works with

Cross-tool by design — standard `SKILL.md` format (YAML frontmatter `name` + `description` + markdown body), shared by **Codex** (`~/.codex/skills`) and **Claude Code** (`~/.claude/skills`). Also reusable in any agent that supports file-based custom skills.

Each skill folder is self-contained: `SKILL.md` is the skill (read by all tools), `references/*.md` holds detailed rubrics loaded on demand, and `agents/openai.yaml` is Codex-only UI metadata that other tools ignore. An improvement committed here reaches every tool at once.

## Updating

```bash
git pull
DEST=~/.claude/skills   # or ~/.codex/skills
for s in platform-product-orchestrator platform-product-guide platform-prd-builder \
         platform-prd-reviewer platform-scope-checker platform-flow-modeler; do
  cp -R "skills/$s" "$DEST"/
done
```

## Who it's for

Product managers, platform/fintech PMs, and internal-tool / back-office teams working on workflow, approval, configuration, risk, finance, operations, or cross-system products — anyone who wants AI to think through the product with them, not just format a document.

Not built for consumer marketing copy, pure UI critique, pure engineering implementation plans, or ungrounded brainstorming.

## License

Released under the [MIT License](LICENSE). Use, modify, and redistribute freely (including commercially); keep the copyright notice.

Keywords: agent skills, Codex skills, Claude Code skills, product management, PRD, PRD review, MVP scope, platform product, fintech, internal tools, workflow, back-office, product ops, flow modeling.

---

<a id="中文"></a>

# 中文说明：平台型产品 Skills

语言：[English](#english) | [中文](#中文)

**你的 AI 产品副手，专为平台与中后台工作打造 —— 你说清要做什么，它带你从一个粗糙想法走到一份审过的 PRD。**

写 PRD、评审、划 MVP 边界、理跨系统流程、追 ownership 和 edge case —— 中后台产品的活又碎又重，还容易漏。这是一套帮你一起扛的 skill 系统。

你不用挑工具、不用记命令。你只用大白话跟一个**产品副手**（技术名 `platform-product-orchestrator`）说话，它判断你要什么、只问真正影响决策的问题、在背后驱动对应的专项 skill。**Codex 和 Claude Code**（CLI、桌面、claude.ai/code）都能用。

## 看它怎么跑

```text
你： 写个审批中心的 PRD，加个功能：申请人 cancel 时通知当前在审的审批人。

它： 确认 3 点（其余我按合理默认走）：
     1. 只通知当前在审层，还是下游 pending 层也通知？
     2. cancel 原因是否必填？
     3. 挂在母 PRD 哪一节下？
     → 你答完，它出精简初稿 → 自动审一遍给就绪度和必改项 → 和你迭代到定稿。
```

换成给它一份现成 PRD、问"这主要写了什么、涉及哪些功能点改造"——它读完给你一份摘要加一份影响分析。同一个入口，换一种活。

## 它能帮你做什么

- **把粗糙想法变成 PRD** —— 澄清 → 出稿 → 审核 → 迭代，告别空白页开局。
- **像严格的 lead 一样评审** —— 就绪度打分、具体矛盾、必改项、哪些是 PRD、哪些该进 RFC。
- **看懂一份现成 PRD** —— 它主要写了什么，几秒说清。
- **分析影响** —— 一个改动到底动了哪些系统和功能，以及隐藏复杂度。
- **守住你的 MVP** —— 这个要不要本期做？include / 简化 / 延后，边界给你划好。
- **啃下难缠的流程** —— 状态、callback、rollback、对账、ownership —— 赶在评审咬你之前。
- **理清模糊需求** —— 变成真正能动笔写的东西。

它是为平台、流程、审批、配置、风控、财务、金融科技中后台这些真实的复杂场景做的 —— 不是泛泛的 PM 建议。它会自动伸缩：小增强给精简产出，0-to-1 平台上完整严谨结构。而且**越用越顺** —— 它记得你的风格和你的系统（存在你自己的私有空间里，绝不进本仓库），时间久了问得越少、初稿越接近你会写的样子。

## 快速上手

**1. 安装** —— clone 一次，复制到你工具的 skills 目录：

```bash
git clone https://github.com/linyindong/platform-product-skills.git
cd platform-product-skills

# Claude Code → ~/.claude/skills   |   Codex → ~/.codex/skills
DEST=~/.claude/skills
mkdir -p "$DEST"
cp -R skills/platform-product-orchestrator "$DEST"/
cp -R skills/platform-product-guide        "$DEST"/
cp -R skills/platform-prd-builder          "$DEST"/
cp -R skills/platform-prd-reviewer         "$DEST"/
cp -R skills/platform-scope-checker        "$DEST"/
cp -R skills/platform-flow-modeler         "$DEST"/
```

**2. 直接说你想做什么。** 不用挑 skill、不用配置 —— 产品副手就是默认入口：

```text
写个审批中心的 PRD，加个功能：申请人 cancel 时通知当前在审的审批人。
这份 PRD 帮我看看主要写了什么，可能涉及哪些功能点改造。[粘贴/上传 PRD]
这个改动要不要放进本期？[改动]
```

**3.（可选）强制副手优先。** 它开箱就是默认入口。如果你想要硬保证，可在 `~/.claude/CLAUDE.md`（Claude Code）或你所用 agent 的项目指令里加一条：

```md
产品/中后台/流程/金融科技类任务，用自然语言描述时，默认走
platform-product-orchestrator，由它在背后调用各专项 skill；只有当我
显式点名或用 / 调用时，才直接用某个专项 skill。
```

## 它怎么运作

```text
你（自然语言）
  -> platform-product-orchestrator   （听懂意图、路由、控流程）
       -> 各专项 skill                （每个把一类活干好）
  -> 你的私有记忆/上下文              （你的风格与领域 —— 越用越顺）
```

产品副手是入口大脑，专项 skill 是它调用的能力，你的个性化存在你自己的私有记忆里（绝不进本仓库）、运行时读取。你也可以在明确时直接调用某个专项 skill。

## 专项 skill 一览

通常不用你自己调。想直接用时，点名或用 `/skill-name`。

| Skill | 作用 |
|---|---|
| `platform-product-orchestrator` | 你的产品副手 —— 入口层，判断意图并驱动其余。 |
| `platform-product-guide` | 方向梳理、平台能力抽象、ownership/source-of-truth 推理。 |
| `platform-prd-builder` | 从粗略输入起草或改写 PRD / 需求章节。 |
| `platform-prd-reviewer` | 评审 PRD —— 就绪度、文档内具体问题、一致性、RFC 边界。 |
| `platform-scope-checker` | MVP 范围、隐藏复杂度、影响分析、include / 简化 / 延后。 |
| `platform-flow-modeler` | 跨系统 flow、状态、callback / rollback / 对账、ownership。 |

## 支持哪些工具

天生跨工具 —— 标准 `SKILL.md` 格式（YAML frontmatter `name` + `description` + markdown 正文），Codex（`~/.codex/skills`）和 Claude Code（`~/.claude/skills`）共用。也可复用于任何支持文件式自定义 skill 的 agent。

每个 skill 文件夹自成一体：`SKILL.md` 是本体（所有工具读），`references/*.md` 是按需加载的详细 rubric，`agents/openai.yaml` 是 Codex 专用 UI 元数据、其它工具会忽略。在这里改一处，所有工具同时生效。

## 更新

```bash
git pull
DEST=~/.claude/skills   # 或 ~/.codex/skills
for s in platform-product-orchestrator platform-product-guide platform-prd-builder \
         platform-prd-reviewer platform-scope-checker platform-flow-modeler; do
  cp -R "skills/$s" "$DEST"/
done
```

## 适合谁

产品经理、平台/金融科技 PM、中后台/内部工具团队，做审批、配置、风控、财务、运营、流程或跨系统产品的人 —— 希望 AI 和你一起把产品想透，而不只是帮你排版文档。

不适合：消费品营销文案、纯 UI 视觉评审、纯工程实现方案、没有产品/系统背景的泛点子 brainstorming。

## License

采用 [MIT License](LICENSE) 开源。可自由使用、修改、再分发（含商用），保留版权声明即可。

关键词：agent skills、Codex skills、Claude Code skills、产品经理、PRD、PRD Review、MVP 范围、平台型产品、金融科技、中后台、内部工具、流程、产品运营、flow 建模。
