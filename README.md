# Skills

可复用的 AI 技能集合。

## 电路板设计

技能目录：[circuit-board-design](./circuit-board-design/)。用于在用户或教师指导下，使用 KiCad 完成原理图、PCB、符号库、封装库与 3D 模型的创建、修改和审查。

- 优先使用 KiCad 自带功能和已核实可用的 MCP 接口。
- 按器件和功能组查阅数据手册、参考设计及有依据的工程经验，核对后放置与连接。
- 通过实际布线发现并修正布局问题，按可检查的电路进度推进。
- 一个主工程只有一个写入者；其他 AI 可独立审查资料与结果。
- 交付时检查 ERC、DRC、封装、3D 和制造输出，明确未验证的项目。

### 安装与使用

在支持本地技能的 Codex 环境中，将完整的 `circuit-board-design` 文件夹复制到 `$CODEX_HOME/skills/`（默认 `~/.codex/skills/`），重新加载技能后使用“电路板设计”。也可让支持 GitHub 技能安装的 AI 从本仓库的该目录安装。

在其他 AI 环境中，将 [SKILL.md](./circuit-board-design/SKILL.md) 作为入口，并保留 `references/` 供按需读取。环境需要自行配置 KiCad 和相应工具接口；上传到 GitHub 不等于自动安装到所有 ChatGPT 会话。

这是可移植技能包，包含工作方法与参考索引，不包含本机路径配置、具体电路板工程、厂商手册或第三方封装及 3D 文件。
