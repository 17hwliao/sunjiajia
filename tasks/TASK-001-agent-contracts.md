# TASK-001：建立 Agent 与 Tool 的基础合约

- 状态：`READY`
- 优先级：`P0`
- 负责人：`待分配`
- 依赖：`无`

## 目标

建立 .NET 8 解决方案的基础项目与稳定的 Tool 合约，使后续聊天模型能请求桌宠动作、RAG 检索和安全确认，而不直接操作系统。

## 范围

- 创建 `NuoNuo.Agent.sln`。
- 创建 `NuoNuo.Agent.Core`、`NuoNuo.Tools.Contracts` 和 `NuoNuo.Tools.Pet` 类库。
- 定义 `ToolDefinition`、`ToolCall`、`ToolResult`、`IToolExecutor`、`IApprovalPolicy` 合约。
- 实现内存版 `PetActionTool`，仅支持 `jump`、`land`、`idle`、`walk`、`run`、`hug`、`sleep`、`curious`。
- 对未知动作返回结构化拒绝结果；不得回退到任意命令执行。
- 提供单元测试和最小控制台演示。

## 不包含

- 不接入真实 WPF 桌宠。
- 不接入网络、MCP、浏览器、鼠标键盘或外部模型 API。
- 不创建或读取用户记忆库。

## 验收标准

- [ ] `dotnet test` 成功。
- [ ] 合法 `jump` 调用返回成功和可序列化的动作事件。
- [ ] 非法动作被拒绝，且不会调用系统进程或文件 API。
- [ ] Tool 输入、输出和错误均能 JSON 序列化。
- [ ] 仓库中没有密钥、个人数据、模型文件、EXE 或 DLL。

## 交付要求

提交说明必须包括运行命令、测试摘要、接口设计理由、已知限制和回滚方式。
