# Idea Card

## Original Idea

用一个快速变化产品功能 case 校验 freshness gate：Codex Windows Computer Use 是否已经从旧 issue 中的缺口变成官方支持能力。

## One-Sentence Goal

判断当前官方资料是否已经覆盖旧 issue 所说的 Windows Computer Use 缺口，并记录仍未验证的限制。

## User And Context

- Primary user: 使用 Codex app 的开发者。
- Usage context: Windows 桌面 / Codex Computer Use。
- Frequency or urgency: 高；快速变化产品能力容易误判。

## Input

- 官方 Codex changelog。
- 官方 Computer Use docs。
- openai/codex historical issue。

## Output

- Evidence Pack。
- Judgment Report。
- Independent Review。

## Core Problem

社区 issue 可能真实但过时。判断当前产品能力时必须先看官方 release timeline 和当前 docs。

## Claim Decomposition

| claim_id | claim | surface_scope | lifecycle_scope | why it matters |
| --- | --- | --- | --- | --- |
| C001 | 旧 issue 记录 Windows Computer Use 曾经缺失或不足。 | desktop_app | not_applicable | 识别历史痛点。 |
| C002 | 官方 changelog 记录 Windows Computer Use 发布或扩展。 | desktop_app | not_applicable | 判断当前能力。 |
| C003 | 当前 docs 记录 Windows Computer Use 支持和限制。 | desktop_app | not_applicable | 判断可用边界。 |
| C004 | Windows Computer Use 可后台运行且不占用当前桌面。 | desktop_app | not_applicable | 防止误读能力范围。 |
| C005 | 当前用户账号、地区、plan 一定可用。 | cross_surface | not_applicable | 区分官方能力和用户环境。 |

## Important Constraints

- Time: L2 校准搜索。
- Cost: 不做 hands-on UI 测试。
- Privacy or sensitivity: 不读取用户账号状态。
- Technical environment: 官方 docs + public issue。
- Quality bar: 能按时间线解释旧 issue 和新 release 的关系。

## Suspected Uniqueness

本 case 的价值不在功能本身，而在测试流程是否会被 stale issue 误导。

## Desired Reuse

- Freshness gate。
- Release timeline。
- Issue staleness detection。

## Unacceptable Substitutes

- 只引用旧 issue。
- 只引用 changelog 而忽略限制。
- 未验证用户环境却断言用户一定可用。

## Search Level

`L2 standard scan`

## Notes For Search Module

优先官方 changelog / current docs，再读 GitHub issue。
