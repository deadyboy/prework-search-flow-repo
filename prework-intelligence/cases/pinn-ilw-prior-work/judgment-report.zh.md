# 判断报告（中文阅读版）

源文件：`judgment-report.md`  
权威状态：中文阅读副本，不作为 Evidence Pack / Judgment Module 的唯一交接文件。若与源文件不一致，以源文件为准。

## 使用的 Evidence Pack

- Case ID: C1
- Evidence Pack path: `docs/prework-intelligence/cases/pinn-ilw-prior-work/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## 主结论

`先补证据`

## 证据引用

主结论引用：`E001`, `E002`, `N001`, `N002`。

## 为什么是这个结论

当前证据包已经找到相邻证据：`E001` 说明 PINN 在非线性色散 PDE 上有相邻方法参考，`E002` 说明 intermediate long wave 作为 PDE/domain 存在相关研究。但 Evidence Pack 同时记录了核心歧义：`ILW` 到底指 inverse Lax-Wendroff，还是 intermediate long wave。

因此现在不能负责任地判断“PINN + ILW 是否已有直接 prior work”，也不能判断 novelty 或可复用程度。需要先补充术语澄清、inverse Lax-Wendroff 定向搜索、代码/benchmark 搜索和引用追踪。

## Claim Matrix 中文解读

| claim_id | 子问题 | 局部结论 | 引用记录 | 中文解释 | 仍缺什么 |
| --- | --- | --- | --- | --- | --- |
| C001 | PINN 在非线性色散 PDE 上有相邻证据。 | `接入改造` | E001 | 可作为方法邻域和 baseline 参考。 | 不是直接的 ILW 边界处理证据。 |
| C002 | intermediate long wave 是活跃的 PDE/domain。 | `先补证据` | E002 | 只有当用户说的 ILW 是 intermediate long wave 时才相关。 | 用户意图尚不明确。 |
| C003 | 已确认存在直接的 PINN + inverse Lax-Wendroff boundary prior work。 | `先补证据` | N001 | 简短搜索没有找到强证据，但搜索深度不足。 | 需要重新做定向 academic/code 搜索。 |
| C004 | 已确认存在直接的 PINN + intermediate long wave prior work。 | `先补证据` | E001; E002; N002 | 目前只是相邻证据，不能当作直接 prior work。 | 需要更深的学术检索。 |

## 最相关实体

| entity_id | 实体 | relevance_score | reuse_score | source_grade | evidence_status | 在判断中的作用 |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | PINN for nonlinear dispersive PDEs | 7 | 5 | A | confirmed | 相邻方法证据。 |
| E002 | Modified intermediate long wave equation | 6 | 3 | A | confirmed | 可能的领域证据。 |

## 现有工作是否能替代

不能。当前证据不足以支持直接 prior-work 结论，因为关键术语未澄清，直接证据也未建立。

## 可复用内容

- `E001` 可作为相邻 PINN baseline 证据。
- `E002` 只能在确认 ILW 指 intermediate long wave 时使用。

## 不该做什么

- 不要根据 `N001` 或 `N002` 声称直接 novelty。
- 不要混用 inverse Lax-Wendroff 和 intermediate long wave 的证据。

## 使用的负面证据

| negative_evidence_id | 搜索范围 | 覆盖来源 | 判断用途 | 限制 |
| --- | --- | --- | --- | --- |
| N001 | PINN + inverse Lax-Wendroff | Academic brief search | 支持补证据请求。 | 搜索需要重跑。 |
| N002 | PINN + intermediate long wave | Academic brief search | 支持补证据请求。 | 不证明不存在。 |

## 下一步

先确认 `ILW` 的含义，再重跑定向 academic 和 code search，然后再判断 novelty 或复用价值。

## 补证据请求

- 受影响的 entity_id：`E001`, `E002`
- 受影响的 negative_evidence_id：`N001`, `N002`
- 缺少来源类型：targeted academic index 和 code repository search
- 缺少对比：inverse Lax-Wendroff boundary treatment 与 intermediate long wave equation 的区分
- 缺少记录类型：direct method entity record 和 baseline/code record
- 为什么不能继续判断：Evidence Pack 没有解决中心术语歧义。
- Search Module 应补充：拆分后的 query families、直接 prior-work map、baseline/code entities。
