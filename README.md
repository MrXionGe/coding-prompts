# Coding Prompts

个人维护的智能体提示词与编码工作流技能集合。当前主要用于 Codex，同时保持简单、开放的 Markdown 结构，便于在 OpenCode 等支持 Agent Skills 的工具中使用。

## 内容

- [`AGENTS.md`](AGENTS.md)：本机环境与通用工作约定。
- `using-coding-workflows`：按任务选择或组合工作流。
- `spec-driven-development`：以 Spec、Plan 和 Todo 推进开发，按风险补充测试。
- `test-functionality`：围绕功能、接口、UI 和交互开展自动化测试。
- `debug-and-fix`：通过复现和证据定位根因、修复并回归验证。

`skills/coding-workflows` 是集合目录；其四个子目录才是可独立安装和调用的技能。

## 手动安装到 OpenCode

### 提示词

将 [`AGENTS.md`](AGENTS.md) 复制或合并到以下位置：

- 项目级：目标项目根目录下的 `AGENTS.md`
- 全局级：`%USERPROFILE%\.config\opencode\AGENTS.md`

当前提示词描述的是本机环境，更适合作为全局规则。目标位置已有文件时应合并内容，不要直接覆盖。详见 [OpenCode 规则文档](https://opencode.ai/docs/zh-cn/rules/)。

### Skills

将 `skills/coding-workflows` 下的四个子目录复制到以下任一位置：

- 项目级：`<project>\.opencode\skills\`
- 全局级：`%USERPROFILE%\.config\opencode\skills\`

安装后的目录应类似：

```text
skills/
├── using-coding-workflows/
├── spec-driven-development/
├── test-functionality/
└── debug-and-fix/
```

OpenCode 通过各目录中的 `SKILL.md` 发现技能；`agents/openai.yaml` 仅用于 Codex 展示，可保留。安装后可以直接在提示中点名某个技能，或让 `using-coding-workflows` 选择和组合。详见 [OpenCode Agent Skills 文档](https://opencode.ai/docs/zh-cn/skills/)。

## 致谢

本项目的部分工作流思路参考并重新整理自：

- [obra/superpowers](https://github.com/obra/superpowers)（MIT License，Copyright © 2025 Jesse Vincent）
- [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)（MIT License，Copyright © 2025 Addy Osmani）

## License

[MIT](LICENSE)
