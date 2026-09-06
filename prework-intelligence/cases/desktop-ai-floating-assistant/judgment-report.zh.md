# 判断报告（中文阅读版）

源文件：`judgment-report.md`  
权威状态：中文阅读副本，不作为 Evidence Pack / Judgment Module 的唯一交接文件。若与源文件不一致，以源文件为准。

## 使用的 Evidence Pack

- Case ID: B1
- Evidence Pack path: `docs/prework-intelligence/cases/desktop-ai-floating-assistant/evidence-pack.md`
- Evidence Pack addendum paths, or `none`: `none`
- Evidence Pack date: 2026-07-09

## 主结论

`场景定制`

## 证据引用

主结论引用：`E001`, `E002`, `E003`, `E004`, `N001`。

## 为什么是这个结论

现有产品说明“桌面 AI 助手 / 快捷唤起 / 选中文本处理 / first-party desktop entry point”这个类别已经成立。但 Evidence Pack 没有证明存在一个成熟、免费、跨平台、Windows 友好、可读取当前上下文、隐私边界清楚、模型/API key 灵活的完整替代方案。

因此不能简单说“没人做过”，也不能直接采用某一个现成产品。更合适的主结论是 `场景定制`：复用已有产品形态和交互模式，再根据目标 surface、权限、隐私和模型选择做定制化比较或实现。

## Claim Matrix 中文解读

| claim_id | 子问题 | 局部结论 | 引用记录 | 中文解释 | 仍缺什么 |
| --- | --- | --- | --- | --- | --- |
| C001 | first-party AI 产品提供桌面入口。 | `直接采用` | E001; E002 | 如果内置能力已经够用，应优先直接用。 | 不同产品 feature parity 不同。 |
| C002 | 第三方 Mac 工具覆盖快捷键/选中文本 workflow。 | `接入改造` | E003; E004 | 这些是强 workflow 参考。 | Windows 适配不确定。 |
| C003 | 完整价值取决于上下文、隐私、模型选择和自动化。 | `场景定制` | E001; E002; E003; E004; N001 | 现有工具覆盖部分需求，不覆盖完整目标。 | 需要 hands-on 约束验证。 |
| C004 | 已存在一个成熟、免费、跨平台的完整方案。 | `先补证据` | N001 | 已搜索范围内没有强证据。 | 更广产品搜索可能细化判断。 |

## 最相关实体

| entity_id | 实体 | relevance_score | reuse_score | source_grade | evidence_status | 在判断中的作用 |
| --- | --- | ---: | ---: | --- | --- | --- |
| E001 | ChatGPT Desktop / Chat Bar | 8 | 7 | S | confirmed | first-party baseline。 |
| E002 | Gemini desktop / Google desktop app | 8 | 7 | S | confirmed | 可比 first-party baseline。 |
| E003 | BoltAI | 9 | 6 | S | confirmed | 强 workflow 参考。 |
| E004 | Elephas / Raycast AI | 8 | 6 | S | confirmed | 可比 workflow 参考。 |

## 现有工作是否能替代

只能替代部分需求。现有产品不能清楚替代完整的 Windows-oriented、context-aware、privacy-controlled、API-flexible assistant。

## 可复用内容

- `E001` 和 `E002` 的 first-party desktop app 预期。
- `E003` 和 `E004` 的快捷键、选中文本命令和工作流模式。
- `N001` 暗含的权限与隐私问题。

## 不该做什么

- 不要把 browser sidebar 叫成全局桌面助手；引用 `N001`。
- 不要假设 overlay chat 就等于能读取当前上下文；引用 `E001`, `E003`, `N001`。

## 使用的负面证据

| negative_evidence_id | 搜索范围 | 覆盖来源 | 判断用途 | 限制 |
| --- | --- | --- | --- | --- |
| N001 | Complete single free cross-platform solution | Product pages and docs | 支持 `场景定制`。 | 不证明不存在。 |

## 下一步

先定义最小目标 surface，再对 Windows-capable candidates 做更窄的 hands-on comparison，然后再决定是否构建。
