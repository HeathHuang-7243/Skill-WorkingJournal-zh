# 技能索引

> **给模型的说明：** 这是根路由目录。请*最先*打开此文件。在执行任务前，再阅读
> `.github/copilot-instructions.md`。要挑选正确的技能，请在 `triggers` 列（或下方的触发词映射）
> 中查找用户的措辞，然后打开 `Working/` 或 `Living/` 下的对应文件。不要猜测——如果没有触发词
> 匹配，请询问用户指的是哪个技能。
>
> **给人类的说明：** 这是你在所有技能域中的导航地图。每一行对应一个技能文件的 YAML frontmatter；
> 你编辑技能时请保持它们同步。
>
> **模板说明：** 下面每一行都来自一个已脱敏的实际配置的示例。请在你创建自己的技能时替换这些行
> （参见 `_TEMPLATE.md` 和 skill-creation-rubric）。保留结构；只改内容。

## 图例
- **proficiency:** Working → beginner · intermediate · advanced · expert ｜  Living → novice · comfortable · fluent ｜ reference = 非技能参考文档（例如 team-routing、决策 rubric）；无熟练度评级
- **triggers:** 指示该技能适用的短语
- **技能创建 rubric:** 在决定是新建技能还是扩展现有技能时，参见 [Working/skill-creation-rubric.md](./Working/skill-creation-rubric.md)

## 领域
- **Working** — 职业 / 工作技能（云架构、IaC、合规、排障等）
- **Living** — 生活技能，按主题子文件夹分组（例如 `Living/Network/`）
- **Working 子文件夹** — `Working/Architecture/`（解决方案架构 / 设计 / 评审）、`Working/Developing/`（代码 / IaC / 动手工作）、`Working/Security/`（云安全 / 合规 / 身份 / 威胁建模）、`Working/Policy/`（平台治理 / 备份保留 / 合规基线）、`Working/Troubleshooting/`（部署阻塞、锁冲突、权限与治理 runbook）。安全类、策略类、架构类与开发类技能存放在这些子文件夹中；路由时请先检查它们。

## 技能

| id                                      | title                                                       | domain  | proficiency  | years | triggers（概要）                                                                                                                                                                                                                                  | file                                                                                                                                                                                                                                  |
| --------------------------------------- | ----------------------------------------------------------- | ------- | ------------ | ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| solution-architecture-design            | 解决方案架构设计                                            | Working | advanced     | 8     | "设计端到端云解决方案"、"在服务/模式之间做选择"、"评审一个云架构"                                                                                                                                                                                   | [Working/Architecture/solution-architecture-design.md](./Working/Architecture/solution-architecture-design.md)                                                                                                                        |
| infrastructure-as-code                  | 基础设施即代码（Terraform / Bicep）                            | Working | advanced     | 6     | "用代码配置基础设施"、"编写/评审 Terraform/Bicep"、"模块化 IaC"                                                                                                                                                                                     | [Working/Developing/infrastructure-as-code.md](./Working/Developing/infrastructure-as-code.md)                                                                                                                                        |
| devops-userstory-creation               | DevOps 用户故事编写（IaC 前置条件）                             | Working | expert       | —     | "代码变更前要提出什么"、"如何创建用户故事"、"IaC 前置流程"、"需要评审"、"用户故事 vs 变更请求"                                                                                                                                                          | [Working/Developing/devops-userstory-creation.md](./Working/Developing/devops-userstory-creation.md)                                                                                                                                  |
| development-discipline                  | 开发纪律（对齐 · TDD · 调试）                                   | Working | advanced     | —     | "写代码前先确认需求 / 不要急着写代码"、"如何验证这个变更"、"先写测试再实现"、"一步步隔离 bug / 有纪律的调试"、"给这个变更做质量门禁"                                                                                                                 | [Working/Developing/development-discipline.md](./Working/Developing/development-discipline.md)                                                                                                                                        |
| cloud-security-compliance               | 云安全与合规                                              | Working | intermediate | 4     | "保护一个云工作负载"、"满足 ISO/SOC/FedRAMP"、"评审安全态势"、"分类并分派漏洞"、"提议安全豁免"                                                                                                                                                        | [Working/Security/cloud-security-compliance.md](./Working/Security/cloud-security-compliance.md)                                                                                                                                      |
| platform-module-compliance              | 平台模块合规                                              | Working | advanced     | 4     | "模块不合规"、"策略评审工作坊"、"决策记录 ADR"、"跨模块共享控制族"、"模块合规基线"                                                                                                                                                                    | [Working/Policy/platform-module-compliance.md](./Working/Policy/platform-module-compliance.md)                                                                                                                                        |
| deployment-lock-troubleshooting         | 平台部署锁排障                                                 | Working | advanced     | —     | "部署被锁阻塞"、"无法移除锁"、"ScopeLocked"、"检查锁是否来自编排运行"、"从邮件/线程解除部署阻塞"                                                                                                                                                          | [Working/Troubleshooting/Platform/deployment-lock-troubleshooting.md](./Working/Troubleshooting/Platform/deployment-lock-troubleshooting.md)                                                                                           |
| missing-resource-troubleshooting        | 平台资源缺失排障                                                 | Working | advanced     | —     | "关联资源未找到"、"部署报告资源缺失"、"工作流未创建资源"、"检查工作流组 / 栈运行历史"、"资源名后缀是随机数——按资源组定位"                                                                                                                                      | [Working/Troubleshooting/Platform/missing-resource-troubleshooting.md](./Working/Troubleshooting/Platform/missing-resource-troubleshooting.md)                                                                                          |
| resource-lock-troubleshooting           | 云资源锁排障                                           | Working | advanced     | —     | "资源部署被锁阻塞"、"ScopeLocked"、"这个锁是谁创建"、"请求者没有移除锁的权限"、"重跑仍然因锁失败"                                                                                                                                                        | [Working/Troubleshooting/Cloud/resource-lock-troubleshooting.md](./Working/Troubleshooting/Cloud/resource-lock-troubleshooting.md)                                                                                                    |
| email-preparation                       | 邮件起草                                                   | Working | expert       | —     | "起草一封邮件回复"、"改写这封邮件并列出要点"、"把这串讨论变成清晰的回复"、"起草一封利落的 incident 邮件"                                                                                                                                                  | [Working/email-preparation.md](./Working/email-preparation.md)                                                                                                                                                                        |
| skill-creation-rubric                   | 技能创建决策 Rubric                                              | Working | reference    | —     | "这应该是新技能还是扩展现有技能"、"技能创建的评分 rubric"、"触发词缺口 / 工作流缺口 / 产出缺口"                                                                                                                                                        | [Working/skill-creation-rubric.md](./Working/skill-creation-rubric.md)                                                                                                                                                                |
| work-triage                             | 工作分流（每日分类与路由）                                        | Working | expert       | —     | "谁该处理这个请求 / 是否在我们的范围"、"如何判断票的归属"、"转交还是协作"、"代码变更 / 部署流程"、"自行处理还是升级"、"如何给这个问题分类"                                                                                                               | [Working/work-triage.md](./Working/work-triage.md)                                                                                                                                                                                    |
| team-routing                            | 团队路由（职责与联系人）                                          | Working | reference    | —     | "这个归谁"、"哪个 Tower 处理这个主题"、"主题 X 该联系谁"                                                                                                                                                                                              | [Working/team-routing.md](./Working/team-routing.md)                                                                                                                                                                                  |
| home-network-troubleshooting            | 家庭网络排障                                              | Living  | comfortable  | —     | "网络连不上"、"Wi-Fi 掉线"、"部分网站无法访问 / DNS 问题"、"路由器配置"、"局域网共享不工作"                                                                                                                                                            | [Living/Network/home-network-troubleshooting.md](./Living/Network/home-network-troubleshooting.md)                                                                                                                                    |

