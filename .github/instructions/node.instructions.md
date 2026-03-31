---
applyTo: "**/*.{ts,js,mts,cts}"
---
# Node.js / TypeScript Instructions

- 新增逻辑优先显式处理错误路径。
- 对公共函数保持输入校验与稳定返回。
- 与外部系统交互时，失败信息应可定位。
- 保持模块职责单一，避免一次提交跨层改动。
- 若项目已启用 lint/typecheck，提交前必须通过。