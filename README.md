# Scoop CTF Bucket

面向 Windows 的 Scoop 第三方桶，收录常用的 CTF、安全与渗透测试工具，便于快速安装、更新和管理。

## 快速开始
- 前提：已安装 `Scoop`
- 添加桶并安装示例工具：

```pwsh
scoop bucket add ctf https://github.com/gandli/scoop-ctf
scoop install ctf/fscan
```

## 常用操作
- 查看工具信息：`scoop info ctf/fscan`
- 更新此桶：`scoop update ctf`
- 更新所有工具：`scoop update`
- 卸载工具：`scoop uninstall ctf/fscan`

## 目录结构
- `bucket/`：工具清单 JSON 文件
- `bin/`：维护与校验脚本（如 `checkver.ps1`, `checkhashes.ps1`）
- `deprecated/`：已弃用内容占位
- `scripts/`：其他脚本占位

## 分类说明
- `bucket\recon`：信息收集与资产发现（如 `subfinder`, `dnsx`, `httpx`, `katana`）
- `bucket\web-fuzz`：目录与内容模糊测试（如 `ffuf`, `feroxbuster`, `dirsearch`）
- `bucket\exploitation`：漏洞利用与 Payload 工具（如 `sqlmap`, `tplmap`, `phpggc`, `ysoserial`）
- `bucket\binary`：二进制分析/调试（原 `reversing`，如 `cutter`, `jadx`, `x64dbg`, `ImHex`, `gda`, 以及 `jar-analyzer`, `jar-obfuscator`, `proguard`, `qrazybox`）
- `bucket\forensics`：取证与内存分析（如 `autopsy`, `FTK-Imager`, `MemProcFS`, `volatility`）
- `bucket\c2-redteam`：C2 与内网渗透辅助（如 `sliver`, `cobaltstrike`, `ligolo-ng`, `stowaway`）
- `bucket\credentials`：凭据相关工具（如 `mimikatz`）
- `bucket\crypto`：密码学相关（如 `hashcat`, `RsaCtfTool`, `bkcrack`, `fastcoll`, `jwt_tool`, `ZipCracker`）
- `bucket\misc`：杂项/通用工具（如 `StegSolve`, `ImageStrike`, `CTFCrackTools`, `EquationToolsGUI`, `CyberChef`, `TweakPNG`）

提示：如果脚本或 CI 依赖清单的具体路径，分类后路径有所变化，请相应更新引用路径；Scoop 安装通常按应用名解析清单，但自定义脚本可能需要显式路径。

## 参与贡献
- 欢迎通过 Issue 或 PR 新增/修复清单。
- 新增清单时参考现有 JSON 格式，尽量提供 `version`, `url`, `hash`, `bin` 等字段，并配置 `checkver`/`autoupdate` 便于维护。
- 提交前可使用 `bin/checkver.ps1` 与 `bin/checkhashes.ps1` 进行校验。

## 许可与声明
- 许可证见 `LICENSE`。
- 本仓库所含工具仅供学习与测试，请在合法合规范围内使用。
