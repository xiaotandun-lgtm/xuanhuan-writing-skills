# 玄幻小说写作技能

从长篇小说的章节分析中提炼可复用的检查规则，把细纲诊断、正文写作和审稿串成一套 Codex 工作流。

## 一例｜白石巷落闸

雨夜，沈苇要关闸护住巷里的两户人家。绷紧的船缆卡着闸槽，割断它，才能立刻落闸，姐妹用母亲银镯换来的一船药也会被冲走。

| 原始细纲 | 编辑诊断 | 改法 |
| --- | --- | --- |
| 铜符亮起，沈苇立刻断定河水倒灌。 | 铜符只能显示水位，单凭它看不出流向。 | 铜符先示警，沈苇再看见芦苇梗穿过闸口朝巷里漂。 |
| 沈苇割缆闭闸，天亮后找回整船药。 | 捞回整船药撤销了作者已经确定的代价。 | 关闸前让读者看清守住药船和及时落闸的取舍，关闸后让药船撞上乱石滩。 |

> “姐，娘那只镯子，就换了这一船。”
>
> 沈苇拔出刀，刀刃抵上绳子，一时没压下去。水已经漫过最底下那级石阶。就算能把缆从槽里扯出来，也赶不及把船拉进巷了。

[原始细纲](examples/sluice-gate/brief.md) · [确认后的细纲](examples/sluice-gate/approved-outline.md) · [正文与复审记录](examples/sluice-gate/walkthrough.md)

## 两个技能

| 技能 | 输入 | 交付 |
| --- | --- | --- |
| [`fantasy-editor-router`](.agents/skills/fantasy-editor-router/SKILL.md) | 项目设定和待检查的细纲或正文 | 有位置、有依据的诊断，附最小修改建议 |
| [`scene-prose`](.agents/skills/scene-prose/SKILL.md) | 作者确认的细纲和写作要求 | 正文和对照细纲的核对说明 |

## 在 Codex 里试用

下载或克隆仓库，在 Codex 中打开仓库根目录。项目技能已放在 `.agents/skills/`。在另一个项目使用时，把所需的技能目录连同 `references/` 一起复制到那个项目的 `.agents/skills/`。[Codex 技能目录说明](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

依次发送下列提示。第二步使用示例中已经确定的细纲，可单独试跑。已有同名技能时，在提示中给出本仓库内 `SKILL.md` 的相对路径。

```text
请使用本仓库的 $fantasy-editor-router，诊断 examples/sluice-gate/brief.md 的原始细纲，给出最小修改建议。
```

```text
请使用本仓库的 $scene-prose。examples/sluice-gate/approved-outline.md 是本次确认的写作任务，按其中的要求写一段正文，正文与核对说明分开交付。
```

```text
请使用本仓库的 $fantasy-editor-router，对照 examples/sluice-gate/approved-outline.md 审核刚才的正文，逐项核对判断依据、落闸取舍、药船代价和结尾边界。
```

## 方法来源

项目从《将夜》《牧神记》的章节笔记里提取反复出现的叙事方法。重点场景回读原文，部分章节采用章内抽读。每条方法都写明适用情形、具体做法和应退回修改的反例。

- 《牧神记》第 2 章《四灵血》提供了可见试验、人物解释与真实成因之间的信息差样本。对应的编辑检查是，角色的结论是否超出了他当时看到的证据。
- 《将夜》第六卷第 127–129 章用于研究规则的作用和限度。对应的编辑检查是，一种能力已经解决了什么，它还有什么保不住，人物是否为此作出选择。

示例「白石巷落闸」为本仓库原创演示，由 Codex 辅助起草和复核。仓库放的是归纳后的技法、使用说明和原创案例。README 和示例的组织方式参考了 [writing-dna-skill](https://github.com/larashero3-dotcom/writing-dna-skill)。
