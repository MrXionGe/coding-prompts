---
name: assess-technical-feasibility
description: "Assess whether a technical approach is feasible and appropriate through evidence-based research, compatibility analysis, and minimal experiments. Use before development for architecture choices, cross-technology integration, dependency compatibility, or significant technical uncertainty."
---

# 技术可行性评估

在正式开发前判断方案是否可实现、适合采用，并能与现有系统协调。不要把“能拼起来”当作“值得采用”。

## 工作流

1. 明确需求、约束、候选方案和判定标准，区分事实与假设。
2. 结合项目现状和权威一手资料，核对版本、平台、接口、生命周期、数据模型与运行边界。
3. 评估需求匹配度、各项技术的架构边界与心智模型是否协调，以及兼容性、性能、成本、复杂度和维护风险；同时比较更简单的替代方案。
4. 通过隔离、最小化的 PoC、spike 或 benchmark 验证关键不确定性；除非明确要求，不进入正式开发。
5. 给出可行、有条件可行、不可行、不建议或证据不足的结论，说明可追溯依据、冲突、适用条件、风险和下一步。

除非用户或上层指令明确要求，否则不要使用子智能体（sub-agent）。
