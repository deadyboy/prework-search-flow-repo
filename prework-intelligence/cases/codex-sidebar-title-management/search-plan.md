# Search Plan

本文件属于 Search Module。它是搜索计划，不是证据；除非执行结果已经进入 Evidence Pack，否则 Judgment Module 不能把它当证据。

## Case Metadata

- Case ID: PI-C001
- Idea title: Codex sidebar title management
- Search level: L2 standard scan
- Search date: 2026-07-04
- Searcher: Codex

## Search Objective

查清楚 Codex sidebar thread title management 是否已有官方功能、公开工具、开源实现、产品替代方案、社区工作流或 issue 讨论，并记录还缺哪些关键证据。

## Domain Routes

Mark applicable routes:

- Software or tooling: primary
- Academic or research: 非主线；只有方法证据明显相关时再查
- Product or startup: secondary
- Patent or invention: 不适用
- R&D or technology scouting: secondary
- Policy or process: secondary
- Internal workflow: secondary，但只使用非敏感项目上下文

## Query Matrix

| Dimension | Chinese terms | English terms | Formal terms | Product terms | User-language terms |
| --- | --- | --- | --- | --- | --- |
| Goal | 侧边栏标题管理; 会话重命名 | sidebar title management; thread title rename | conversation metadata; thread metadata | Codex; ChatGPT; Cursor; Claude | rename my Codex thread; fix sidebar titles |
| Problem | 标题不准; 自动命名错误 | inaccurate title; auto title wrong | title generation; title governance | chat history; project sidebar | hard to find old tasks |
| Object | Codex 会话; 线程标题 | Codex thread; conversation title | task title; session title | Codex desktop; Codex CLI | sidebar title |
| Method | 安全重命名; 人工审核 | safe rename; review before update | human-in-the-loop metadata update | plugin; command; UI action | batch rename with review |
| Substitute | 官方功能; 插件; 工作流 | official rename; extension; workflow | title-management feature | ChatGPT rename; issue tracker | manual rename |

## Planned Sources

| Source class | Planned source | Query families | Why this source matters |
| --- | --- | --- | --- |
| General web / official docs | OpenAI Help, OpenAI Codex docs, OpenAI product pages | exact Codex title terms; rename terms; sidebar terms | 如果官方已经支持，这是最强复用来源。 |
| GitHub or open source | GitHub repository and code search | `codex title rename`; `conversation title management`; `thread title rename` | 查找可复用实现、脚本、插件或 CLI。 |
| GitHub issues/discussions | GitHub issues and discussions for relevant repos | issue, feature request, limitation, not supported | 了解公开痛点、限制和产品缺口。 |
| Product or tool substitutes | General product search for chat title management and AI workspace management | alternative, competitor, chat history organizer, workspace title management | 查找相邻产品或工作流替代方案。 |
| Communities / forums if available | OpenAI Community, Reddit, Stack Overflow or public forum pages | complaint, workaround, manual rename, auto title wrong | 捕捉用户侧 workaround 和限制。 |
| Local or user-provided sources only if explicitly necessary and safe | Project docs only; no private `.codex` database or private conversation content | AGENTS title rule, project notes | 本地证据可描述用户真实工作流，但私人 session 内容不进入本案例。 |
| Papers | Only if research/method evidence appears relevant | conversation title generation, chat summarization title | 大概率是可选来源；本案例主要是操作工具问题，不是研究方法问题。 |

## Exclusion Rules

忽略浏览器 tab title、无关文件标题规范化、SEO title generation、视频标题生成器，以及不能帮助判断 Codex 或同类 AI work-session title governance 的 chat 产品。

## Stopping Rules

当 L2 覆盖到官方文档/help、general web、GitHub/open-source、GitHub issue/community、产品替代方案，以及关于官方或开源缺口的 negative/failure queries 后停止。若论文来源没有明显相关性，记录为未搜索的可选来源。

## Negative Search Scope

搜索是否缺少官方 rename 证据、是否缺少 Codex sidebar title support、是否存在废弃或过时工具、feature request、auto title complaint，以及缺少开源实现的证据。Negative evidence 只能描述已搜索范围。

## Evidence Pack Handoff Checklist

- Query log records what was searched.
- Results are grouped by entity.
- Every entity has `entity_id`.
- Every entity has `relevance_score`, `reuse_score`, `method_similarity`, `method_note`, `source_grade`, and `evidence_status`.
- Information gaps are explicit.
- No final judgment is included.
