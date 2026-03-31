# Branch & Merge Policy

## 1. 分支命名

- 功能分支：`feat/<issue-id>-<short-name>`
- 修复分支：`fix/<issue-id>-<short-name>`
- 维护分支：`chore/<issue-id>-<short-name>`

示例：`feat/123-user-search`

## 2. 分支策略

- 采用 GitHub Flow：短生命周期分支，PR 合并到 `main`。
- 禁止直接向 `main` 推送。
- 每个 PR 仅解决一个明确问题，避免过大改动。

## 3. PR 合并门禁（建议设为必需）

- 至少 1 位评审通过。
- 必需状态检查全部通过（`ci`、`pr-check`）。
- PR 模板字段完整（关联 Issue、验证证据、回滚计划）。
- 会话中的关键评论已解决。

## 4. 合并方式

- 默认使用 Squash Merge，保证主干历史简洁。
- 合并标题建议遵循 Conventional Commits：
  - `feat: ...`
  - `fix: ...`
  - `chore: ...`

## 5. 紧急修复

- 紧急修复使用 `fix/hotfix-<id>-<name>`。
- 同样通过 PR 流程，至少保留最小验证（lint + 关键测试）。
- 合并后必须在下一个工作日补齐复盘记录。