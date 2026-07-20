---
name: coding-workflows
description: "Choose and combine four coding workflows: technical feasibility assessment, spec-driven development, functionality testing, and evidence-based debugging/fixing. Use for architecture or integration uncertainty; new projects, features, or behavior changes; acceptance, API, UI, interaction, coverage, or regression testing; and bugs, failures, performance, or environment-specific issues."
---

# 编码工作流

根据任务的主要目标选择一个方向；跨阶段任务按依赖组合。按任务规模和风险裁剪流程，不为流程本身制造文档或扩大工作范围。

## 通用原则

- 先理解用户目标、项目现状、约束和可用证据，再采取行动；区分事实、假设与推测。
- 遵循仓库现有约定，聚焦必要改动，避免无关重构。
- 让验证强度与风险相称，并说明结果、残余风险或阻塞。
- 尊重任务边界；若用户只要求评估、测试或诊断，不自动扩展为正式开发或修复。

## 四个方向

### 技术可行性评估

明确需求、约束和判断标准；结合代码现状与可靠资料评估方案适配性、技术边界、兼容性、依赖和替代方案。必要时用最小实验验证关键假设，给出结论、依据、风险与建议。

### Spec 驱动开发

将需求整理为足够明确、可验证的轻量 Spec，包括目标行为、范围和验收标准；再按依赖形成 Plan，沿用现有模式逐步实现。对关键行为按需使用 TDD 或其他测试，最后按验收标准核对交付。

### 功能测试

围绕用户可观察行为明确预期、范围与主要风险，选择合适的测试层级，以少量高价值测试覆盖主路径、边界、错误场景和关键交互。先定向验证，再按影响范围扩展；UI 或交互任务条件允许时使用真实浏览器。报告通过项、失败项、发现的问题和未覆盖风险。

### 调试与修复

明确预期与实际行为，收集环境、日志和近期变更并尽量稳定复现；沿数据流、状态和调用链缩小范围，用证据验证根因假设。确认根因后做聚焦修复，并验证原始场景及相关回归；说明根因、改动和验证结果，未确认内容标为推测。

## 组合方式

按实际需要串联，例如“可行性评估 → 开发 → 功能测试”或“复现与诊断 → 修复 → 回归测试”。只进入完成当前目标所需的阶段。
