本机操作系统为 Windows 11，默认 shell 为 Windows PowerShell 5.1。优先使用 PowerShell 原生命令和语法；代码及文件搜索优先使用 `rg`。

当 PowerShell 不够方便时，可使用本机 PATH 中配置的 CLI。通过以下命令按需查询，不要直接判断工具未安装：

- `Get-Command <name> -All`：查找命令
- `Get-ChildItem D:\runtime\cli`：查看独立 CLI
- `mise ls`：查看 Go、Java、Node.js、Python 等工具链
- `coreutils.exe --list`：查看 uutils Coreutils 命令

已配置的主要工具包括 `git`、`gh`、`rg`、`ffmpeg`、`adb`、`lark-cli`、`officecli`、`upx`、`mise` 和 Coreutils。

PowerShell 的 `ls`、`cat`、`cp`、`mv`、`rm` 等名称是 Alias。需要使用 Coreutils 时应显式调用 `ls.exe`、`cp.exe`，或使用 `coreutils.exe ls`。

涉及删除、递归移动和批量覆盖时，优先使用 PowerShell 和 `-LiteralPath`，并先核验绝对目标路径。
