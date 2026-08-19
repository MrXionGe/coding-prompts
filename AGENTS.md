本机为 Windows 11，默认 shell 是 Windows PowerShell 5.1（非 PowerShell 7）。优先使用 PowerShell 原生命令；代码和文件搜索优先使用 `rg`。不要使用 `&&`、`||` 等仅 PowerShell 7 支持的语法；多步命令使用换行，并按需检查 `$LASTEXITCODE`。

本机已配置 `git`、`gh`、`rg`、`ffmpeg`、`adb`、`lark-cli`、`officecli`、`upx`、Coreutils，以及由 `mise` 管理的 Go、Java、Node.js、Python 等工具链。不要直接判断工具未安装，按需查询：

- `Get-Command <name> -All`
- `Get-ChildItem -LiteralPath D:\runtime\cli`
- `mise ls`
- `coreutils.exe --list`

`ls`、`cat`、`cp`、`mv`、`rm` 等名称是 PowerShell Alias，不要当作 GNU Coreutils 使用。需要 Coreutils 时显式调用 `ls.exe`、`cp.exe` 或 `coreutils.exe <command>`。

PowerShell 5.1 读取 UTF-8 无 BOM 文本时可能使用系统代码页；读取时显式指定 `-Encoding UTF8`，写入时避免无意改变编码或 BOM。

删除、递归移动或批量覆盖前，先解析并核验绝对目标路径；使用 PowerShell cmdlet 和 `-LiteralPath`。
