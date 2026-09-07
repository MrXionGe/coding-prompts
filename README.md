# Coding Prompts

个人维护的智能体提示词与编码工作流技能集合。当前主要用于 Codex，同时保持简单、开放的 Markdown 结构，便于在 OpenCode 等支持 Agent Skills 的工具中使用。

## 内容

- [`AGENTS.md`](AGENTS.md)：本机环境与通用工作约定。
- [`coding-workflows`](skills/coding-workflows/)：一个可独立安装和调用的约束型编码工作流 Skill，包含四个方向：
  - 技术可行性评估：在开发前判断方案适配性、技术兼容性和关键风险。
  - 开发：以轻量目标和验收标准推进实现，按风险补充测试。
  - 功能测试：围绕功能、接口、UI 和交互开展自动化验证。
  - 调试与修复：通过复现和证据定位根因、聚焦修复并回归验证。

默认使用模型原生编码能力；当任务需要更严格的范围控制、证据要求或交付规范时，显式调用 `coding-workflows`。是否调用取决于任务需要，而非模型代际；GPT-6 等模型也可按需使用。在 Codex 中，该 Skill 已禁止隐式触发，使用 `$coding-workflows` 手动调用。

Skill 根据当前请求和已有上下文判断授权，在授权范围内推进必要阶段；测试按风险收敛，修复失败后根据新证据决定是否继续。用户明确要求只评估、只诊断或不修改时，仍遵守该限制。

## 手动安装到 Codex

### 提示词

将 [`AGENTS.md`](AGENTS.md) 合并到以下任一位置：

- 全局级：`%USERPROFILE%\.codex\AGENTS.md`；设置了 `CODEX_HOME` 时，使用该目录下的 `AGENTS.md`。
- 项目级：目标项目根目录下的 `AGENTS.md`。

本仓库的环境约定更适合安装到本机全局配置。其他使用者应按实际环境调整，已有文件应合并而非覆盖；项目级规则应补充项目自己的构建、测试和业务约束。详见 [Codex AGENTS.md 文档](https://learn.chatgpt.com/docs/agent-configuration/agents-md)。

### Skills

将完整的 `skills/coding-workflows` 目录复制到以下任一位置：

- 项目级：`<project>\.agents\skills\coding-workflows\`。
- 用户级：`%USERPROFILE%\.agents\skills\coding-workflows\`。

目标目录中应直接包含 `SKILL.md` 和 `agents/openai.yaml`，不要再嵌套一层 `coding-workflows`。目标已存在时先比较并合并本地定制。仓库中的 `skills/` 是分发目录，仅克隆仓库不会将其中的 Skill 自动安装到 Codex。

安装后显式调用，例如：

```text
使用 $coding-workflows 修复登录失败的问题，完成相关验证。
```

若未出现新安装的 Skill，可重启 Codex 后重试。详见 [Codex Skills 文档](https://learn.chatgpt.com/docs/build-skills)。

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
