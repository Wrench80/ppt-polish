# ppt-polish

一个给**大学生**用的 PPT 美化 Agent Skill：把一份"有 AI 味 / 套模板"的 PPT，改造成干净、专业、贴合具体场景的成品。**只修呈现，不改结论与事实。**

## 适用场景（按受众分五类）

| 大类 | 受众 | 子场景 |
|---|---|---|
| 学术科研型 | 导师 / 评审 | 组会汇报 · 开题/中期 · 学位答辩 · 学术会议 |
| 竞赛评审型 | 评委 | 学科竞赛答辩 · 创新创业路演 |
| 课程教学型 | 老师 / 同学 | 课程/小组汇报 · 文献汇报 · 课程设计答辩 |
| 评优展示型 | 评委 / 师生 | 奖学金答辩 · 社会实践/志愿服务 · 述职/竞选 |
| 求职升学型 | 面试官 / 招生老师 | 实习转正 · 求职面试 · 考研复试/保研夏令营 |

## 它能做什么

- 按场景套用一套完整设计系统：配色（具体色值）、字体字号、版式、图表、语气。
- 去除 AI 味：禁用词表（赋能/助力/闭环/抓手/颗粒度/多模态…）+ 10 条"AI 模板脸"视觉红线（渐变底、emoji、堆图标、满屏 bullet、居中一切…）。
- 贴合老师/导师审美：结论式页标题、图有编号图注、轴有标签和单位、科学边界、讲稿 30–60 秒/页、程序化验收。

## 安装

**Codex（本地）**：把本仓库放入 `~/.codex/skills/ppt-polish/`，即：

```text
~/.codex/skills/ppt-polish/
├── SKILL.md
├── references/
│   ├── scenarios.md
│   └── style-rules.md
└── agents/openai.yaml
```

**其他支持 SKILL.md 的 agent**：克隆仓库到对应的 skills 目录即可（如 `~/.claude/skills/ppt-polish`）。

## 用法

对 agent 说：

- 「用 ppt-polish 把这份 PPT 按**学术答辩**风格美化」
- 「这份 PPT 太 AI 味了，帮我去掉 AI 味、弄成导师看着顺眼的样子」
- 不指定场景时，agent 会从标题/结构/受众推断，分不清时会问你。

## 结构

- `SKILL.md` — 入口：用途、工作流、场景路由、底线规则。
- `references/scenarios.md` — 五大类、13 个子场景的配色/字体/版式/图表/语气/验收清单。
- `references/style-rules.md` — 去 AI 味（词表+视觉）、导师审美、科学边界、讲稿与程序化验收。

## 灵感与致谢

"去 AI 味词表、结论式标题、科学边界、讲稿与程序化验收"的思路取自开源技能 [GeraltVitas/academic-report-ppt](https://github.com/GeraltVitas/academic-report-ppt)（MIT License），本技能在其基础上扩展为多场景美化工作流。

## License

MIT