## 触发词映射（路由）
- "设计 / 评审 / 验证一个云架构" → `Working/Architecture/solution-architecture-design.md`
- "Terraform / Bicep / OpenTofu / 用代码配置基础设施" → `Working/Developing/infrastructure-as-code.md`
- "写代码前先确认需求 / 如何验证这个变更 / 先写测试 / 一步步调试 / 给变更做质量门禁" → `Working/Developing/development-discipline.md`
- "DevOps 用户故事 / 代码变更前置 / IaC 流程门禁 / 用户故事 vs 变更请求 / ADO 模板字段 / 作为…我希望…以便…" → `Working/Developing/devops-userstory-creation.md`（生成的示例保存在 `Working/Artifacts/devops-userstory-creation/` 下）
- "安全基线 / 合规 / ISO 27001 / SOC 2 / FedRAMP" → `Working/Security/cloud-security-compliance.md`（位于 `Working/Security/` 子文件夹）
- "模块不合规 / 策略评审工作坊 / 跨模块 ADR / 共享控制族 / 模块合规基线" → `Working/Policy/platform-module-compliance.md`（位于 `Working/Policy/` 子文件夹）
- "部署被锁阻塞 / 无法移除锁 / ScopeLocked / 检查锁是否由编排工作流设置 / 从邮件/线程解除阻塞" → `Working/Troubleshooting/Platform/deployment-lock-troubleshooting.md`
- "关联资源未找到 / 部署报告资源缺失 / 工作流未创建资源 / 检查工作流组或栈运行历史 / 资源名后缀是随机数——按资源组定位" → `Working/Troubleshooting/Platform/missing-resource-troubleshooting.md`
- "资源部署被锁阻塞 / ScopeLocked / 这个锁是谁创建 / 请求者没有移除锁的权限 / 重跑仍因锁失败" → `Working/Troubleshooting/Cloud/resource-lock-troubleshooting.md`
- "起草一封邮件回复 / 改写这封邮件并列出要点 / 把这串讨论变成清晰回复 / 起草利落的 incident 邮件" → `Working/email-preparation.md`
- "这应该是新技能还是扩展现有技能 / 评分 rubric / 触发词缺口·工作流缺口·产出缺口" → `Working/skill-creation-rubric.md`（添加新技能前先运行它）
- "请求归属 / 范围判定 / 转交还是协作 / 代码变更与部署流程 / 自行处理还是升级 / 如何给问题分类" → `Working/work-triage.md`
- "这个归谁 / 哪个 Tower 负责这个主题 / 联系路由" → `Working/team-routing.md`
- "网络连不上 / Wi-Fi 掉线 / DNS 问题 / 局域网共享不工作" → `Living/Network/home-network-troubleshooting.md`

