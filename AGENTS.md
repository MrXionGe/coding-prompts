本机为 Windows 11；沿用 agent 当前 Shell，按实际执行环境编写命令。不确定时再检查 Shell / 版本，区分 PowerShell、Git Bash 与 WSL，不混用语法、路径或工具链。

- 搜索优先用 `rg`、`rg --files`。路径正确引用；跨 Shell 调用时注意参数展开与路径转换。
- PowerShell 优先用原生 cmdlet；同名 Unix 命令可能是 Alias。5.1 不支持 `&&`、`||`。外部程序退出码用 `$LASTEXITCODE`，cmdlet 错误用 `-ErrorAction Stop` 等机制处理；Bash 按自身语法处理。依赖前步成功的操作须检查状态，不能仅用换行串联。
- 保留文件编码、BOM 和换行。PowerShell 读取 UTF-8 时指定 `-Encoding UTF8`；注意 5.1 用该参数写入会添加 BOM。
- 删除、递归移动或批量覆盖前核验绝对路径与范围，在同一 Shell 内完成；PowerShell 文件操作优先用 `-LiteralPath`。
- 工具找不到时先查解析与 PATH：PowerShell 用 `Get-Command <name> -All`，Bash 用 `type -a <name>`。按需检查本机 `D:\runtime\cli`、`mise ls`、`coreutils.exe --list`，不要直接认定未安装；WSL 工具环境另行确认。
