# Copilot Vibe Coding 工作流模板

一套基于 **VS Code + GitHub Copilot** 的流程化开发工作流，参考 Harness Engineering 方法论。

核心原则：**最小改动、可验证、可回滚**。

---

## 这是什么？

帮助开发者在使用 GitHub Copilot 编写代码时，保持规范、可追溯、可回滚的开发流程。适用于个人项目和团队协作。

适用技术栈：Node.js / TypeScript、Python、React / Next.js。

---

## 目录结构

| 路径 | 用途 |
|---|---|
| `.github/copilot-instructions.md` | 全局 Copilot 行为规则，约束 AI 生成代码的边界 |
| `.github/instructions/` | 按技术栈的路径级规范（frontend / node / python） |
| `prompts/` | 标准化 Prompt 模板，直接复制到 Copilot Chat 使用 |
| `docs/workflow/README.md` | 完整流程规范与运行手册（6 阶段工作流） |
| `docs/context/adr/` | 架构决策记录，沉淀关键决策避免上下文丢失 |
| `AGENTS.md` | AI agent 必读上下文，描述项目背景与约束 |

---

## 快速开始（复用到你的项目）

**第 1 步：复制核心文件**

将以下目录和文件复制到你的目标项目根目录：

```
.github/
docs/workflow/
docs/context/adr/
prompts/
AGENTS.md
```

**第 2 步：更新 `AGENTS.md`**

打开 `AGENTS.md`，按你的项目实际情况修改：
- `Project Overview`：填写你的项目背景和技术栈
- `Known Constraints`：填写你的约束条件
- `Key Files & Directories`：更新关键路径说明

**第 3 步：调整 CI 工作流**

打开 `.github/workflows/ci.yml`，将 lint / test / build 命令替换为你项目真实的命令。

**第 4 步：开启 GitHub 分支保护**

在 GitHub 仓库 → Settings → Branches → 为 `main` 分支开启保护规则，并将 `ci` 设为必需检查。

**第 5 步：跑通第一个完整流程**

用一个小需求完整走一遍：**创建 Issue → 新建分支 → 用 Prompt 编码 → 提交 PR → 合并**，熟悉整套流程后再扩展规则。

---

## Prompt 模板使用方式

| 场景 | 文件 |
|---|---|
| 新任务拆解 | `prompts/plan-task.prompt.md` |
| 编码实现 | `prompts/implement-task.prompt.md` |
| PR 评审 | `prompts/review-task.prompt.md` |
| 周复盘 | `prompts/retro.prompt.md` |

打开对应文件 → 复制内容 → 粘贴到 Copilot Chat → 填入 Issue/PR 上下文 → 按输出执行。

---

## 核心规则

- 禁止直接推送 `main`，所有改动走 Pull Request
- PR 必须关联 Issue，必须填写验证证据与回滚方案
- 每次 PR 只解决一个问题，禁止引入无关重构
- CI（lint / test / build）必须通过才能合并

---

## 详细文档

- 完整流程规范：[docs/workflow/README.md](docs/workflow/README.md)
- 架构决策记录：[docs/context/adr/](docs/context/adr/)