## Artifacts（产出归档约定）
- **规则：** 每个技能生成的产出（示例、模板实例、文档、归档的最终输出）都放在 **`Working/Artifacts/<skill-id>/`** 下，命名为 `<skill-id>-YYYY-MM-DD.md` 或 `<主题>-YYYY-MM-DD.md`。
- **归档规则：** 如果一段对话的最终输出需要"保留"或"作为产出归档"，就保存到对应目录。
- **查找：** 当技能需要生成/产出内容时，从对应目录读取；不要把产出散落到 `Working/` 根目录或技能文件正文里。
- 示例：`Working/Artifacts/email-preparation/` —— 归档的邮件产出，可作为未来邮件起草工作的参考。

## Working-Journal 日志规则
- 任何为 Working-Journal 工作区执行的操作，必须在当天记入 `Working-Journal/daily/<YYYY-MM-DD>.md`。
- 日志最少内容：请求了什么、产出/变更了什么、关键下一步或待定决策。
- 如果为 Working-Journal 工作创建了产出文件，请在日志中记录其相对路径。
- 每天第一次对话时，快速回看 `Working-Journal/daily/` 中最近 7 天的日志，找出未完结主题（待办动作、阻塞项、未决决策）。如有未完结主题，主动通知用户。
- 每个工作日开始时，还要连同 `Working-Journal/daily/` 一起读取最新的 `Skills/Memory/` 日志，这样上下文同时来自工作执行与技能仓库记忆。
- 当用户说出"记下来"、"做个笔记"、"写进日志"之类的短语时，追加到当前日期的 `Working-Journal/daily/<YYYY-MM-DD>.md`。

## 关系
```
solution-architecture-design
        │  (提供输入)
        ├──<── infrastructure-as-code
        │  (实现)
        └──<── cloud-security-compliance
                  (基线应用到 IaC 与设计)

devops-userstory-creation
        │  (前置条件；门禁)
        └──> infrastructure-as-code

work-triage
        │  (查询负责人)
        └──> team-routing

deployment-lock-troubleshooting
        │  (先查来源)
        ├──> team-routing
        └──> devops-userstory-creation

missing-resource-troubleshooting
        │  (先追踪所有者工作流；按资源组+标签定位，后缀是随机数)
        ├──> deployment-lock-troubleshooting
        ├──> team-routing
        └──> infrastructure-as-code

resource-lock-troubleshooting
        │  (通用云锁分流)
        ├──> team-routing
        └──> deployment-lock-troubleshooting

email-preparation
        │  (把线程变成对外回复)
        ├──> work-triage
        └──> team-routing

development-discipline
        │  (对齐/TDD/调试纪律，贯穿开发与排障)
        ├──> devops-userstory-creation
        ├──> infrastructure-as-code
        └──> deployment-lock-troubleshooting

platform-module-compliance
        │  (工作坊循环 + 共享控制族)
        ├──> devops-userstory-creation
        ├──> infrastructure-as-code
        └──> cloud-security-compliance

# Living / 主题子文件夹（例如 Living/Network/）
home-network-troubleshooting  (独立；通用的家庭网络 / Wi-Fi / 设备修复)
```

## 如何添加一个技能
1. 先运行 [Working/skill-creation-rubric.md](./Working/skill-creation-rubric.md) 中的新建技能决策检查。
2. 从目标领域复制模板：`Working/_TEMPLATE.md` 或 `Living/_TEMPLATE.md`。
3. 填写 YAML frontmatter（`id` 必须与文件名一致，`triggers` 驱动路由）。
4. 用任何适合该技能的正文结构来写正文。
5. 保存到正确的领域文件夹（例如 `Working/`、`Living/`，或类似 `Working/Architecture/`、`Working/Developing/`、`Working/Security/`、`Working/Policy/`、`Working/Troubleshooting/` 的子文件夹）。
6. 在上面的 **Skills** 表加一行，并在**触发词映射**中加一条。
7. 如果技能会生成产出（模板、代码示例、实例、归档的最终输出），按 **Artifacts** 约定放到 `Working/Artifacts/<skill-id>/` 下。
8. **强制记忆同步：** 本仓库的任何变更（新建 / 修改 / 移动 / 删除 / 重构 / 规则更新）都必须当天追加一条记录到 `Memory/YYYY-MM-DD.md`（没有就创建）。参见 `README.md` → 记忆约定。