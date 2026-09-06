# Idea Card

## Original Idea

比较现有 skill / agent workflow 框架，看 Prework Intelligence 是否应吸收它们的结构。

## One-Sentence Goal

找出可迁移的文档结构、边界规则和验证方式，同时避免过早引入 agent 执行复杂度。

## Claim Decomposition

| claim_id | claim | surface_scope | lifecycle_scope | why it matters |
| --- | --- | --- | --- | --- |
| C001 | Skill 格式已形成可复用的工作流封装模式。 | cross_surface | not_applicable | 影响 strategy card / method packaging。 |
| C002 | Agent frameworks 提供可复用的执行原语。 | cross_surface | not_applicable | 判断未来自动化是否可借鉴。 |
| C003 | Guardrails / handoff / tracing 可帮助保持边界。 | cross_surface | not_applicable | 对 Search/Judgment 分离有参考价值。 |
| C004 | 未发现现成 Prework Intelligence 等价框架。 | cross_surface | not_applicable | 防止误判已有工作已完全替代。 |

## Important Constraints

- 不新增自动化实现。
- 不新增 agent runtime。
- 只做方法对标。

## Desired Reuse

- Skill 文件结构。
- when-to-use / inputs / outputs / forbidden behavior。
- verification checklist。
- guardrail 和 tracing 思路。

## Unacceptable Substitutes

- 只比较 agent 框架功能，不回答是否适合 Prework。
- 把执行框架当判断方法论。

## Search Level

`L3 deep review`
