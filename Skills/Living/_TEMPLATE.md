---
# 这是 Living 领域的规范技能模板。
# 使用前：阅读 Working/skill-creation-rubric.md，决定是创建新技能还是扩展现有技能。

id: <技能-id-kebab-case>            # 必须与文件名完全一致
title: <人类可读的技能标题>
domain: Living                         # Working | Living | reference
proficiency: <见下方枚举>         # Living 刻度：novice | comfortable | fluent
years: null                            # Living 技能很少用年来衡量
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

> 正文按设计**完全自由**。唯一标准化的部分是上面的 YAML frontmatter——它让 `index.md` 可以把触发词路由到这个文件。选任何适合该技能的版式。

---

## § Domain、proficiency、years —— 速查

| 字段 | 取值 | 说明 |
|-------|-------|--------|
| `domain` | `Working` · `Living` · `reference` | `reference` = 无技能熟练度的路由/参考文档。谨慎使用。 |
| `proficiency`（Working） | `beginner` · `intermediate` · `advanced` · `expert` | 对照触发场景做自我评估。 |
| `proficiency`（Living） | `novice` · `comfortable` · `fluent` | 同一个思路，用个人尺度的措辞。 |
| `proficiency`（`reference`） | `reference` | 唯一的字面值；不在 Working 或 Living 的刻度上。 |
| `years` | 整数（数字型 Working 技能）· `null` | **仅**用于"年限能有效衡量技能"的 Working 技能。Living 技能填 `null`。 |

---

## § Triggers —— 路由契约

- **3–9 条短语。** 少于 = 太模糊；多于 = 重复。
- 每条短语都是用户（或模型）在这个技能适用时会输入/说出的话。
- 触发词驱动 `index.md` 的**触发词映射**。Skills 表的 `triggers` 列是压缩摘要；frontmatter 的列表才是唯一权威来源。

---

## § Related —— 双向链接

- 列 `id`（不是路径）。如果你链接 `[proxy-subscription]`，该链接必须能解析到一个 `id: proxy-subscription` 存在的文件。
- **按约定双向：** 当你加 A → B，也要加 B → A（或注明 A 的反向在 B 的 related 中）。
- 只有没有同类技能时才用 `[]`（罕见）。

---

## § 正文 —— 适合生活技能的版式

现有技能中出现的 Living 技能版式如下。选适合的那一种；也可以自由发明新的。

1. **任务清单 + 踩坑** —— 最适合动手操作类工作流（例如"如何配置 X"）。
2. **触发驱动的分流流程图** —— 最适合排障（例如"网络连不上"）。
3. **路由表 + 交互模型 + 踩坑** —— 适合参考类技能（例如"哪台设备用哪个客户端"）。

---

## § 活文档字段 —— 何时添加 `last_reviewed` + `maturity`

如果技能会**随着时间被修订**（规则变化、新工具、经验教训），添加：

```yaml
last_reviewed: YYYY-MM-DD
maturity: evolving   # 当你还在迭代时
maturity: stable     # 当你确信规则不会逐月变化时
```

---

## § 秘密规则（Living 技能）

- 订阅、密码、令牌、个人标识符（邮箱、私有 IP、账号 ID）**绝不**进 `.md` 文件。
- 只记录它们*在哪里*（密码管理器 / 私有保险库 / 供应商控制台），不记录值。
- 功能性需要时，RFC1918 局域网地址和非标识性设备信息可以接受——在 Gotchas 中标注为私有。

---

## 保存前检查清单（保存新技能前运行）

- [ ] **决策** —— `Working/skill-creation-rubric.md` 判定为新建（得分 ≥ 9），而不是扩展。
- [ ] **文件名 = `<技能-id>.md`** 且 **`id:` 与它完全一致**。
- [ ] **`domain:`** 精确为 `Living`。
- [ ] **`proficiency:`** 是 `novice` / `comfortable` / `fluent`。
- [ ] **`years:`** 是 `null`。
- [ ] **`triggers:`** 有 3–9 项；每项都是用户会真实说出的话。
- [ ] **`summary:`** 是一句话。
- [ ] **`related:`** 列的是真实存在的 `id`；理想情况下双向。
- [ ] 文件中没有秘密。

## 保存后检查清单（保存后运行）

- [ ] 在 `index.md` **Skills** 表加一行（id / title / domain / proficiency / triggers 概要 / file 路径）。
- [ ] 在 `index.md` **触发词映射**中加一条（与 frontmatter triggers 对应）。
- [ ] 向 `Memory/YYYY-MM-DD.md` 追加记录（强制记忆同步）。

---

**给急躁者的 TL;DR：** 复制此文件 → 设 `id` = 文件名 → `domain: Living` + 从 Living 刻度选择 `proficiency` → 写 3–9 条触发词 → 一句话 `summary` → 保存到正确的主题子文件夹 → 在 `index.md` 加 Skills 行 + 触发词映射条目 → 记入 `Memory/YYYY-MM-DD.md`。