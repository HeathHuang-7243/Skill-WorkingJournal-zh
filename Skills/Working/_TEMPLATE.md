---
# 这是规范的技能模板。
# 使用前：阅读 Working/skill-creation-rubric.md，决定是创建新技能还是扩展现有技能。

id: <技能-id-kebab-case>            # 必须与文件名完全一致（例如 proxy-subscription.md -> id: proxy-subscription）
title: <人类可读的技能标题>    # 中英文皆可；选你一眼就能看懂的那个
domain: Working                       # Working | Living | reference
proficiency: <见下方枚举>         # 取决于 domain —— 见 §Proficiency 枚举
years: null                            # 数字型 Working 技能填数字；Living/reference 填 null
tools: [<工具1>, <工具2>, ...]         # 具体使用的工具/服务；没有用 [] 
triggers:                              # 3–9 条模型（或你）在这个技能适用时会说的话
  - "<短短语>"
  - "<另一个短语>"
summary: <一句话：这个技能覆盖什么、产出什么。>
related: [<其他技能-id>, ...]       # 双向链接；见 §Related
# 可选 —— 当技能是会被修订的"活文档"时添加：
# last_reviewed: YYYY-MM-DD
# maturity: evolving | stable
---

# <技能标题>

> 正文按设计**完全自由**。唯一标准化的部分是上面的 YAML frontmatter——它让 `index.md` 可以把触发词路由到这个文件。选任何适合该技能的版式——叙述、清单、表格、决策树、代码块、实战故事。

---

## § Domain、proficiency、years —— 速查

| 字段 | 取值 | 说明 |
|-------|-------|--------|
| `domain` | `Working` · `Living` · `reference` | `reference` = 无技能熟练度的路由/参考文档（例如 team-routing、skill-creation-rubric）。谨慎使用。 |
| `proficiency`（Working） | `beginner` · `intermediate` · `advanced` · `expert` | 对照触发场景做自我评估。 |
| `proficiency`（Living） | `novice` · `comfortable` · `fluent` | 同一个思路，用个人尺度的措辞。 |
| `proficiency`（`reference`） | `reference` | 唯一的字面值；不在 Working 或 Living 的刻度上。 |
| `years` | 整数（数字型 Working 技能）· `null` | 仅用于"年限能有效衡量技能"的 Working 技能（例如"8 年云架构"）。Living 技能填 `null`。 |

---

## § Triggers —— 路由契约

- **3–9 条短语。** 少于 = 太模糊；多于 = 重复。
- 每条短语都是用户（或模型）在这个技能适用时会输入/说出的话。
- 触发词驱动 `index.md` 的**触发词映射**。Skills 表的 `triggers` 列是压缩摘要；frontmatter 的列表才是唯一权威来源。

---

## § Related —— 双向链接

- 列 `id`（不是路径）。如果你链接 `[work-triage]`，该链接必须能解析到一个 `id: work-triage` 存在的文件。
- **按约定双向：** 当你加 A → B，也要加 B → A（或注明 A 的反向在 B 的 related 中）。
- 只有没有同类技能时才用 `[]`（罕见——例如 rubric）。

---

## § 正文 —— 六种已观察到的版式（选一种，或自创）

现有技能中实际出现的版式如下。选适合的那一种；也可以自由发明新的。

1. **叙述 + 决策标准** —— 最适合判断类技能。示例：`Working/Architecture/solution-architecture-design.md`。
2. **任务清单 + 工具参考 + 踩坑** —— 最适合动手操作类工作流。示例：`Working/Developing/infrastructure-as-code.md`。
3. **控制映射 + 清单** —— 最适合治理/合规。示例：`Working/Security/cloud-security-compliance.md`、`Working/Policy/platform-module-compliance.md`。
4. **路由表 + 交互模型 + 踩坑** —— 适合参考类技能。示例：`Working/team-routing.md`。
5. **带阶段的过程循环** —— 适合可重复的 4–5 阶段工作流。示例：`Working/Policy/platform-module-compliance.md`（盘点 → 分诊 → 工作坊 → ADR → 修复）。
6. **触发驱动的分流流程图** —— 适合排障。示例：`Working/Troubleshooting/Cloud/resource-lock-troubleshooting.md`。

---

## § 活文档字段 —— 何时添加 `last_reviewed` + `maturity`

如果技能会**随着时间被修订**（规则变化、新工具、经验教训），添加：

```yaml
last_reviewed: YYYY-MM-DD
maturity: evolving   # 当你还在迭代时
maturity: stable     # 当你确信规则不会逐月变化时
```

为什么：读取该文件的模型能分辨是把规则当真理（stable）还是问一句"仍然成立吗？"（evolving）。每当你实质性修订正文时更新 `last_reviewed`。

---

## § Artifacts —— 当这个技能产出文件时

如果技能生成具体产出（模板、代码示例、实例文档、归档的邮件），存放在：

```
Working/Artifacts/<技能-id>/<文件>.md
```

已在使用的示例：`Working/Artifacts/email-preparation/`、`Working/Artifacts/devops-userstory-creation/`。

当技能文件提到"from artifacts"时，指的就是这个目录。不要把产出散落到 `Working/` 根目录或技能正文里。

---

## 保存前检查清单（保存新技能前运行）

- [ ] **决策** —— `Working/skill-creation-rubric.md` 判定为新建（得分 ≥ 9），而不是扩展。
- [ ] **文件名 = `<技能-id>.md`** 且 **`id:` 与它完全一致**。
- [ ] **`domain:`** 精确为 `Working` / `Living` / `reference`。
- [ ] **`proficiency:`** 在对应枚举中（见上表）。
- [ ] **`years:`** 是数字型 Working 技能的数字，否则为 `null`。
- [ ] **`tools:`** 是一个列表（为空用 `[]`，绝不省略）。
- [ ] **`triggers:`** 有 3–9 项；每项都是用户会真实说出的话。
- [ ] **`summary:`** 是一句话。
- [ ] **`related:`** 列的是真实存在的 `id`；理想情况下双向。

## 保存后检查清单（保存后运行）

- [ ] 在 `index.md` **Skills** 表加一行（id / title / domain / proficiency / years / triggers 概要 / file 路径）。
- [ ] 在 `index.md` **触发词映射**中加一条（与 frontmatter triggers 对应）。
- [ ] 如果技能会产出文件，**第一个产出**保存在 `Working/Artifacts/<技能-id>/` 下（必要时创建目录）。
- [ ] 文件中没有秘密——订阅 / 密码 / 令牌绝不进 `.md`。只记录其*存放位置*（密码管理器 / 私有保险库），不记录值。
- [ ] 向 `Memory/YYYY-MM-DD.md` 追加记录（强制记忆同步）。

---

## § Living 领域

`Living/_TEMPLATE.md` 现在用于 Living 领域的技能。Working 技能用本文件。Living 的差异是：

- `domain: Living`
- `proficiency:` 使用 Living 枚举（`novice` / `comfortable` / `fluent`）
- `years: null`（Living 技能很少用年来衡量）
- Living 技能通常放在主题子文件夹中（例如 `Living/Network/`）

---

**给急躁者的 TL;DR：** 复制此文件 → 设 `id` = 文件名 → 从表中选择 `domain` + `proficiency` → 写 3–9 条触发词 → 一句话 `summary` → 保存到正确的子文件夹 → 在 `index.md` 加 Skills 行 + 触发词映射条目 → 记入 `Memory/YYYY-MM-DD.md`。