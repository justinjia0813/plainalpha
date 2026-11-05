# 投点人话 · PlainAlpha

把投研报告写得自然、专业、有判断。让读者看清公司在做什么、客户为什么买、公司能赚多少钱，以及哪些事还没弄清。

**投点人话**，就是把研究结果说清楚。**PlainAlpha**，取 plain 的直白和 alpha 的投资语境；Skill 调用名是 `plain-alpha`。

它适合处理这样的句子：

> 公司已构建高壁垒客户认证体系，商业化兑现确定性持续提升。

改成：

> 公司披露已通过两家客户的指定测试，其中一家有过一次复购。客户导入已有进展，接下来要看能否稳定交货，以及这些订单能给公司带来多少利润。

上例为自拟例句。给定资料是公司披露的“两家客户通过指定测试、其中一家复购一次”，改写保留了这一范围和信息归属。

## 它能帮你做什么

| 任务 | 重点 |
| --- | --- |
| 行业报告 | 先写研究判断，再解释需求、竞争和收益如何变化 |
| 投资讨论稿 | 写清投资理由、主要反对理由和作决定的条件 |
| 投后更新 | 说明发生了什么变化、原判断是否改变、下一步做什么 |
| 给合伙人的短汇报 | 留下最重要的判断、依据、限制和动作 |
| 现有稿件改写 | 减少空话、刻意对照和术语堆叠，保留原有事实与结论 |

常见编辑动作：删去为强调而添加的“不是 X，而是 Y”；把“价值捕获机制”展开为公司如何留下利润；把“已验证”“有望”“管理层预计”等词放在准确的位置。

必要的技术名词和财务指标仍会保留。目标是让读者理解其业务含义，同时保住数字、口径、来源和判断条件。

## 怎么工作

读原材料 → 确定读者和用途 → 核对事实与状态 → 组织判断和理由 → 改写 → 对照原稿检查。

例如，客户测试、认证、交货、确认收入和回款是不同的进展。文字变顺以后，这些区别仍须清楚。纯语言改写直接使用已有资料；需要补充研究时，先指出具体缺口。

## 安装

本仓库根目录就是 Skill 目录，包含 `SKILL.md`、`agents/` 和 `references/`。以下方式手动安装，不需要构建。

先检查目标目录。如果目录已经存在，查看其中的内容和来源，再决定如何更新；不要直接覆盖。

**Codex**

```sh
git clone https://github.com/justinjia0813/plain-alpha.git ~/.codex/skills/plain-alpha
```

**Claude Code**

```sh
git clone https://github.com/justinjia0813/plain-alpha.git ~/.claude/skills/plain-alpha
```

安装后新开一次会话，确认客户端能找到 `plain-alpha`。两个位置供各自客户端使用，按需选择。

## 直接调用

在 Codex 中，显式调用这个 Skill，并附上原稿或资料：

```text
$plain-alpha 把这份研究改为两页投资讨论稿，保留来源、数字和未知项。
```

```text
$plain-alpha 将本周项目进展写成 300 字汇报，说明变化、影响和下一步。
```

已有分析框架或模板时，一并提供。只想改语言，可以直接说明“保持结构和结论，只改表达”。

### 与 mathink 配合

`mathink` 负责材料行业分析，`plain-alpha` 将分析写成投资读者容易理解的报告。研究结果应带上来源、口径、模型假设和未知项，表达稿再返回原分析核对。

下例适用于已另行安装 `mathink` 的 Codex：

```text
$mathink $plain-alpha 分析 CMP 抛光液行业，先完成材料研究，再按八章写成合伙人可读的报告。
```

本仓库只提供 `plain-alpha`。没有 `mathink` 时，也可以直接处理你已有的研究材料。

## 先看样本

- [CMP 抛光液行业研究范文](examples/cmp-slurry-industry.md)：使用真实公开来源，展示完整研究如何形成可读的行业判断。
- [语言改写前后对照](examples/voice-before-after.md)：虚构业务场景，展示句子怎样改、哪些事实须保留。
- [中文声音与例句](references/language-and-examples.md)：用词、句式和事实强度的具体规则。
- [六份机构原文的样本拆解](references/sample-analysis.md)：学习了什么，以及各篇文档的使用边界。
- [验证范围](docs/validation.md)：目前的有限模拟案例、检查方法和未覆盖部分。

## 方法参考与许可

表达方法参考了六份机构公开原文。这些文档分别属于行业分析、客户备忘录和历史项目投资建议；本 Skill 的规则是作者的编辑归纳。

- a16z：[Who Owns the Generative AI Platform?](https://a16z.com/who-owns-the-generative-ai-platform/)
- Bessemer：[State of the Cloud 2024](https://www.bvp.com/atlas/state-of-the-cloud-2024)、[Shopify 投资备忘录](https://www.bvp.com/memos/shopify)、[Twilio 投资备忘录](https://www.bvp.com/memos/twilio)
- Menlo Ventures：[2024: The State of Generative AI in the Enterprise](https://menlovc.com/2024-the-state-of-generative-ai-in-the-enterprise/)
- Oaktree：[Sea Change](https://www.oaktreecapital.com/insights/memo/sea-change)

本仓库的原创 Skill 指令、参考说明和示例采用 [MIT 许可](LICENSE)。外部原文、商标及引用资料的权利仍归各自权利人。仓库提供来源链接和自己的分析，不收录大段原文。

语言编辑也参考了 Humanizer 对常见AI句式的整理，许可与来源见 [第三方说明](THIRD_PARTY_NOTICES.md)。
