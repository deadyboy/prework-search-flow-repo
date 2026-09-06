# Evidence Pack

这是 Search Module 交给 Judgment Module 的唯一交接物。它只记录证据、评分、缺口和负面搜索范围，不输出最终判断。

## Case Metadata

- Case ID: PI-C001
- Idea title: Codex sidebar title management
- Original idea: 判断 Codex sidebar thread title 是否可控，是否已有官方或可复用方案，以及是否值得做一套安全的标题治理流程。
- Search level: L2 standard scan
- Search date: 2026-07-04
- Searcher: Codex

## Coverage Summary

- Searched source classes: official OpenAI docs; OpenAI Help Center; OpenAI Developer Community; GitHub repository/issues; GitHub/web search for open-source implementation; product/tool substitutes; public communities.
- Unsearched source classes: private local `.codex` data; private conversation content; patent sources; academic paper indexes.
- Languages searched: English; general web 中少量中文产品词。
- Timebox: 单次 Codex run 内完成的 L2 scan。
- Coverage note: 找到了官方 Codex app-server 文档、公开 issue 讨论、一个具体的开源 patcher，以及相邻的 chat-management 产品。没有检查私人本地状态。论文没有搜索，因为本案例是操作工具问题，不是研究方法问题。

## Query Log

| query_id | source_class | source_name | query | result_count | kept_entities | notes |
| --- | --- | --- | --- | ---: | --- | --- |
| Q001 | official docs | OpenAI Developers / Help | `site:developers.openai.com/codex Codex sidebar title rename`; `site:help.openai.com Codex rename thread title sidebar` | 10+ | E001; E004; N001 | 找到 Codex app-server thread naming API、Codex changelog/config 相关引用，以及相邻的 ChatGPT chat-management 文档。 |
| Q002 | official docs | OpenAI Developers | `site:developers.openai.com/codex "thread/name/set"`; `site:developers.openai.com/codex "thread" "title" "rename"` | 4 | E001 | 找到 `thread/name/set`、`thread.name` 和 `thread.rename` metric references。 |
| Q003 | GitHub issues | openai/codex | `site:github.com/openai/codex/issues rename thread title Codex` | 10+ | E002 | 找到多个关于 Codex thread/task title renaming 的 feature requests 和 bug reports。 |
| Q004 | GitHub / open source | GitHub and web constrained to GitHub | `codex thread renamer patcher vscode`; `"codex-thread-renamer-patcher" GitHub` | 5+ | E003 | 找到一个面向 VS Code 的 Codex thread renamer patcher。 |
| Q005 | communities | OpenAI Developer Community / Reddit | `Codex VSCode Extension how to name rename task`; `Codex app threads should be able to rename themselves` | 5+ | E002; N002 | 找到公开 workaround 和 feature-request discussions。 |
| Q006 | product substitutes | General web / product docs | `chat history title management AI chat rename conversation product`; `AI chat conversation title manager extension` | 10+ | E004 | 找到相邻的 chat-management / chat-history 产品，但不是 Codex-specific substitute。 |
| Q007 | negative search | official docs / GitHub / product web | `Codex sidebar title does not support rename`; `Codex thread title limitation`; `Codex thread rename no open source`; `Codex thread rename deprecated` | 10+ | N001; N002 | 找到限制和需求讨论；没有找到成熟、独立、Codex-specific 的 title-governance 产品或工具。 |

## Entity Records

每个 entity 聚合一个对象，不按 URL 聚合。

### Entity E001

- entity_id: E001
- entity_name: Codex app-server thread naming API
- entity_type: official feature / developer API
- core_function: 提供官方 app-server 方法，用于设置或更新用户可见的 thread name，并在 thread API responses 中暴露 thread name。
- relevance_score: 10
- reuse_score: 7
- method_similarity: 2
- method_note: 这个方法直接修改用户可见的 thread name，和标题管理的底层需求高度一致。但它是 API 能力，不是完整的用户审核型 sidebar 工作流。
- source_grade: S
- evidence_status: confirmed

#### Main Source

