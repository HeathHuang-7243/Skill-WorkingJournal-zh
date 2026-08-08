# Copilot 工作区指令

本仓库是一个个人技能目录。请把它当作一个可路由的技能系统。

## 路由的权威来源

- 始终先阅读 `index.md`。
- 读完 `index.md` 后，在执行任何操作前，始终阅读本文件（`.github/copilot-instructions.md`）。
- 使用 `index.md` 中的 `triggers` 和触发词映射来选择正确的技能文件。
- 当没有触发词匹配时，不要猜测技能；询问用户想要哪个技能。

## 技能位置

- Working 技能位于 `Working/` 下（包括 `Architecture/`、`Developing/`、`Security/`、`Policy/`、`Troubleshooting/` 等子文件夹）。
- Living 技能位于 `Living/` 下（按主题子文件夹分组，例如 `Living/Network/`）。

## 执行模型

- 保持 YAML frontmatter（`id`、`title`、`domain`、`proficiency`、`tools`、`triggers`、`summary`、`related`）与 `index.md` 一致。
- 把每个技能文件的正文当作操作指南；不要用泛泛的建议替代它。
- 新增/更新技能时，同时更新 `index.md` 的技能表和触发词映射。
- 不确定是否该新增技能时，先运行 `Working/skill-creation-rubric.md` 再决定。

## Artifacts

- 技能生成的产出，文件存放在：
  - `Working/Artifacts/<skill-id>/`
- 命名约定：
  - `<skill-id>-YYYY-MM-DD.md`
  - 或 `<主题>-YYYY-MM-DD.md`

## 本仓库的记忆

- 项目记忆存放在 `Memory/` 下（仓库本地；不要写入全局记忆位置）。
- 每日文件使用 `YYYY-MM-DD.md`。
- 本仓库的任何变更都必须追加到当天的记忆文件。

## 每日开工读取

- 每个工作日开始时，在做任何实质性任务之前，读取两个仓库的每日上下文：
  - `Working-Journal/daily/`（最新一天 + `index.md` 中定义的快速回看窗口）
  - `Skills/Memory/`（最新的每日记忆记录）
- 把这当作强制性的开工上下文加载，而不是可选项。