# 玄幻小说写作技能

从长篇小说的章节分析中提炼可复用的检查规则，把细纲诊断、正文写作和审稿串成一套 Codex 工作流。

## 原创演示

雨夜，守闸人要落闸护住巷里的两户人家。船缆卡在闸槽里，割断它就能及时落闸，但一船药也会被冲走。

| 原始细纲 | 编辑诊断 | 改法 |
| --- | --- | --- |
| 铜符亮起，守闸人立刻断定河水倒灌。 | 铜符只能显示水位，单凭它看不出流向。 | 铜符先示警，再用芦苇梗漂进巷内交代水流方向。 |
| 守闸人割缆闭闸，天亮后找回整船药。 | 捞回整船药撤销了作者已经确定的代价。 | 先写清守住药船和及时落闸的取舍，再写药船撞上乱石滩。 |

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

这些方法来自中文长篇小说的章节笔记和重点场景复核，主要关注人物如何获得信息、规则怎样影响选择，以及关键选择会带来什么后果。每条方法都配有适用情形、具体做法和反例。

案例由 Codex 辅助起草和复核，用于演示这些方法怎样应用到原创场景。README 和示例的组织方式参考了 [writing-dna-skill](https://github.com/larashero3-dotcom/writing-dna-skill)。