- title: App Server - Codex
- url_or_local_reference: https://developers.openai.com/codex/app-server
- accessed_at: 2026-07-04
- source_grade: S
- source_excerpt_or_summary: 官方 Codex app-server docs 把 `thread/name/set` 列为设置或更新 thread user-facing name 的 API method，并说明 `thread.name` 会出现在 read/list/resume responses 中。

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Advanced Configuration - Codex | https://developers.openai.com/codex/config-advanced | 2026-07-04 | S | Telemetry 包含 `thread.rename`，说明 thread rename 是 Codex 已识别的事件。 |
| Changelog - Codex | https://developers.openai.com/codex/changelog | 2026-07-04 | S | Changelog 提到 renamed thread titles 的维护项，包括 reconciliation 时保留 renamed titles，以及修复 forked thread name inheritance。 |
| Auto-generate and apply a concise thread name after the first prompt | https://github.com/openai/codex/issues/24289 | 2026-07-04 | A | 公开 issue 提到 Codex 存在 manual rename path，并请求复用它做 first-prompt 自动命名。 |

#### Key Facts

这些事实直接来自上面列出的来源。

- app-server API overview 包含 `thread/name/set`，用于设置或更新 thread name。
- 当 user-facing title 已设置后，Thread API responses 可能包含 `thread.name`。
- Codex docs 和 changelog 中有 thread-rename 相关引用，但本次未找到完整的用户审核型 sidebar title-governance workflow 文档。
- 官方来源能证明 capability 存在，但不能证明 batch title governance 的安全性或 UX 完整性。

#### Similarity Notes

- Problem similarity: 同一个 metadata/title 层问题。
- User similarity: 部分重叠，面向 app-server client 和管理 Codex threads 的用户。
- Input similarity: 相同或等价，即 Codex thread id 和目标 thread name。
- Output similarity: 相同，即 user-facing thread name。
- Workflow similarity: 部分相似。它是 API-level update，不是完整 sidebar review workflow。
- Constraint similarity: 有部分共同约束。它是官方路径，但集成方式和 review process 仍需设计。

#### Reuse Notes

- Reusable parts: 官方 thread-name setter、thread response 中的 thread-name hydration、thread-related events。
- Integration cost: 中等；需要 client 或 app-server integration 安全调用 API。
- License or terms: 官方 Codex API 文档；可用性取决于产品/API access 和支持的 client context。
- Maintenance signal: 官方文档和 changelog 引用，维护信号强。

#### Gaps

- 没找到官方用户文档说明 Codex Desktop sidebar bulk title review flow。
- 需要确认不同 surface 的可用性：desktop app、VS Code extension、CLI、remote threads 和当前 app 环境可能不同。
- 需要确认在不读取私人 thread content 的前提下，是否能支持用户审核和安全批量更新。

#### Risks

- API capability 可能受 client、environment、loaded-thread state 或 experimental API options 限制。
- 如果未经 review 直接改标题，可能影响用户导航。
- API-level capability 不能自动解决 title-generation quality。

### Entity E002

- entity_id: E002
- entity_name: Public Codex rename feature-request cluster
- entity_type: issue/discussion cluster
- core_function: 记录 VS Code、CLI、Cursor、Codex Desktop 等场景中，用户对 Codex thread/task/session title rename 的需求和限制。
- relevance_score: 9
- reuse_score: 3
- method_similarity: 1
- method_note: 这些 issue/discussion 描述的是同一个用户问题和期望工作流，但它们是需求证据和产品缺口证据，不是可复用实现。
- source_grade: A
- evidence_status: confirmed

#### Main Source

- title: Allow renaming task/thread titles to improve history navigation - openai/codex issue #12564
- url_or_local_reference: https://github.com/openai/codex/issues/12564
- accessed_at: 2026-07-04
- source_grade: A
- source_excerpt_or_summary: 该 issue 描述 VS Code extension context 中多个自动生成的 Codex task/chat titles 难以区分，用户找回旧任务困难，因为当时没有明显的 rename action。

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Add ability to rename Codex chat/session titles - openai/codex issue #15533 | https://github.com/openai/codex/issues/15533 | 2026-07-04 | A | 请求在 Codex conversation titles 的 UI/CLI surfaces 中加入 built-in rename。 |
| Ability to manually rename Codex chat/thread titles in the VS Code extension - openai/codex issue #16089 | https://github.com/openai/codex/issues/16089 | 2026-07-04 | A | 描述日常 parallel-chat pain，并请求 persistent rename behavior。 |
| Codex app threads should be able to rename themselves - OpenAI Developer Community | https://community.openai.com/t/codex-app-threads-should-be-able-to-rename-themselves-e-g-to-include-pr/1376537 | 2026-07-04 | B | 描述 PR 出现后标题应演进的工作流，但仍由用户手动应用 title。 |
| Codex VSCode Extension - How to name/rename a task? - OpenAI Developer Community | https://community.openai.com/t/codex-vscode-extension-how-to-name-rename-a-task/1375697 | 2026-07-04 | B | 包含手动修改本地文件的 workaround，并提醒不要让 prompt 直接驱动数据库或文件修改。 |

