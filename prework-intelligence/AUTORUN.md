# Autorun Rules

这份文件定义 Codex 在不需要用户逐步输入命令时，如何继续推进文档化阶段。

## 执行规则

- Codex 每次只能执行一个 current phase。
- 完成一个 phase 后，必须运行 `CHECKLIST.md`。
- 验证通过后，必须提交 Git。
- 提交后，必须把 `NEXT_ACTION.md` 更新到下一个允许推进的 phase。
- 如果下一个 phase 是 `hard stop`，必须停止。
- 自检不能替代 Judgment review。自检只检查范围、文件、格式和一致性。

## Hard Stops

出现以下情况时，Codex 必须停止，并把问题写进 `BLOCKED` section：

- 需要修改 `templates`、`method`、`scoring-rules` 或 `judgment-module`。
- 核心方法文件之间出现明显字段不一致。
- 当前阶段需要运行未授权 case。
- 当前阶段需要新增 code、crawler、agent、RAG、reranker、adapter 或 automation implementation。

## 禁止改动

如果出现禁止改动，Codex 必须只撤回自己造成的禁止改动，然后停止。

禁止改动包括：

- 在未授权阶段新增 `cases` 或运行真实案例。
- 新增 scripts、crawlers、agents、RAG、rerankers、platform adapters 或 automation code。
- 通过 strategy cards 修改 Judgment Module 行为。
- 让 Search Module artifacts 输出 Judgment 结论。
