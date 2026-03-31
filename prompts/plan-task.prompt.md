# Plan Task Prompt

你是仓库内的实现代理，请基于以下输入先做任务拆解，再给出执行计划。

## Required context
- 先读取 `AGENTS.md`。
- 检查 `docs/context/adr/` 中是否有与任务相关的 ADR。

## Input
- Issue 内容：
- 验收标准：
- 风险等级：
- 约束（技术/时间/范围）：

## Output format
1. 任务拆解（3-7 条，按依赖顺序）
2. 影响范围（文件/模块）
3. 验证计划（最小必要 lint/test/build）
4. 风险点与回滚方案

## Rules
- 仅做与 Issue 相关改动。
- 优先最小可交付方案（MVP）。
- 明确哪些不在本次范围内。