# Coding Prompts

个人维护的智能体提示词与编码工作流技能集合。当前主要用于 Codex，同时保持简单、开放的 Markdown 结构，便于在 OpenCode 等支持 Agent Skills 的工具中使用。

## 内容

- [`AGENTS.md`](AGENTS.md)：本机环境与通用工作约定。
- [`coding-workflows`](skills/coding-workflows/)：一个可独立安装和调用的编码工作流 Skill，包含四个方向：
  - 技术可行性评估：在开发前判断方案适配性、技术兼容性和关键风险。
  - Spec 驱动开发：以轻量 Spec 和 Plan 推进实现，按风险补充测试。
  - 功能测试：围绕功能、接口、UI 和交互开展自动化验证。
  - 调试与修复：通过复现和证据定位根因、聚焦修复并回归验证。

四个方向统一写在一个 `SKILL.md` 中，由模型根据任务自行选择、裁剪和组合。在 Codex 中，该 Skill 已禁止隐式触发，需使用 `$coding-workflows` 手动调用。

## 手动安装到 OpenCode

### 提示词

将 [`AGENTS.md`](AGENTS.md) 复制或合并到以下位置：

- 项目级：目标项目根目录下的 `AGENTS.md`
- 全局级：`%USERPROFILE%\.config\opencode\AGENTS.md`

当前提示词描述的是本机环境，更适合作为全局规则。它写明了 Windows 11 和 `mise`；其他使用者应按实际环境调整后再安装。目标位置已有文件时应合并内容，不要直接覆盖。详见 [OpenCode 规则文档](https://opencode.ai/docs/zh-cn/rules/)。

### Skills

将完整的 `skills/coding-workflows` 目录复制到以下任一位置：

- 项目级：`<project>\.opencode\skills\`
- 全局级：`%USERPROFILE%\.config\opencode\skills\`

安装后的目录应类似：

```text
skills/
└── coding-workflows/
    ├── SKILL.md
    └── agents/
        └── openai.yaml
```

OpenCode 通过 `SKILL.md` 发现技能；`agents/openai.yaml` 用于 Codex 的展示和调用策略，可一并保留。安装后在提示中明确调用 `coding-workflows`，再由模型在同一 Skill 内选择和组合工作方向。详见 [OpenCode Agent Skills 文档](https://opencode.ai/docs/zh-cn/skills/)。

## 致谢

本项目的部分工作流思路参考并重新整理自：

- [obra/superpowers](https://github.com/obra/superpowers)（MIT License，Copyright © 2025 Jesse Vincent）
- [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)（MIT License，Copyright © 2025 Addy Osmani）

## License

[MIT](LICENSE)
