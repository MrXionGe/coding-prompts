---
name: using-coding-workflows
description: "Select or combine technical feasibility assessment, spec-driven development, automated testing, and debugging workflows for coding tasks. Use when choosing a workflow or coordinating multiple development stages."
---

# 使用编码工作流

根据任务的主要目标，选择最少且足够的技能，并加载对应说明：

- 开发前的方案、选型、兼容性或关键技术存在较大不确定性：`assess-technical-feasibility`
- 开发或行为变更：`spec-driven-development`
- 功能、接口、UI 或交互验证：`test-functionality`
- 已有实现存在 Bug、异常、失败测试、性能退化或环境差异：`debug-and-fix`

组合技能时按依赖顺序执行，例如先评估可行性再开发、开发后测试、修复后回归。简要说明选择理由，复用前序结果，并在目标或证据变化时重新判断。除非用户或上层指令明确要求，否则由当前智能体连续执行，不使用子智能体（sub-agent）。
