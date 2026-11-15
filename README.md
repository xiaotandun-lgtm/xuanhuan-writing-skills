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

项目以中文长篇小说的章节笔记为基础，回读重点场景，归纳人物选择、信息揭露和情节收束的写法。

1. **按场景记录因果。** 记下人物当时知道什么、想保住什么、为什么得在这一刻行动，以及选择改变了什么。遇到推理或规则揭露时，分别记录可观察的事实、人物的解释和读者已经知道的信息。
2. **比较写法和适用条件。** 把承担相近叙事任务的场景放在一起，结合反例判断写法何时适用。比如，读者需要先理解某条规则才能看懂人物的冒险，可以提前交代必要条件。需要读者跟着人物一起发现异常时，可以先写可见结果，再让人物依据线索作出判断。
3. **转成写作提示和审稿问题。** 细纲要能说明判断依据从哪里来、选择受什么限制、后果在哪一处兑现。正文用动作、对白和可见结果把这些关系写出来。复审把问题定位到具体段落，给出范围明确的改法。

原创案例从原始细纲出发，依次完成诊断、起草和复审。复审发现初稿有一处时间衔接跳得太快，定向补写了一个动作，交代后续结果为何在此时发生。案例由 Codex 辅助起草和复核。[查看完整演示](examples/sluice-gate/walkthrough.md)

README 和示例的组织方式参考了 [writing-dna-skill](https://github.com/larashero3-dotcom/writing-dna-skill)。

## 许可证

本仓库的技能、文档和原创示例采用 [MIT 许可证](LICENSE)。
