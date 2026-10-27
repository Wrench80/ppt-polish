---
name: ppt-polish
description: Beautify an existing PowerPoint deck for a Chinese university scenario (课程汇报, 学术科研, 竞赛答辩, 评优展示, 求职升学), removing generic AI styling and matching what teachers and advisors consider professional. Use when the user asks to 美化/打磨/排版/润色/优化 an existing PPT, or says a deck has "AI 味" or "太模板" or "老师/导师觉得不够专业".
---

# PPT Polish（大学生场景 PPT 美化）

把一份**内容已齐全、但观感像 AI 生成或套模板**的 PPT，改造成干净、专业、贴合具体场景的成品。**只修呈现，不改结论与事实**。灵感与部分规则来自 `academic-report-ppt`（GeraltVitas，MIT）：保留它的"去 AI 味 + 导师视角"，补全多场景视觉风格与"美化已有 deck"的入口。

## 何时使用

- 用户要求**美化 / 打磨 / 排版 / 润色 / 优化**一份已有的 `.pptx`，或说它"有 AI 味""太模板""老师/导师觉得不够专业"。
- 用户指定了场景，或场景能从标题 / 结构 / 受众判断。
- 不适用：没有源内容从零做一份 PPT（交给 Presentations 技能创建，仅在要学术风时叠加本技能的 `references/scenarios.md`）；纯文案改写而没有文件。

## 工作流

1. **判断场景**。按受众归类到五大类之一（见下）。用户没指定时，从标题、结构、受众推断；确实分不清才问用户（给 2–3 个候选，不开放式追问）。
2. 用环境里的演示文稿技能（本环境为 Presentations 技能，`@oai/artifact-tool`）**读取**原 deck：盘点幻灯片、母版、字体、配色、已有图表与图片、备注。
3. 读 `references/scenarios.md` 里对应类别的设计规范；读 `references/style-rules.md` 里共用的"去 AI 味 + 导师审美"规则。
4. 按顺序改：**(a) 修文字**（页标题 → 结论式；正文 → 去 AI 词、收紧）→ **(b) 修版式与层级** → **(c) 套场景配色、删装饰噪音** → **(d) 图表/表格改成数据优先** → **(e) 整体一致性收尾**。
5. **保留原意，只收紧措辞**：不虚构结论、数据或引用；数字、单位、符号、引用标注一律保留原值。
6. 交付成品 + 一句"改了什么、为什么"，遵循所用演示文稿技能的交接规则。

## 场景路由（按受众分五类）

| 大类 | 受众 | 子场景 | 详见 |
|---|---|---|---|
| 学术科研型 | 导师 / 评审 | 组会汇报 · 开题/中期 · 学位答辩 · 学术会议 | `references/scenarios.md` 一 |
| 竞赛评审型 | 评委 | 学科竞赛答辩 · 创新创业路演 | `references/scenarios.md` 二 |
| 课程教学型 | 老师 / 同学 | 课程/小组汇报 · 文献汇报 · 课程设计答辩 | `references/scenarios.md` 三 |
| 评优展示型 | 评委 / 师生 | 奖学金答辩 · 社会实践/志愿服务 · 述职/竞选 | `references/scenarios.md` 四 |
| 求职升学型 | 面试官 / 招生老师 | 实习转正 · 求职面试 · 考研复试/保研夏令营 | `references/scenarios.md` 五 |

## 所有类别都不可违反的底线

- **一页一个要点**：页标题写结论（"X 方法把误差降到 3%"），不写名词标签（"结果分析"）。
- **清除 AI 味**：紫/蓝渐变大底、emoji、无意义 3D 装饰、纯装饰图标、与数据无关的配图、软阴影圆角卡片堆叠——一律删。
- **图有编号图注，轴有标签和单位**；图/表里的数字必须与正文一致（改一处全 deck 同步）。
- **整套 deck 一套配色 + 最多两种字体**。
- **不许文字墙**：要点是短语不是整句；细节进备注或附录。
- **守住科学边界**：不写因果、不外推、不把噪声说成信号（完整规则见 `references/style-rules.md`）。

## 参考文件

- `references/scenarios.md` — 五大类、13 个子场景的配色 / 字体 / 版式 / 图表 / 语气与验收清单。
- `references/style-rules.md` — 去 AI 味（词表 + 视觉）、导师审美标准、科学边界、讲稿与程序化验收。

