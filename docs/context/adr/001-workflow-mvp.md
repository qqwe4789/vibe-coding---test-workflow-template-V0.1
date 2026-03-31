# ADR-001: 采用 Copilot 流程化工作流 MVP

## Status

Accepted

## Date

2026-03-31

## Context

团队使用 VS Code + GitHub Copilot 进行开发，但缺乏标准化流程，导致：
- AI 生成代码无约束，质量不稳定
- 需求拆解随意，验收标准不清晰
- PR 缺少验证证据和回滚方案
- 无法度量流程效率与稳定性

## Decision

采用基于 Harness Engineering 方法论的单仓库 MVP 工作流，包含：
- Copilot 仓库级指令（`copilot-instructions.md`）约束 AI 行为
- 结构化 Issue/PR 模板强制输入输出标准化
- CI + PR 门禁工作流做最小验证
- DORA 四指标做首期度量基线
- ADR 沉淀关键决策，避免上下文丢失

不接入 Harness 产品，仅对齐其方法论。

## Alternatives Considered

- **直接使用 Copilot 无约束**：效率高但质量不稳定，放弃。
- **接入完整 Harness 产品栈**：成本高、初期过重，放弃。
- **使用第三方工作流平台**：增加外部依赖，放弃。

## Consequences

- 正面：流程可复用、可度量、可回滚；AI 行为更可预期。
- 负面：需要团队遵守模板规范，初期有适应成本。
- 后续关注：根据复盘结果迭代模板，季度评估是否引入更多自动化检查。
