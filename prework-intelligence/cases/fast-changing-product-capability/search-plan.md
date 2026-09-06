# Search Plan

## Case Metadata

- Case ID: A3
- Idea title: Fast-changing current product capability
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent calibration subagent brief

## Search Objective

验证 Codex Windows Computer Use 的当前官方支持状态，并把旧 issue 作为历史证据而不是当前缺口证据。

## Claim Decomposition

| claim_id | claim | surface_scope | lifecycle_scope | planned evidence needed |
| --- | --- | --- | --- | --- |
| C001 | 旧 issue 记录 Windows Computer Use 曾经缺失或不足。 | desktop_app | not_applicable | GitHub issue date and claim. |
| C002 | 官方 changelog 记录 Windows Computer Use 发布或扩展。 | desktop_app | not_applicable | Official release timeline. |
| C003 | 当前 docs 记录 Windows Computer Use 支持和限制。 | desktop_app | not_applicable | Current docs. |
| C004 | Windows Computer Use 可后台运行且不占用当前桌面。 | desktop_app | not_applicable | Negative/limit search. |
| C005 | 当前用户账号、地区、plan 一定可用。 | cross_surface | not_applicable | Account/user-observed evidence, if available. |

## Domain Routes

- Software or tooling: yes
- Academic or research: no
- Product or startup: yes
- Patent or invention: no
- R&D or technology scouting: no
- Policy or process: no
- Internal workflow: no

## Query Matrix

| Dimension | Chinese terms | English terms | Formal terms | Product terms | User-language terms |
| --- | --- | --- | --- | --- | --- |
| Goal | Windows Computer Use | Codex Windows Computer Use | release timeline | Codex app | computer use on Windows |
| Problem | 旧 issue 当前能力 | stale issue current feature | freshness gate | OpenAI Codex | does it exist now |
| Object | 桌面控制 | desktop computer use | foreground control | Computer Use | Windows support |
| Method | changelog 检查 | changelog release notes | current docs | Codex docs | release fixed issue |
| Substitute | 旧 issue | historical issue | current_official | GitHub issue | old request |

## Planned Sources

| Source class | Planned source | Query families | Why this source matters |
| --- | --- | --- | --- |
| Web | OpenAI docs search | Codex Computer Use Windows | Current capability. |
| GitHub or open source | openai/codex issue | Windows Computer Use issue | Historical gap. |
| Papers | not applicable | none | Not a research case. |
| Product directories | not applicable | none | Official product docs are primary. |
| Communities | optional | issue comments | Historical pain only. |
| Patents or standards | not applicable | none | Not needed. |
| Local or user-provided sources | not searched | none | Avoid account/UI inspection. |

## Current Product Capability Gate

- Official changelog / release notes checked: yes.
- Current docs checked: yes.
- Current UI or user-observed evidence available: no.
- Older issues or community posts used only as historical evidence: yes.
- Freshness gaps: account, region, plan, and installed app behavior not verified hands-on.

## Exclusion Rules

- Ignore macOS-only claims when judging Windows support.
- Ignore old issue text as current capability evidence unless later freshness is recorded.
- Ignore third-party summaries when official docs are available.

## Stopping Rules

Stop after official changelog, current docs, and one representative older issue establish the timeline and limitation boundaries.

## Negative Search Scope

- Background/non-foreground Windows operation.
- Guaranteed account/region availability.
- Product-wide absence after official release.

## Evidence Pack Handoff Checklist

- Query log records what was searched.
- Results are grouped by entity.
- Every entity has `entity_id`.
- Every entity has `relevance_score`, `reuse_score`, `method_similarity`, `method_note`, `source_grade`, and `evidence_status`.
- Capability Claim Matrix records `claim_id`, `surface_scope`, `lifecycle_scope`, `freshness_status`, supporting records, and gaps.
- Information gaps are explicit.
- No final judgment is included.
