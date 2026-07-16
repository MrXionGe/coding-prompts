---
name: using-coding-workflows
description: "为编码任务选择或组合 Spec 驱动开发、自动化测试、调试与修复工作流。适用于需要判断工作流或涉及多个阶段的任务。"
---

# Using Coding Workflows

根据任务的主要目标，选择最少且足够的技能，并加载对应说明：

- 开发或行为变更：`spec-driven-development`
- 功能、接口、UI 或交互验证：`test-functionality`
- Bug、异常或失败测试：`debug-and-fix`

组合技能时按依赖顺序执行，例如开发后测试、修复后回归。简要说明选择理由，复用前序结果，并在目标或证据变化时重新判断。除非用户或上层指令明确要求，否则由当前智能体连续执行，不使用子智能体（sub-agent）。
