# Indicators

> 公开版指标记录。以下内容仅来自本次事件中的本机观测，不构成攻击者归因。

## Network Indicators

| Indicator | Context |
| --- | --- |
| `47.242.194.202:7092` | 可疑进程曾连接该地址。 |
| `27.124.34.221:8160` | 可疑进程曾连接该地址。 |
| `127.0.0.1:7897` | 可疑进程曾使用本机代理端口。 |

## Defender Detection Names

- `Trojan:WinNT/DeceptiveSight.A!dha`
- `VulnerableDriver:Win64/TrueSight`
- `VirTool:PowerShell/ExcludeProc.A`

## Suspicious Components

| File name | Observed location type | Notes |
| --- | --- | --- |
| `w75w7c.exe` | Program Files (x86) random directory | 曾出现外联行为，并被启动项引用。 |
| `naMW8L.exe` | Program Files (x86) random directory | 被伪装启动项引用。 |
| `skHixa.exe` | Public random directory | 被伪装启动项引用。 |
| `Y7URjOUV.exe` | ProgramData random directory | 曾出现外联行为，并由可疑计划任务关联。 |
| `u7ma1Emn.exe` | ProgramData random directory | 重启后曾短暂复现，随后清理并二次复核未再复活。 |
| `Diagnostics.Client.3441537467.exe` | ProgramData WindowsInstaller-like directory | 可疑落地文件，已隔离。 |
| `ranchserv.jpg` | Windows Temp | 扩展名伪装，曾被服务项引用。 |
| `SiPolicy.p7b` | System32 CodeIntegrity | 异常策略文件，曾影响 Defender 运行。 |

## Persistence Summary

- Suspicious scheduled tasks, including names imitating Edge update tasks.
- HKLM Run entries imitating Tencent / Alibaba security-health names.
- Suspicious service pointing to a file under Windows Temp with a `.jpg` extension.
- Defender exclusions covering broad paths such as system disk, user directory, Program Files and ProgramData.
- An abnormal WDAC / Code Integrity policy affecting Defender execution.
