---
name: using-coding-workflows
description: "为编码任务选择或组合 Spec 驱动开发、自动化测试和调试修复。适用于需要判断工作流或涉及多个阶段的任务。"
---

# Using Coding Workflows

根据任务的主要目标，选择最少且足够的技能并加载其说明：

- 开发或行为变更：`spec-driven-development`
- 功能、接口、UI 或交互验证：`test-functionality`
- Bug、异常或失败测试：`debug-and-fix`

需要组合时按依赖顺序执行，例如开发后测试、修复后回归。简要说明选择及原因，复用前序结果，并在目标或证据变化时重新判断。默认由当前智能体连续执行，不因组合自动创建子智能体。
