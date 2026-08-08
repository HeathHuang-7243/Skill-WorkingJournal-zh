# Artifacts

技能生成的产出归档在这里，每个技能一个文件夹：`Working/Artifacts/<skill-id>/`。

## 规则
- **位置：** 技能生成的每个产出（示例、模板实例、文档、归档的最终输出）都放在 `Working/Artifacts/<skill-id>/` 下。
- **命名：** `<skill-id>-YYYY-MM-DD.md` 或 `<主题>-YYYY-MM-DD.md`。
- **归档触发：** 如果一段对话的最终输出要"保留"或"作为产出归档"，就保存在这里——不要散落在 `Working/` 根目录或技能正文里。
- **查找：** 当技能需要生成/产出内容时，先从对应文件夹读取（例如写新的 User Story 前先读最近的一条）。

## 当前示例文件夹
- `email-preparation/` —— 归档的邮件产出，可作为未来邮件起草工作的参考
- `devops-userstory-creation/` —— 真实的 User Story 示例（参考模板）