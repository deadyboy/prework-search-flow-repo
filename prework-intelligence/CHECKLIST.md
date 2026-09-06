# Verification Checklist

每个无人值守阶段或已授权案例阶段结束后，运行这份检查清单。

## Git

- 运行 `git status --short --branch`。
- 运行 `git diff --check`。

## 占位符检查

- 搜索 `TODO`、`TBD`、`FIXME` 和 `??`。
- 命中内容必须是有意保留的说明文本，或者在提交前修掉。

## 禁止产物检查

- 在 strategy-card 阶段，确认没有新增 `cases` 目录。
- 在已授权 case 阶段，确认只新增当前 case 目录和允许的 case 文件。
- 确认没有新增 scripts、crawlers、agents、RAG、rerankers、platform adapters 或 automation code。
- 确认没有新增当前阶段之外的 strategy card。

## 策略卡边界

- 检查 strategy cards 是否只服务 Search Module。
- 检查 strategy cards 是否没有输出 Judgment 结论。
- 检查 strategy cards 是否只把结果交给 Evidence Pack。

## 架构边界

- 检查 Search Module 和 Judgment Module 是否仍然分离。
- 检查 Search Module 是否只输出 Evidence Pack records。
- 检查 Judgment Module 是否只读取 Evidence Pack records。

## 同步检查

- 检查 `strategy-cards/README.md` 的 Available Strategy Cards 是否同步。
- 检查 `current-state.md` 是否同步。
- 检查 `NEXT_ACTION.md` 是否指向正确的下一阶段。
