# Idea Card

## Original Idea

评估一个公开的 Codex thread rename patcher 是否可以作为 Codex title governance 的正式方案基础。

## One-Sentence Goal

判断 open-source patcher 是可以直接采用、接入改造，还是只能作为风险参考。

## User And Context

- Primary user: 想改进 Codex thread title 管理的人。
- Usage context: Codex / VS Code extension / 本地工作流。
- Frequency or urgency: 中等；用于校准流程判断粒度。

## Input

- 公开 GitHub repo。
- 官方 Codex 文档。
- patcher 文档、license、维护信号。

## Output

- Evidence Pack。
- Judgment Report。
- Independent Review。

## Core Problem

有开源实现不等于可作为正式默认路径。需要区分功能相似、风险、官方支持边界和可复用程度。

## Claim Decomposition

| claim_id | claim | surface_scope | lifecycle_scope | why it matters |
| --- | --- | --- | --- | --- |
| C001 | 有公开 patcher 能改 Codex / VS Code thread title 相关 UI。 | vscode_extension | manual_rename | 判断是否存在可复用实现。 |
| C002 | patcher 有 license、维护和发布信号。 | vscode_extension | not_applicable | 判断是否能工程复用。 |
| C003 | patcher 修改 installed extension files，存在兼容和安全风险。 | local_state | not_applicable | 判断是否适合默认方案。 |
| C004 | 官方支持边界与 patcher 目标 surface 不完全一致。 | cross_surface | not_applicable | 避免把 workaround 当官方路径。 |
| C005 | patcher 是否可作为正式默认方案。 | cross_surface | not_applicable | 这是最终行动判断的核心 claim。 |

## Important Constraints

- Time: L2 校准搜索。
- Cost: 不做代码审计。
- Privacy or sensitivity: 不读取用户本地 extension 或 Codex state。
- Technical environment: 公开 repo 和官方 docs。
- Quality bar: 能解释为什么“可借鉴”不等于“直接采用”。

## Suspected Uniqueness

用户想要的是稳定、可审查、可回滚的 title governance，不只是一次性 patch。

## Desired Reuse

- UI affordance。
- rename workflow。
- verify / backup / restore 机制。
- 风险提示。

## Unacceptable Substitutes

- 直接修改本地私有状态作为默认方案。
- 没有 license 或维护信号的代码。
- 与当前 Codex surface 不匹配的 demo。

## Search Level

`L2 standard scan`

## Notes For Search Module

重点查 GitHub repo、官方 Codex open-source/support boundary、package distribution 和 negative evidence。
