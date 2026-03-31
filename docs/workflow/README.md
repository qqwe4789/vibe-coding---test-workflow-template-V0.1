# Copilot Vibe Coding Workflow (MVP)

这套流程用于在 VS Code + GitHub Copilot 场景下，以可复用、可验证、可回滚的方式完成需求开发。

## 1. 流程阶段

1. 需求入口（Issue Form）
2. 任务拆解（子任务 + 验收标准）
3. 实现执行（Copilot Prompt 模板）
4. 验证门禁（CI + PR 检查）
5. 发布与回滚（Revert PR / 配置降级）
6. 复盘沉淀（周会模板 + 指令更新）

## 2. 角色职责

- 需求提出者：提交结构化 Issue，明确验收标准与风险。
- 实现负责人：按模板拆解任务，执行编码与自测。
- 评审人：验证实现、风险与回滚方案是否完整。
- 仓库管理员：维护分支保护、工作流与模板。

## 3. 输入输出标准

### 阶段 1：需求入口
- 输入：业务目标、范围、约束、截止时间。
- 输出：标准化 Issue（含验收标准、风险等级、回滚预案）。

### 阶段 2：任务拆解
- 输入：主 Issue。
- 输出：子任务列表（每项含 DoD、测试点、依赖关系）。

### 阶段 3：实现执行
- 输入：任务卡 + Prompt 模板。
- 输出：代码变更 + 本地验证记录。

### 阶段 4：验证门禁
- 输入：Pull Request。
- 输出：通过 lint/test/build 和 PR 规范检查。

### 阶段 5：发布与回滚
- 输入：已合并 PR。
- 输出：发布记录；异常时执行标准回滚。

### 阶段 6：复盘沉淀
- 输入：当周交付与故障数据。
- 输出：流程改进项、模板更新项。

## 4. 目录约定

- `docs/workflow/`：流程规范与运行手册。
- `.github/ISSUE_TEMPLATE/`：需求/缺陷/任务模板。
- `.github/workflows/`：CI 与 PR 门禁工作流。
- `prompts/`：Copilot 复用提示词模板。

## 5. 最小执行规则（MVP）

- 所有开发需求必须从 Issue Form 创建。
- 所有代码改动必须通过 Pull Request 合并。
- PR 必须关联 Issue，必须填写验证证据与回滚方案。
- 主分支合并前必须通过 CI 检查。
- 每周一次复盘，更新模板或指令。

## 6. 首次启用步骤

1. 将本仓库中的 `.github/`、`docs/workflow/`、`docs/context/adr/`、`prompts/` 和 `AGENTS.md` 复制到目标项目。
2. 按目标项目实际情况更新 `AGENTS.md` 中的项目背景、技术栈与关键约束。
3. 按目标项目真实命令调整 `.github/workflows/ci.yml`，确认 lint/test/build 可以在 GitHub Actions 中执行。
4. 在 GitHub 仓库设置中为 `main` 开启分支保护，并将 `ci` 与 `pr-check` 设为必需检查。
5. 如需自动请求评审，更新 `.github/CODEOWNERS` 中的拥有者配置。
6. 第一次使用时，先用一个小需求完整跑一遍 Issue → 实现 → PR → 合并流程，再决定是否继续增强规则。
- Bootstrap checks run: 2026-03-31