# 判断报告（中文阅读版）

源文件：`judgment-report.md`  
权威状态：中文阅读副本，不作为 Evidence Pack / Judgment Module 的唯一交接文件。若与源文件不一致，以源文件为准。

## 使用的 Evidence Pack

- Case ID: D2
- Evidence Pack path: `docs/prework-intelligence/cases/ecmo-unstructured-extraction-prediction/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## 主结论

`场景定制`

## 证据引用

主结论引用：`E001`, `E002`, `E003`, `E004`, `N001`。

## 为什么是这个结论

Evidence Pack 显示，ECMO registry 和字段定义、ECMO 结局评分、ECMO 机器学习预测论文、ICU free-text 预测方法都存在。但搜索到的公开证据没有形成一个成熟的、可直接复用的“ECMO 非结构化病历抽取 -> 时间线结构化 -> 预测建模”完整闭环。

所以这个任务不应直接简化成“让 LLM 做二分类预测”。更合理的是 `场景定制`：先做抽取 schema 和时间窗标签，再把抽取结果与结构化变量融合，最后单独验证预测模型。

## Claim Matrix 中文解读

| claim_id | 子问题 | 局部结论 | 引用记录 | 中文解释 | 仍缺什么 |
| --- | --- | --- | --- | --- | --- |
| C001 | ECMO registry 基础存在。 | `接入改造` | E001 | 可用于字段 schema 参考。 | 本地病历字段可能不同。 |
| C002 | ECMO 预测 prior work 存在。 | `接入改造` | E002; E003 | 可作为 baseline 或写作参考。 | 多数依赖结构化变量。 |
| C003 | ICU free-text 预测方法存在。 | `接入改造` | E004 | 可作为非结构化方法类比。 | 不是 ECMO-specific。 |
| C004 | 已有完整 ECMO 非结构化抽取-预测闭环。 | `补齐缺口` | E001; E002; E003; E004; N001 | 组件存在，但完整 workflow 需要定制。 | 没找到完整公开闭环。 |

## 最相关实体

| entity_id | 实体 | relevance_score | reuse_score | source_grade | evidence_status | 在判断中的作用 |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | ELSO Registry and data definitions | 11 | 8 | S | confirmed | Schema 基础。 |
| E002 | ELSO outcome prediction scores | 9 | 5 | S | confirmed | Baseline 和限制。 |
| E003 | ECMO ML mortality prediction papers | 9 | 6 | A | confirmed | 目标领域预测证据。 |
| E004 | ICU free-text mortality prediction methods | 8 | 7 | A | confirmed | 非结构化方法类比。 |

## 现有工作是否能替代

不能作为完整现成方案替代。现有证据支持“先抽取、再建模”的架构，但没有提供可以直接拿来用的 ECMO 非结构化抽取与预测 workflow。

## 可复用内容

- `E001` 的 ELSO 字段。
- `E002` 的评分和 baseline 框架。
- `E003` 的 ECMO ML 建模注意事项。
- `E004` 的 ICU notes NLP 模式。

## 不该做什么

- 不要在没有 schema 和时间窗的情况下，用一个 LLM classifier 同时做抽取和预测。
- 不要把 ELSO scores 当作自动临床决策系统；引用 `E002`。
- 不要把私人病历作为搜索证据。

## 使用的负面证据

| negative_evidence_id | 搜索范围 | 覆盖来源 | 判断用途 | 限制 |
| --- | --- | --- | --- | --- |
| N001 | Complete ECMO unstructured extraction-prediction workflow | Registry, papers, ICU NLP | 支持场景定制。 | 不证明不存在。 |

## 下一步

先建立非私人抽取 schema 和 temporal-label plan，再做建模；抽取验证和预测验证需要分开。
