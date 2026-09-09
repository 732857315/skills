# 电路板设计：工具依赖

本目录记录 `circuit-board-design` 采用的工具源码，2026-09-10 核对。各目录是指向上游的 Git 子模块；许可文件保留在原仓库。

| 子模块 | 角色 | 固定版本 / 提交 |
| --- | --- | --- |
| [KiCAD-MCP-Server](./KiCAD-MCP-Server) | 技能指定的 KiCad MCP 服务 | 2.7.0；`b420ff7edacf64d5b1259a1acff33ead17d506c1` |
| [kicad-python](./kicad-python) | KiCad 官方 IPC Python 绑定，导入名 `kipy` | 标签 `0.8.0`；`473a03cb4c900a9df059c04b26e66106632604bf` |
| [kicad-skip](./kicad-skip) | MCP 使用的原理图文件操作库 | 标签 `v0.2.5`；`2c68c84e987028bbcf6e02c9405eadd90cefdc03` |

MCP 提交来自技能已有验证记录；安装目录没有 Git 元数据，不能据此声称当前全部本机文件与上游逐字相同。两个 Python 标签对应本机已安装的包版本。固定提交用于复现来源，不代表全部操作或其他系统环境都已验证。

## 安装与接入

1. 安装适合目标系统的 [KiCad](https://www.kicad.org/download/)，优先使用安装包提供的符号、封装和 3D 库。技能既有运行记录使用 KiCad 10.0.5，切换版本时核对实际接口能力。
2. 阅读 [MCP 的安装及配置说明](https://github.com/mixelpixx/KiCAD-MCP-Server/tree/b420ff7edacf64d5b1259a1acff33ead17d506c1)。按所用系统配置 Node.js、Python、KiCad 路径和 MCP 客户端；使用其 `package.json`、锁文件与 `requirements.txt` 安装通用运行依赖。下载这些子模块本身不会自动安装或启动服务。
3. 正常使用 `kicad-python` 和 `kicad-skip` 时，优先安装对应发行包到 MCP 实际使用的 Python 环境；本组版本分别为 `kicad-python==0.8.0`、`kicad-skip==0.2.5`。源码目录用于核查实现；需要源码构建时再遵循上游构建说明及内部子模块要求。
4. 实时 PCB 操作须在 KiCad 中打开目标板并启用 API，再按技能的 [实时接入说明](../circuit-board-design/references/kicad-mcp.md) 检查目标文件、后端和读回结果。已有稳定接入环境直接复用，不因更新子模块重复安装。

[kicad-python 项目说明](https://pypi.org/project/kicad-python/)确认其上游位于 GitLab，且 IPC 操作需要运行中的 KiCad。不要把获取源码当作已经接通 GUI。

## 其他依赖与可选来源

MCP 的其余 npm/pip 通用包由其原有依赖清单管理，不逐一改成源码子模块。KiCad 应用和官方元件库优先由正常安装包提供。

[Freerouting](https://github.com/freerouting/freerouting)是 MCP 可选的外部自动布线工具，不是本技能必备组件，本次未重新安装或加入默认下载。博客、教程和参考电路属于按项目查阅的设计资料，不作为运行依赖。

## 更新版本

本仓库记录的子模块提交是默认复现版本。更新上游时先核对版本、兼容性及代表操作，再把新的子模块提交记录到 `skills`；不要把未经核验的上游最新提交当作已通过版本。