#### Key Facts

这些事实直接来自上面列出的来源。

- 公开 Codex issues 反复提到：自动生成标题在 history/sidebar views 中难以区分。
- 用户请求覆盖 UI action、command palette action、CLI/resume picker action，以及 agent-initiated 或 automatic naming。
- 社区 workaround 包含手动编辑本地 index data。这对安全约束很重要，但不能当成支持的用户工作流。

#### Similarity Notes

- Problem similarity: 同一个核心问题。
- User similarity: 相同或高度重叠的 Codex power users。
- Input similarity: 同一个对象，即现有 Codex threads/tasks/chats。
- Output similarity: 同一个期望输出，即更清楚的 user-facing titles。
- Workflow similarity: 用户痛点高度一致，但没有直接实现。
- Constraint similarity: 和 privacy/safety 约束强相关，因为 workaround 涉及本地 Codex state。

#### Reuse Notes

- Reusable parts: 问题表述、UI 期望、安全提醒、术语。
- Integration cost: 作为需求素材成本低；没有直接代码可复用。
- License or terms: 公开 GitHub/community discussions。
- Maintenance signal: 2026 年多个近期 issue 和 community posts。

#### Gaps

- Issue 页面不能证明当前每个 client version 是否已经暴露 rename path。
- 社区 workaround 不是权威来源，也不应当作为安全实现指南。
- 在断言 client availability 前，需要官方 surface-specific 文档或实际 UI 证据。

#### Risks

- 如果 Codex 后续添加了 rename support，部分 issue 可能已经过时。
- 不同 surface 行为可能不同：Desktop、VS Code、CLI、Cursor、remote threads。

### Entity E003

- entity_id: E003
- entity_name: Just-Boring-Cat/codex-thread-renamer
- entity_type: open-source project
- core_function: patch VS Code OpenAI ChatGPT/Codex extension，加入 live thread rename UI commands 和 persistence helpers。
- relevance_score: 8
- reuse_score: 5
- method_similarity: 2
- method_note: 这个项目直接实现了 Codex thread renaming 的 sidebar/UI 场景，但方式是 patch 已安装 extension，而不是走完全支持的用户工作流。
- source_grade: A
- evidence_status: single-source

#### Main Source

- title: Just-Boring-Cat/codex-thread-renamer
- url_or_local_reference: https://github.com/Just-Boring-Cat/codex-thread-renamer
- accessed_at: 2026-07-04
- source_grade: A
- source_excerpt_or_summary: 该 repo 描述了一个面向 OpenAI ChatGPT/Codex VS Code extension 的 patcher，提供 command palette rename、sidebar context-menu rename、inline title editing、shortcuts、live title updates 和 backup/verify steps。

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Codex Thread Renamer Patcher for VS Code | https://documents.theboringcat.com/documents/codex-thread-renamer-patcher-for-vscode | 2026-07-04 | B | 二级项目文档描述了同一个 patcher 和兼容性主张。 |

#### Key Facts

这些事实直接来自上面列出的来源。

- 项目目标是 OpenAI ChatGPT/Codex VS Code extension，不一定适用于 Codex Desktop。
- 它会修改已安装 extension files，并在应用前创建备份。
- 它要求 Node.js 和 `sqlite3` CLI，并建议先 verify 再 apply。
- 它通过 command palette、sidebar context menu、inline editing 和 keyboard shortcut 暴露 rename。

#### Similarity Notes

