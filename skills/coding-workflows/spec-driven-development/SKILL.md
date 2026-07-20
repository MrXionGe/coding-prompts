---
name: spec-driven-development
description: "Guide implementation with a clear Spec and Plan, using TDD when helpful. Use for new projects, features, or behavior changes."
---

# Spec 驱动开发

以可验证的 Spec 对齐目标和验收标准，用 Plan 推进交付，按风险补充测试。

## 工作流

1. 理解需求和项目，形成足够明确的 Spec。
2. 将 Spec 转化为按依赖排序的 Plan，沿用现有模式逐步实现。
3. 对关键行为按需使用 TDD 或其他测试，完成验收并说明结果与风险。

根据任务规模裁剪流程。除非用户或上层指令明确要求，否则不要使用子智能体（sub-agent）。
