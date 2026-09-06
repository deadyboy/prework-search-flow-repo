# Case Retrospective

## 哪些字段本案例确实需要？

- `method_similarity` 和 `method_note` 有用。它们把“API 层能改 thread name”和“完整 sidebar governance workflow”区分开了。
- `reuse_score` 有用。它能区分官方 API、风险较高的 patcher、以及只能借鉴模式的相邻产品。
- `negative_evidence_id` 有用。这个案例需要记录：在官方文档和公开产品/开源来源中，没有找到完整安全流程。
- `gaps` 和 `risks` 必要。具体 surface 是否可用、本地状态是否安全、patcher 是否可复用，这些都不能省略。

## 哪些搜索源最有用？

- 官方 Codex app-server docs 最有用，因为它给出了最强的可复用基础。
- Codex changelog 和 configuration docs 是有价值的支撑来源，能证明 thread rename 不是孤立概念。
- `openai/codex` GitHub issues 很有用，能看到用户痛点、缺失 surface 和近期 feature request。
- 目的很明确的 open-source patcher 有用。它提供了实现模式，也暴露了安全风险。

## 哪些搜索源浪费时间或未能覆盖？

- 泛产品搜索大多只找到相邻 AI chat managers，不是 Codex-specific title governance。
- ChatGPT Help Center 只能提供相邻产品模式，不能直接证明 Codex 支持。
- academic paper search 对本案例帮助不大，所以没有执行。
- 本地 Codex state 没有检查。这是有意的，因为它可能涉及私人 thread data，而且第一次公开来源案例不需要它。

## 评分是否稳定，哪里不稳定？

- `relevance_score` 对官方 API 和公开 issue 比较稳定。
- `reuse_score` 不太稳定，因为它取决于用户实际使用的 Codex surface，以及 app-server 或 UI rename access 是否暴露。
- `source_grade` 对官方文档和 GitHub issues 比较稳定；对产品页和项目自写文档要更谨慎。
- `evidence_status` 对“公开记录是否存在”比较稳定，但对“当前 client 行为”不稳定，因为没有做 hands-on UI verification。

## Judgment Report 的结论是否能指导行动？

可以。报告把下一步收窄为：先审查 Case 1 输出，再用非私人 test thread 验证当前 Codex Desktop 或 app-server rename availability。验证前不应该设计更大的 title-governance workflow。

这个结论也避免了两件事：一是直接改本地数据库，二是在 surface-specific safety 没确认前做大范围自动化。

## Proposed future changes

- 后续案例可以考虑增加轻量字段 `surface_scope`，用来标记 desktop app、VS Code extension、CLI、app-server、remote thread 或 web product。
- Evidence Pack 可以更清楚地标记：哪些 private/local sources 是因为隐私原因有意不搜。
- Strategy cards 后续可以提醒：official API capability 和 complete user-facing workflow support 不是一回事。
