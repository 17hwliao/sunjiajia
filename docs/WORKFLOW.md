# 协作流程

## 任务生命周期

`DRAFT` → `READY` → `IN_PROGRESS` → `REVIEW` → `ACCEPTED` / `RETURNED` / `BLOCKED`

1. 任务发布者在 `tasks/` 创建 `TASK-xxx-*.md`，并将状态设为 `READY`。
2. 执行模型只处理该任务明确列出的范围；不修改无关文件，不提交密钥、个人资料或模型文件。
3. 提交时必须附上：变更摘要、运行命令、测试结果、已知限制和回滚方式。
4. 验收者以 `docs/ACCEPTANCE.md` 审计实现，产出 `audit/TASK-xxx-review.md`。
5. 只有标记为 `ACCEPTED` 的任务才能成为后续任务的依赖。

## 分支与提交

- 一个任务一个分支：`task/TASK-001-agent-contracts`。
- 一个提交只包含一个清晰目的。
- 不允许强推、重写历史或提交二进制模型。
- 所有外部 API Key 只从运行环境或安全凭据读取，绝不提交到仓库。

## 交互反馈格式

验收反馈必须包含：

1. 结论：`ACCEPTED`、`CONDITIONAL`、`RETURNED` 或 `BLOCKED`。
2. 证据：复现命令、测试输出、涉及文件。
3. 风险：隐私、权限、成本、性能和回滚风险。
4. 下一步：一个可执行、可验收的后续任务。
