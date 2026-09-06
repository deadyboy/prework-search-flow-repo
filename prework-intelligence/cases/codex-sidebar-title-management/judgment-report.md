# Judgment Report

这份报告由 Judgment Module 在读取一个 Evidence Pack 后写出。它不能引入新证据。

## Evidence Pack Used

- Case ID: PI-C001
- Evidence Pack path: `docs/prework-intelligence/cases/codex-sidebar-title-management/evidence-pack.md`
- Evidence Pack date: 2026-07-04

## Primary Conclusion

`补齐缺口`

## Conclusion Glossary

- `放弃不做`: 现有证据表明现在不值得继续。
- `直接采用`: 已有方案足够贴合，可以直接使用。
- `接入改造`: 已有方案能覆盖基础需求，但需要集成、包装或轻改。
- `场景定制`: 通用方案存在，但用户场景需要垂直定制。
- `补齐缺口`: 已有工作覆盖了基础，主要价值在于补 workflow、UX 或 operational pieces。
- `自研小样`: 没看到合适可复用基础，可以先做小型内部 prototype。
- `先补证据`: Evidence Pack 不足以支撑负责任的判断。

## Required Evidence Citations

本报告中的判断只引用 Evidence Pack 里的 `entity_id` 或 `negative_evidence_id`。

Primary cited records: `E001`, `E002`, `E003`, `N001`, `N002`.

Negative evidence 只能解释为：在记录的 source coverage 内没有发现强证据。它不能解释为某个方案、产品、方法或 prior work 绝对不存在。

## Judgment Rule Table

这些是粗判断规则，不是完整公式。

- 覆盖不足或关键 source class 未查：`先补证据`
- 高相关 + 高可复用：`直接采用` / `接入改造`
- 高相关 + 低可复用：`补齐缺口` / `场景定制`
- 单个 entity 不够，但多个 entity 组合能覆盖：`接入改造` / `补齐缺口`
- 没有强替代，且 negative evidence 覆盖充分：`自研小样`
- 强替代已经存在，剩余差异不重要：`放弃不做`

## Conclusion Rationale

- Primary conclusion: `补齐缺口`
- Cited entity_id or negative_evidence_id values: `E001`, `E002`, `E003`, `N001`, `N002`
- Why these evidence records support the conclusion: `E001` 说明官方 thread-name capability 已经存在，所以这不是从零做 title-renaming。`E002` 说明用户痛点真实存在，并且不同 Codex surface 上仍有工作流缺口。`E003` 说明有人做过接近的实现，但 patching installed extension 的方式不符合我们想要的安全约束。`N001` 和 `N002` 说明在本次覆盖的公开来源中，没有找到完整、安全、可审查的 Codex sidebar title-governance workflow。
- Important evidence gaps: 仍需验证具体 surface 是否可用。开源 patcher 的 license 和 maturity 需要单独检查。没有读取私人本地状态。

## Most Relevant Entities

| entity_id | entity_name | relevance_score | reuse_score | source_grade | evidence_status | role in judgment |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | Codex app-server thread naming API | 10 | 7 | S | confirmed | 证明存在可复用的官方基础能力。 |
| E002 | Public Codex rename feature-request cluster | 9 | 3 | A | confirmed | 证明用户痛点和 workflow gap 存在。 |
| E003 | Just-Boring-Cat/codex-thread-renamer | 8 | 5 | A | single-source | 提供接近的实现模式，但有安全和兼容性风险。 |
| E004 | Adjacent AI chat history and title-management patterns | 5 | 3 | B | confirmed | 提供较弱的产品模式参考，不是 Codex-specific substitute。 |

## Why Existing Work Does Or Does Not Substitute

`E001` 足以说明这件事不该从空白开始：app-server 层已经有官方 thread-name path。

但 `E001` 不能完全替代用户需求。Evidence Pack 没有记录到完整的 reviewed sidebar title-governance workflow、batch review process 或 surface-specific safety proof。

`E002` 证明这是一个真实的导航和 title drift 问题，但它不是实现。

`E003` 对 VS Code extension 用户很接近，但 patching method 和 local-state fallback 风险较高，不能直接当成完整答案。

`N001` 和 `N002` 只能说明：在已覆盖的官方、GitHub、产品和社区来源中，没有找到强证据证明已有完整安全流程。不能说外部一定不存在。

## What To Reuse

- 从 `E001` 复用官方 thread-name capability。如果当前 surface 可用，它应优先作为底层路径。
- 从 `E002` 复用问题表述：stale 或 generic titles 会降低 history navigation 质量，用户需要持久、可见、可编辑的标题。
- 从 `E003` 借鉴 UI pattern：command palette rename、sidebar context action、inline editing、写入前 verification 和 backup-minded safety checks。
- 从 `E004` 借鉴通用 chat-history pattern：searchable history、显式 rename affordance 和 privacy-aware conversation management。

## What Not To Do

- 不要把直接改本地文件或数据库设计成默认路径。`E002` 和 `E003` 说明这种 workaround 存在，但风险明显。
- 不要把相邻 chat managers 当成 Codex 直接替代方案。`E004` 只是弱相关。
- 不要声称已经存在完整公开的 Codex title-governance workflow。`N001` 和 `N002` 只说明本次搜索范围内没有找到。
- 不要在 surface-specific support 未确认前做广泛自动化。`E001`、`N001` 和 `N002` 都留下了 client availability 和 safety gaps。

## Negative Evidence Used

| negative_evidence_id | searched_scope | source_classes_covered | judgment use | limits |
| --- | --- | --- | --- | --- |
| N001 | Complete public official Codex sidebar title-governance workflow | Official Codex docs, changelog, Help Center | 支撑“仍缺 review、batch naming 和 safety rules 工作流”的判断。 | 不能排除 UI features、private docs 或 newly released client behavior。 |
| N002 | Mature safe standalone Codex-specific solution | GitHub, GitHub issues/discussions, product web, Chrome Web Store, OpenAI Developer Community | 支撑“覆盖范围内没有找到完整安全替代方案”的判断。 | 不能证明搜索范围外不存在此类方案。 |

## Next Action

先审查 Case 1 输出。之后如果继续推进，应在一个非私人 test thread 中验证当前 Codex Desktop 或 app-server rename availability，再决定是否写更具体的 title-governance workflow。

## Supplement-Evidence Request

未使用。Primary conclusion 不是 `先补证据`。

## Validity Checklist

- 本报告只读取 Evidence Pack。
- Primary conclusion 是允许值之一。
- Primary conclusion 引用了 `entity_id` 或 `negative_evidence_id`。
- 没有引入新 sources、URLs 或 entities。
- Negative evidence 只解释为“在已覆盖来源内没有发现强证据”。
- 没有把 evidence gaps 写成 confident claims。
