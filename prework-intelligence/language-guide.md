# Language Guide

这份文件说明 Prework Intelligence 文档应该用中文、英文还是中英混合。

## 总原则

面向人阅读的说明用中文优先。

面向接口、字段、文件名、query 模板和跨工具约定的内容保留英文。

不要为了中文化而改动字段名。`entity_id`、`relevance_score`、`reuse_score`、`source_grade`、`evidence_status`、`method_similarity` 和 `method_note` 这类字段应保持英文。

## 建议分层

| 文件类型 | 推荐语言 | 原因 |
| --- | --- | --- |
| 状态和推进文件 | 中文优先，保留 phase/status 关键字 | 这些文件主要给人读，用来判断现在走到哪一步。 |
| 方法解释文件 | 中文优先，字段名保留英文 | 方法需要被快速理解，但字段名要稳定。 |
| 模板文件 | 中英混合 | 标题和说明可以中文，字段名和结构键保持英文，方便复制到 Evidence Pack。 |
| Evidence Pack | 中英混合 | 字段名英文，证据摘要和 gaps/risks 可用中文。 |
| Judgment Report | 中文优先 | 判断是给用户看的，结论词本来就是中文。 |
| Strategy Cards | 中文优先，query templates 保留英文 | 搜索策略需要读得懂，但查询模板通常直接复制到英文搜索。 |
| 外部来源标题和 URL | 保持原文 | 避免误引、误译或影响复核。 |
| HTML 展示页 | 中文优先 | 它是阅读入口，不是接口规范。 |

## 双轨文档规则

从 Case 校准阶段开始，允许同一份 case 输出同时存在英文权威版和中文阅读版。

| 文件后缀 | 用途 | 约束 |
| --- | --- | --- |
| `.md` | 英文权威版，供模型读取、继续修改和模块交接使用。 | 字段名、枚举、引用 ID 和表格结构保持稳定。 |
| `.zh.md` | 中文阅读版，供用户审查、介入和复盘使用。 | 不新增证据、不改结论、不替换引用 ID，只翻译和解释权威版内容。 |

中文阅读版必须在开头声明其源文件和权威状态。例如：

```md
源文件：`judgment-report.md`
权威状态：中文阅读副本，不作为 Evidence Pack / Judgment Module 的唯一交接文件。
```

如果 `.md` 和 `.zh.md` 发生冲突，以同目录下的 `.md` 权威版为准。修正流程应先改权威版，再同步中文阅读版。

展示页应优先把 `.zh.md` 作为面向用户的阅读入口，同时保留英文权威版入口，便于模型、复核者或后续 agent 使用。

## 哪些内容应该保留英文

- 文件名和目录名。
- Markdown 模板中的字段名。
- `entity_id`、`negative_evidence_id`、`source_grade` 等接口字段。
- `confirmed`、`single-source`、`conflicting`、`unverified` 等枚举值。
- query templates。
- 外部 source title、URL、repo 名、issue 标题。
- Git commit message 可以继续用英文，便于历史检索。

## 哪些内容应该改成中文

- 当前状态、路线图、下一步、停止规则。
- 方法目的、使用说明、边界解释。
- case 背景、结论理由、复盘。
- strategy card 的 Purpose、When To Use、Execution Steps、Stopping Rules 等说明性段落。
- HTML 展示页中的分组、说明和阅读顺序。

## 当前调整状态

已处理入口和控制层：

- `current-state.md`
- `ROADMAP.md`
- `NEXT_ACTION.md`
- `CHECKLIST.md`
- `AUTORUN.md`
- `framework-map.html`

已处理 Case 1：

- `cases/codex-sidebar-title-management/idea-card.md`
- `cases/codex-sidebar-title-management/search-plan.md`
- `cases/codex-sidebar-title-management/evidence-pack.md`
- `cases/codex-sidebar-title-management/judgment-report.md`
- `cases/codex-sidebar-title-management/case-retrospective.md`

核心方法文件、模板和 strategy cards 暂不整篇翻译，避免一次性改动过大。后续可以按“先方法说明，再策略卡说明，最后模板说明”的顺序逐步中文化。

双轨试点已启动，优先为最需要人工审查的 Case Judgment Report 增加中文阅读版。
