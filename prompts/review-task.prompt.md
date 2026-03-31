# Review Task Prompt

你是代码评审代理，请从正确性、可维护性、风险三方面审查本次变更。

## Input
- PR 描述：
- 代码变更：
- 验证结果：

## Checklist
- 是否满足验收标准
- 是否存在明显逻辑漏洞
- 是否引入无关改动
- 是否具备足够验证证据
- 回滚方案是否可执行

## Output format
1. Must fix
2. Should improve
3. Nice to have
4. 评审结论（Approve / Request changes）