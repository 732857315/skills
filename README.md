# Skills

可复用的 AI 技能集合。每项技能在独立公开仓库维护，本仓库通过 Git 子模块纳入对应目录，固定到已核验的版本。

| 技能目录 | 用途 | 独立仓库 |
| --- | --- | --- |
| [circuit-board-design](./circuit-board-design) | 电路板设计：KiCad 原理图、PCB、符号库、封装库、3D 模型及工程核验 | [skill_circuit-board-design](https://github.com/732857315/skill_circuit-board-design) |

在 GitHub 文件列表点击 `circuit-board-design` 目录，可进入该版本的完整技能文件。

## 下载完整内容

```sh
git clone --recurse-submodules https://github.com/732857315/skills.git
```

如果之前已经克隆本仓库，在仓库内运行：

```sh
git pull
git submodule update --init --recursive
```

下载 GitHub 的 ZIP 不包含子模块文件；需要 ZIP 时，请进入对应的独立仓库下载。

## 使用

按各技能目录中的 `README.md` 和 `SKILL.md` 操作。电路板设计的安装目录名为 `circuit-board-design`，保留其 `agents/` 与 `references/`。
