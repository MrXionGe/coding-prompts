---
name: debug-and-fix
description: "Find root causes by reproducing issues, gathering evidence, and testing hypotheses, then implement reliable fixes and regression checks. Use for bugs, exceptions, failing tests, performance regressions, or environment-specific problems."
---

# 调试与修复

用证据缩小范围，修复根因，避免靠堆叠补丁碰运气。

## 工作流

1. 明确预期行为、实际行为、影响范围和运行环境，收集错误信息、日志与近期变更，并尽量获得稳定的最小复现。
2. 沿数据流、状态变化和调用链追踪最早出现的偏差，提出可验证的根因假设，并优先验证信息增益最高的假设。
3. 确认根因后，实施符合现有设计的最小修复，并在适合时补充回归测试。
4. 重新验证原始场景，并运行受影响范围内的检查；假设被否定时回到定位阶段，不累积试探性改动。

最终说明根因、关键证据、修复内容、验证结果和剩余风险；未确认的结论明确标注为推测。
