本机为 Windows 11。沿用当前 Shell，不确定时先确认类型和版本。跨 PowerShell、Git Bash 或 WSL 调用时，按两侧规则处理参数引用、变量展开和路径转换。

- 搜索文本优先用 `rg`，查找文件用 `rg --files`。
- PowerShell 优先用原生 cmdlet。后续操作依赖前一步成功时，外部程序按其退出码语义检查 `$LASTEXITCODE`，cmdlet 用 `-ErrorAction Stop` 等机制处理错误。PowerShell 5.1 不支持 `&&`、`||`。
- 编辑时保留原编码、BOM 状态和换行。PowerShell 读取 UTF-8 文件时指定 `-Encoding UTF8`。在 5.1 中，用该参数写回会添加 BOM。
- 删除、递归移动或批量覆盖前，核验目标绝对路径和操作范围，并在同一 Shell 内完成。PowerShell 文件操作优先用 `-LiteralPath`。
- 找不到工具时先查命令解析和 PATH。PowerShell 用 `Get-Command <name> -All`，Bash 用 `type -a <name>`。按需检查 `D:\runtime\cli`、`mise ls`、`coreutils.exe --list`。WSL 内单独确认。