- Problem similarity: 同一个 thread title management 问题。
- User similarity: 相同或重叠的 Codex VS Code users。
- Input similarity: 现有 Codex extension thread data。
- Output similarity: Codex sidebar 中持久化的 thread title。
- Workflow similarity: 对 VS Code extension 高度相似；对 desktop app 不确定。
- Constraint similarity: 部分冲突，因为 patch installed extension files 比期望的安全治理流程风险更高。

#### Reuse Notes

- Reusable parts: UI pattern、安全检查、backup/verify 概念、persistence concerns。
- Integration cost: 中到高；patcher 强依赖特定环境，且侵入性较高。
- License or terms: 复用前应检查 repository license。
- Maintenance signal: repo 和 quick start 存在，但独立来源支持有限。

#### Gaps

- 本次 scan 没找到独立可靠性验证。
- 没确认它和当前 Codex Desktop 的兼容性。
- license 和 release maturity 没有完整审计。

#### Risks

- 修改已安装 extension files 可能在更新后失效。
- 直接 cache 或 SQLite fallback 相关行为，如果没有严格用户审查，可能不安全。
- 如果不加 guardrails 复用，可能把风险较高的 local-state edits 正常化。

### Entity E004

- entity_id: E004
- entity_name: Adjacent AI chat history and title-management patterns
- entity_type: product/workflow substitute cluster
- core_function: 说明 AI chat 产品和 extensions 常见 chat history search、archive/delete、manual rename 或跨平台 conversation management 模式。
- relevance_score: 5
- reuse_score: 3
- method_similarity: 1
- method_note: 相邻产品使用相似的 chat-history 和 title-management 思路，但不能直接管理 Codex sidebar threads。
- source_grade: B
- evidence_status: confirmed

#### Main Source

- title: Autopilot - Chat history
- url_or_local_reference: https://docs.uipath.com/autopilot/other/latest/user-guide/chat-history
- accessed_at: 2026-07-04
- source_grade: A
- source_excerpt_or_summary: UiPath Autopilot docs 描述 chat history access、search，以及对 chat history entries 的 rename；默认标题来自初始 prompt 或生成摘要。

#### Support Sources

| title | url_or_local_reference | accessed_at | source_grade | supports_which_claim |
| --- | --- | --- | --- | --- |
| Group Chats in ChatGPT | https://help.openai.com/en/articles/12703475-group-chats-in-chatgpt | 2026-07-04 | S | OpenAI Help 记录了 ChatGPT group chats 的 rename action。 |
| How to Delete and Archive Chats in ChatGPT | https://help.openai.com/en/articles/8809935-how-to-delete-and-archive-chats-in-chatgpt | 2026-07-04 | S | OpenAI Help 记录了 ChatGPT sidebar archive/delete 管理，作为相邻 chat-history controls 证据。 |
| ContextWizard - AI Chat Manager & Search | https://chromewebstore.google.com/detail/contextwizard-ai-chat-man/lmhnmmedgmnfggecdalkancllnekofnb?hl=en | 2026-07-04 | B | Chrome Web Store listing 描述跨平台 AI conversation capture、organization 和 search。 |
| Chat Memo - AI Conversation Manager | https://chatmemo.ai/ | 2026-07-04 | C | 产品页声称支持 mainstream assistants 的 local storage 和 cross-platform AI conversation management。 |

#### Key Facts

这些事实直接来自上面列出的来源。

- 相邻 AI 产品提供 chat history search 和 rename patterns。
- ChatGPT group chat rename 有公开文档，但本次搜索的 Help Center 页面没有证明 Codex sidebar rename UI 等价存在。
- 跨平台 conversation-manager extensions 通常关注 capture/search，不直接管理 Codex Desktop sidebar thread titles。

#### Similarity Notes

- Problem similarity: 相关问题，但不是同一对象。
- User similarity: 都是 AI power users，但不一定是 Codex developers。
- Input similarity: chat sessions，而不是 Codex thread objects。
- Output similarity: 更容易导航的 chat history。
- Workflow similarity: 有可借鉴的 workflow。
- Constraint similarity: conversation-management tools 也有 privacy 和 local-storage 约束。

#### Reuse Notes

- Reusable parts: rename UI pattern、chat-history search pattern、privacy language、user-review expectations。
- Integration cost: 如果适配 Codex，成本高；多数工具不暴露 Codex-specific title APIs。
- License or terms: 复用前需要逐个检查 product-specific terms。
- Maintenance signal: 官方文档稳定；浏览器 extension 和产品页主张需要单独复核。

