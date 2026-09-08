以下约定适用于本机 Windows 11 / PowerShell 5.1；其他环境以实际操作系统、Shell 和工具配置为准。

- 优先使用 PowerShell 原生命令，代码和文件搜索优先使用 `rg`。不用 `&&`、`||`；多步命令使用换行，后续操作依赖外部命令成功时检查 `$LASTEXITCODE`。
- `ls`、`cat`、`cp`、`mv`、`rm` 等是 PowerShell Alias。需要 GNU Coreutils 时显式调用对应的 `.exe` 或 `coreutils.exe <command>`。
- 读取 UTF-8 文本时显式指定 `-Encoding UTF8`；写入时保留原有编码和 BOM 约定。
- 删除、递归移动或批量覆盖前，解析并核验绝对目标路径；使用 PowerShell cmdlet 和 `-LiteralPath`。

工具不可用时，先按需检查命令解析和本机配置，再判断是否缺失：

- 命令位置：`Get-Command <name> -All`
- 本机补充目录：`Get-ChildItem -LiteralPath D:\runtime\cli`
- 工具链版本：`mise ls`
- Coreutils 子命令：`coreutils.exe --list`
