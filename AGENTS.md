# Project Agent Context

Copilot agent 在执行任务前必须先读取本文件，获取项目背景与约束。

## Project Overview

- 本仓库实现一套基于 VS Code + GitHub Copilot 的流程化开发工作流（类 Harness Engineering）。
- 核心原则：最小改动、可验证、可回滚。
- 适用技术栈：Node.js / TypeScript、Python、React / Next.js。

## Architecture Decisions

重要架构决策记录在 `docs/context/adr/` 目录，执行任务前先检查是否有相关 ADR。

## Known Constraints

- 所有代码改动必须通过 PR，禁止直接推送 `main`。
- PR 必须关联 Issue 并填写验证证据与回滚方案。
- 每次改动仅解决一个明确问题，禁止引入无关重构。
- CI 检查（lint / test / build）必须通过后才可合并。

## Key Files & Directories

| 路径 | 用途 |
|---|---|
| `.github/copilot-instructions.md` | 全局 Copilot 行为规则 |
| `.github/instructions/` | 按技术栈的路径级规范 |
| `prompts/` | 标准化 Prompt 模板 |
| `docs/workflow/` | 流程规范与运行手册 |
| `docs/context/adr/` | 架构决策记录 |

## Decision Log Summary

最新决策见 `docs/context/adr/`，重大变更必须先写 ADR 再实现。