#### Gaps

- 没找到一个可以端到端安全治理 Codex sidebar titles 的产品。
- 产品页通常不足以评估 privacy 和 local data handling。

#### Risks

- 相邻工具可能收集 conversation content，带来 privacy 和 compliance risk。
- 通用 AI conversation managers 不一定能看到本地 Codex Desktop 或 VS Code extension state。

## Information Gaps

以下缺口可能影响后续判断。

- Surface-specific availability 尚未完全验证：Codex Desktop、VS Code extension、CLI、Cursor integration 和 remote-thread behavior 可能不同。
- 没有检查本地 Codex database、config 或 private session content。
- 没有在 Codex Desktop 或 VS Code 中做 hands-on UI test。
- package registry 和 VS Code Marketplace 只通过 web search 粗查，没有做完整 registry audit。
- academic paper sources 未搜索，因为本案例没有明显研究方法依赖；这是未搜索的可选 source-class note，不是 negative evidence。
- 开源 patcher 的 license 和 maintenance maturity 没有完整审计。

## Negative Evidence Records

Negative Evidence 只表示：在明确覆盖的 source classes、queries 和 limits 内，没有发现强证据。它不能表示绝对不存在。

### Negative Evidence N001

- negative_evidence_id: N001
- searched_claim: 公开官方文档提供了完整的 Codex Desktop sidebar title-governance workflow，包含 review、batch naming 和 safety rules。
- searched_source_classes: Official OpenAI Codex docs, Codex changelog, OpenAI Help Center.
- searched_queries: `site:developers.openai.com/codex Codex sidebar title rename`; `site:developers.openai.com/codex "thread/name/set"`; `site:help.openai.com Codex rename thread title sidebar`; `site:developers.openai.com/codex "sidebar" "title"`.
- result: 找到了官方 thread name setting API 证据，但没有找到一页完整的公开官方文档，描述 reviewed sidebar title-governance workflow。
- interpretation_limit: 这只覆盖本次搜索的公开官方文档。它不能排除 UI features、private docs、newly released client behavior 或 environment-specific tools。

### Negative Evidence N002

- negative_evidence_id: N002
- searched_claim: 已有成熟、安全、独立的 open-source 或 product solution，端到端覆盖 Codex sidebar title governance。
- searched_source_classes: GitHub repository search via web, GitHub issues/discussions, product web search, Chrome Web Store, OpenAI Developer Community.
- searched_queries: `codex thread renamer patcher vscode`; `"codex-thread-renamer-patcher" GitHub`; `Codex thread rename no open source`; `chat history title management AI chat rename conversation product`; `AI chat conversation title manager extension`.
- result: 找到了 VS Code extension patcher 和相邻 AI conversation managers，但没有发现成熟、受支持、非侵入式、Codex-specific 的完整治理流程。
- interpretation_limit: 这不表示此类方案不存在。它只表示本次覆盖的公开来源和 query families 内没有找到强证据。

## Negative Search Scope

记录已经搜索过的 failure cases、complaints、limitations、abandoned projects 和 alternative approaches。未搜索的 source classes 要明确说明。

- 已搜索的 failure / limitation terms 包括 `not supported`、`no supported rename action`、`feature request`、`limitation`、`manual rename`、`no open source`、`patcher`、`workaround` 和 `does not support`。
- 公开 GitHub 和 community evidence 显示：用户确实遇到 auto-generated titles、missing rename surfaces 和 unsafe local-file workarounds 相关问题。
- negative evidence 只覆盖上面列出的公开来源和 queries，不描述 private Codex product state 或未被索引的 internal tools。

## Search Module Notes

这里只记录搜索限制和不确定性，不包含最终建议。

- 最强复用证据是官方 app-server 支持 setting thread names。
- 最强缺口证据是：公开 issue 和 community posts 说明 API/partial support 与完整安全 sidebar workflow 不是一回事。
- 没有检查私人 `.codex` 文件、本地数据库、private thread content 或 account-specific settings。
- 分数只是 Search Module 的结构化估计，用于交接给 Judgment Module，不是最终判断。
