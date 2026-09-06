# Search Plan

## Case Metadata

- Case ID: A2
- Idea title: Open-source patcher as formal solution
- Search level: L2 standard scan
- Search date: 2026-07-09
- Searcher: Codex with independent calibration subagent brief

## Search Objective

查清楚公开 patcher 的功能、license、维护、风险和官方支持边界，避免把相似代码误判为可直接正式采用。

## Claim Decomposition

| claim_id | claim | surface_scope | lifecycle_scope | planned evidence needed |
| --- | --- | --- | --- | --- |
| C001 | Patcher 提供相关 rename 功能。 | vscode_extension | manual_rename | repo README / docs。 |
| C002 | Patcher 有 license 和维护信号。 | vscode_extension | not_applicable | license、release、commit、stars/forks。 |
| C003 | Patcher 通过修改 installed extension files 工作。 | local_state | not_applicable | docs/how-it-works。 |
| C004 | 官方支持边界不同于 patcher surface。 | cross_surface | not_applicable | 官方 Codex docs。 |
| C005 | Patcher 可否作为正式默认路径。 | cross_surface | not_applicable | C001-C004 综合证据和 negative evidence。 |

## Domain Routes

- Software or tooling: yes
- Academic or research: no
- Product or startup: no
- Patent or invention: no
- R&D or technology scouting: no
- Policy or process: no
- Internal workflow: no

## Query Matrix

| Dimension | Chinese terms | English terms | Formal terms | Product terms | User-language terms |
| --- | --- | --- | --- | --- | --- |
| Goal | Codex 标题 重命名 patcher | Codex thread renamer patcher | extension patching | Codex / VS Code extension | rename Codex thread |
| Problem | 标题治理 风险 | installed extension patch risk | support boundary | OpenAI Codex | safe default |
| Object | thread title | thread name | `thread/name/set` | app-server | sidebar title |
| Method | 修改扩展文件 | patch installed extension files | backup restore verify | GitHub repo | workaround |
| Substitute | 官方 API | official support | open-source boundary | Codex docs | direct adoption |

## Planned Sources

| Source class | Planned source | Query families | Why this source matters |
| --- | --- | --- | --- |
| Web | general web | exact repo name | Find official/secondary discussion. |
| GitHub or open source | GitHub repo | repo, license, docs, release | Main implementation evidence. |
| Papers | not applicable | none | Not a research case. |
| Product directories | not applicable | none | Not a product replacement case. |
| Communities | optional | issue / limitation | Risk evidence if needed. |
| Patents or standards | not applicable | none | Not needed. |
| Local or user-provided sources | not searched | none | Avoid private local state. |

## Current Product Capability Gate

- Official changelog / release notes checked: not central to this case.
- Current docs checked: Codex open-source boundary and app-server docs.
- Current UI or user-observed evidence available: no.
- Older issues or community posts used only as historical evidence: yes.
- Freshness gaps: no hands-on patch test or code audit.

## Exclusion Rules

- Ignore generic thread rename tools unrelated to Codex.
- Ignore demos without source/license.
- Ignore advice that requires private local state inspection.

## Stopping Rules

Stop after the patcher repo, its docs/license, and official Codex support boundary are covered, plus negative evidence for official endorsement.

## Negative Search Scope

- Official endorsement.
- Package registry distribution.
- Unsupported / not maintained / deprecated signals.

## Evidence Pack Handoff Checklist

- Query log records what was searched.
- Results are grouped by entity.
- Every entity has `entity_id`.
- Every entity has `relevance_score`, `reuse_score`, `method_similarity`, `method_note`, `source_grade`, and `evidence_status`.
- Capability Claim Matrix records `claim_id`, `surface_scope`, `lifecycle_scope`, `freshness_status`, supporting records, and gaps.
- Information gaps are explicit.
- No final judgment is included.
