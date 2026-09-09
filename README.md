# Skills

可复用的 AI 技能集合。技能与工具依赖通过 Git 子模块纳入对应目录，固定到明确版本。

| 技能目录 | 用途 | 独立仓库 |
| --- | --- | --- |
| [circuit-board-design](./circuit-board-design) | 电路板设计：KiCad 原理图、PCB、符号库、封装库、3D 模型及工程核验 | [skill_circuit-board-design](https://github.com/732857315/skill_circuit-board-design) |

## circuit-board-design dependencies

| 子模块 | 用途 |
| --- | --- |
| [circuit-board-design-dependencies/KiCAD-MCP-Server](./circuit-board-design-dependencies/KiCAD-MCP-Server) | KiCad MCP 服务 |
| [circuit-board-design-dependencies/kicad-python](./circuit-board-design-dependencies/kicad-python) | 官方 IPC Python 库，实时读写已打开的 PCB |
| [circuit-board-design-dependencies/kicad-skip](./circuit-board-design-dependencies/kicad-skip) | 原理图文件操作库 |

版本、安装说明与可选工具见 [依赖说明](./circuit-board-design-dependencies/README.md)。在 GitHub 文件列表中点击子模块目录即可打开对应源码版本。

## 下载技能与直接依赖

```sh
git clone https://github.com/732857315/skills.git
cd skills
git submodule update --init --depth 1
```

已有克隆则先运行 `git pull`，再运行上述 `git submodule update`。这些命令获取本仓库列出的技能与三个直接依赖，不自动展开上游自己的构建子模块。

需要从源码构建上游库时，按对应仓库说明补齐其内部子模块。`--recursive` 会继续获取上游嵌套源码；例如 kicad-python 的构建源码还引用 KiCad。GitHub ZIP 不包含子模块文件，需要 ZIP 时请进入对应独立仓库下载。

## 使用

按技能目录中的 `README.md` 和 `SKILL.md` 操作。电路板设计安装目录名为 `circuit-board-design`，保留其 `agents/` 与 `references/`。`circuit-board-design-dependencies/` 中是工具源码，安装及 MCP 配置按 [依赖说明](./circuit-board-design-dependencies/README.md) 完成。
