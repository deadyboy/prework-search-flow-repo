# Idea Card

## Original Idea

Codex 侧边栏里的 thread title 如果默认生成得不准，后面就很难找回对应任务。这个案例要判断：标题命名是否可控，官方是否已经有重命名能力，以及是否值得做一套安全的标题治理流程。

## One-Sentence Goal

判断 Codex sidebar title management 应该直接使用现有功能、接入改造已有能力、补齐工作流缺口，还是做一个小型自研原型。

## User And Context

- Primary user: 管理大量 Codex / 类 Codex 工作线程的用户。
- Usage context: 在本地 Codex workspace 中查找、识别、重命名和整理侧边栏会话或任务标题。
- Frequency or urgency: 当会话越来越多、默认标题不能反映真实任务时，这会反复影响检索和继续工作。

## Input

- 现有 Codex 侧边栏 thread list 或 task list。
- 现有 thread titles、首条消息、最近真实意图和 case metadata。只有在安全且必要时才使用。
- 用户认可的命名规则或标题约定。
- 公开文档、公开 issue、社区讨论和可见产品能力。

## Output

- 一份可供判断的 Evidence Pack 和 Judgment Report，用来决定标题治理应依赖现有功能、接入已有工具、补齐窄工作流，还是先做小样。

## Core Problem

自动生成或默认生成的 conversation title 可能跟不上任务真实状态。标题不准会让旧工作更难找，也会增加打开、fork 或继续错误 thread 的风险。

## Important Constraints

- Time: 使用 `L2 standard scan`，不做完整产品审计或代码审计。
- Cost: 如果现有官方能力或轻量工作流足够，优先复用。
- Privacy or sensitivity: 不读取私人 Codex conversation content、本地数据库、账号文件或 `.codex` state，除非明确必要且安全。本案例优先依赖公开来源和非敏感项目上下文。
- Technical environment: Windows 上的 Codex desktop 或类 Codex app 环境。
- Quality bar: 任何标题治理流程都不能默认直接改本地数据库；改标题前应保留用户审查。

## Suspected Uniqueness

这个需求不是泛泛的 chat title editing。它更具体：给 Codex sidebar 工作线程做安全、可复核的 title governance，让标题同时反映稳定背景和最新真实进展。

## Desired Reuse

最值得复用的是官方 rename 功能、现有 Codex feature、公开 plugin/workflow、issue 中的社区模式，或者一个安全的操作清单。

## Unacceptable Substitutes

- 泛泛建议“少开一些 thread”。
- 不经用户审查，直接修改本地 Codex 数据库。
- 只能改浏览器 tab、文件名或无关 chat 产品标题的工具。
- 全自动改标题，但没有 review 步骤。

## Search Level

`L2 standard scan`

## Notes For Search Module

可用搜索词包括 Codex sidebar title、Codex thread title、rename Codex conversation、ChatGPT project or chat rename、OpenAI Codex task、Codex CLI、conversation title management、issue、feature request 等。只有在公开来源不足且有明确安全理由时，才考虑本地或用户提供来源。
