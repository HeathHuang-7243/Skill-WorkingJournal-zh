# Skill-WorkingJournal 系统模板（中文版）

一套开箱即用的**双仓库操作系统**，用于与 AI 助手一起开展日常工程工作。本模板是从一套实际生产环境中提炼并脱敏的通用模板——不含任何公司名、人名、客户名、资源名或凭据。

> **开始使用前，请输入：**"请阅读说明文件，然后我们开始搭建吧"

> 🌐 **English version:** [Skill-WorkingJournal](https://github.com/HeathHuang-7243/Skill-WorkingJournal.git)

## 这套系统是什么

| 仓库 | 回答的问题 | 内容 |
|---|---|---|
| **`Skills/`**（仓库 1） | 这件事应该怎么做 | 技能文件（可复用流程 / 判断引擎 / 运维手册）<br>· `index.md`：触发词 → 技能路由目录<br>· `Memory/`：每日日志，强制同步 |
| **`Working-Journal/`**（仓库 2） | 发生了什么工作 | · `active/`：进行中的事件，按主题组织<br>· `Archive/`：已关闭的工作，按项目归档<br>· `daily/`：逐日工作日志 |

- **Skills/** 回答*"这件事应该怎么做？"*——它是一个可路由的目录。每个技能文件都有标准化的 YAML frontmatter（**唯一的共享契约**）；正文完全自由，让每个技能保留最适合它的版式。`index.md` 将用户的措辞映射到正确的技能文件，AI 模型（或人类）可以据此自我路由。
- **Working-Journal/** 回答*"发生了什么？"*——它是长期记忆：进行中的事件文件夹、按项目归档的档案、逐日工作日志。

两个仓库通过约定关联：`Skills/` 内的任何变更必须在当天记入 `Skills/Memory/YYYY-MM-DD.md`，并且每个工作日都从读取两个仓库的最新日志开始。

## 目录结构

```
Skill-WorkingJournal-zh/
├── README.md                     ← 你在这里
├── MIGRATION-GUIDE.md            ← 如何采纳这套模板（从这里开始）
├── Skills/
│   ├── README.md                 ← 仓库约定 + 记忆规则
│   ├── index.md                  ← 路由目录（核心契约）
│   ├── .github/copilot-instructions.md  ← 给 AI 模型的规则
│   ├── Memory/                   ← 每日日志（YYYY-MM-DD.md）
│   ├── Working/                  ← 职业技能
│   │   ├── _TEMPLATE.md          ← 新技能模板
│   │   ├── skill-creation-rubric.md   ← 新建 vs 扩展的决策
│   │   ├── work-triage.md        ← 示例：判断引擎
│   │   ├── team-routing.md       ← 示例：静态路由表
│   │   ├── email-preparation.md  ← 示例：产出工作流
│   │   ├── Architecture/         ← 示例：设计技能
│   │   ├── Developing/           ← 示例：代码/IaC 技能
│   │   ├── Security/             ← 示例：合规技能
│   │   ├── Policy/               ← 示例：治理技能
│   │   ├── Troubleshooting/      ← 示例：运维手册技能
│   │   └── Artifacts/            ← 产出物归档
│   └── Living/                   ← 生活技能
│       ├── _TEMPLATE.md
│       └── Network/              ← 示例：家庭网络
└── Working-Journal/
    ├── README.md
    ├── daily/                    ← 逐日工作日志
    ├── active/                   ← 进行中的工作文件夹
    └── Archive/                  ← 已关闭的工作，按项目归档
```

## 为什么这样设计

| 设计决策 | 原因 |
|---|---|
| frontmatter 是唯一契约，正文自由 | 一套共享的元数据模式支撑路由；每个技能保留适合自己的版式（叙述、清单、运维手册、表格……），不强行套模板。 |
| 触发词驱动路由 | AI 模型通过匹配用户措辞到 `triggers` 来路由；人类浏览同一张目录表。一个目录，两种受众。 |
| 两套熟练度标尺 | 职业技能用 `beginner→expert`；生活技能用 `novice→fluent`。“年限”只对职业技能有意义。 |
| 创建技能前先打分 | 防止触发词重叠与技能泛滥——只有当触发词、工作流、产出三者都独立时才新建技能。 |
| 判断引擎与静态查询分离 | `work-triage` 记录*你如何决策*（分类 → 定归属 → 协作 → 自行处理）；`team-routing` 只是它查询的表。流程才是可复用的资产，表格只是附录。 |
| 证据优先排障 | 每个运维手册都要求先证明问题根源再动手——部署锁、资源缺失、无法销毁。绝不瞎猜，绝不盲目"修复"。 |
| 强制记忆同步 | `Skills/` 的任何变更都追加到当日记忆日志，让未来每个会话都加载到完整上下文。 |
| 每个技能独立的产出目录 | 生成的产出（邮件、用户故事、交接文档）归档在 `Working/Artifacts/<skill-id>/` 下，不散落在技能正文里。 |

## 如何使用这套模板

1. 阅读 **[MIGRATION-GUIDE.md](./MIGRATION-GUIDE.md)**——它会带你完成结构采纳与第一个技能的编写。
2. 将 `Skills/` 文件夹复制到一个**私有** git 仓库（填入内容后会包含个人数据）。
3. 将 `Working-Journal/` 复制到第二个私有仓库。
4. 从第一个技能开始：选一个你反复执行的任务，复制 `_TEMPLATE.md`，填好 frontmatter，在 `index.md` 中加一行。
5. 让 AI 模型在每个工作日开始时读取 `index.md` → `.github/copilot-instructions.md` → 你的最新日志。

## 脱敏声明

本模板提取自一套实际运行的个人配置。已移除：公司名与客户名、同事姓名、资源与环境标识符、订阅/凭据引用、个人账户与私有 IP。技术名称（Azure、Terraform、StackGuardian 等）作为示例保留——请在你自己的技术栈不同之处替换它们。