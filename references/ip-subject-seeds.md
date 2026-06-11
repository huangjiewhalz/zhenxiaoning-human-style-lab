# IP Subject Seeds

用户没有自己的角色图或角色设定时，用这里的原创主体种子起步。种子只是第一版视觉脚手架，不代表用户已经拥有成熟 IP。用户后续提供角色图、名称、动作偏好后，要优先覆盖这些种子。

## 使用规则

- 一次最多推荐 2 个主体，避免让用户陷入选择菜单。
- 先根据用户内容场景选择主体，再写外形，不要随机抽。
- 每个主体都要能承担核心动作，不能只是角落装饰。
- 不使用第三方角色名、在世创作者风格、品牌 IP 或可识别案例构图。
- 如果用户选定主体，生成 `ip-subject.md` 时要写清：当前为“候选主体”，待后续校准。

## 选择表

| 主体 | 适合场景 | 气质 | 不适合 |
| --- | --- | --- | --- |
| 墨点操作员 | AI 工具、知识解释、系统状态 | 冷静、克制、轻微怪诞 | 儿童感、强情绪内容 |
| 纸片工人 | 写作、文档、知识库、笔记 | 认真、朴素、整理感 | 强视觉冲击海报 |
| 红章操作员 | 判断、审核、反风格、观点内容 | 直接、严谨、有边界 | 温柔陪伴型内容 |
| 线团人 | 信息过载、流程、关系、混乱到清晰 | 找线索、解问题 | 极简品牌 KV |
| 空心方盒 | 产品、模块、UI、工具链 | 容器感、系统感 | 情绪故事、生活方式 |

## 样例资产

这些图片是原创主体方向的小样，用于让用户快速理解“主体可替换”。不要把它们当作必须复刻的固定模板；生成用户 Skill 时，应根据用户内容场景、偏好和后续校准改写外形、动作和道具。

| 主体 | 样例路径 |
| --- | --- |
| 墨点操作员 | `assets/examples/subjects/ink-dot-operator.png` |
| 纸片工人 | `assets/examples/subjects/paper-worker.png` |
| 红章操作员 | `assets/examples/subjects/red-stamp-operator.png` |
| 线团人 | `assets/examples/subjects/thread-person.png` |
| 空心方盒 | `assets/examples/subjects/hollow-box.png` |

## 墨点操作员

### 外形

不规则墨迹、印痕或水滴状主体。眼睛可以是短横线、空心小孔或单个缺口。四肢可用细线支架、夹子或小脚架表达。不要使用“黑色实心小怪物 + 白点眼 + 细腿”的完整组合。

### 性格

冷静、认真、笨拙，不卖萌。像一个在白纸上整理系统状态的小操作员。

### 动作库

压住、挡住、夹住、标记、搬运、守口、托起、贴签。

### 适合

- 把 AI 默认输出压成个人风格。
- 拦截 AI 味和模板句。
- 表达“风格资产盒”“反风格闸口”“待校准样本”。

### 禁止

- 不要变成现成第三方角色。
- 不要过度圆润可爱。
- 不要只站在旁边。

### 示例 prompt

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.
Use a clean white canvas, loose black pencil-like lines, and a few short handwritten Chinese notes in red, orange, or blue.
Original subject: 墨点操作员, an irregular ink-drop operator with one small cutout eye and tiny clamp-like supports, serious and not cute.
Topic: 把默认 AI 味拦在风格资产外面。
Meaning: User style rules should filter generic AI phrases before output.
Scene: The ink operator presses down a small gate labeled "反风格", while loose template phrases bounce outside. On the right, a neat card labeled "像我" exits a paper slot.
Short notes: 默认味 / 反风格 / 待校准 / 像我
Avoid third-party IP, polished vector art, slide diagrams, dense arrows, and corner titles.
```

## 纸片工人

### 外形

折起来的一张纸或便签主体，有简笔眼睛和细线手脚。边缘可以有折痕、夹角和贴纸痕迹。

### 性格

认真、朴素、像在整理文档。适合把碎片变成结构。

### 动作库

折叠、归档、递纸、贴标签、压平、装订、拆页。

### 适合

- 写作风格归档。
- 文章结构拆解。
- 知识库、Notion、文档型内容。

### 禁止

- 不要做成可爱纸娃娃。
- 不要给复杂服装。
- 不要把整页文字塞进图里。

### 示例 prompt

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.
Use white canvas, black hand-drawn pencil outlines, spacious layout, and a few handwritten Chinese notes.
Original subject: 纸片工人, a folded paper worker with simple line limbs and a calm expression.
Topic: 把 5 篇旧作品整理成风格档案。
Meaning: Past works become reusable style cards.
Scene: The paper worker flattens messy notes on the left, stamps three small cards in the center, and slides them into drawers labeled "语气", "结构", "禁用词".
Short notes: 旧作品 / 语气 / 结构 / 禁用词 / 可复用
Avoid third-party characters, copied compositions, PPT diagrams, and big titles.
```

## 红章操作员

### 外形

一个小红印章或印泥块主体，有短脚和极简眼睛。身体可以是红色方章、圆章或斜放印章，不要像品牌 logo。

### 性格

直接、严谨、有边界。像负责审核风格偏差的小审查员。

### 动作库

盖章、否决、标红、压住、挡回、确认、圈出。

### 适合

- 反风格清单。
- “不要 AI 味”的质检。
- 观点类内容的边界判断。

### 禁止

- 不要做成权威机构印章。
- 不要恐吓感太强。
- 不要满屏红字。

### 示例 prompt

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.
White canvas, loose black sketch lines, restrained red/orange/blue handwritten notes.
Original subject: 红章操作员, a small red stamp operator with tiny feet and a strict calm face.
Topic: 生成前先过反风格检查。
Meaning: Generic phrases must be rejected before content is delivered.
Scene: The red stamp operator stands at a small review desk, stamping "退回" on a pile of template phrases. A clean note labeled "可发布" waits on the right.
Short notes: 模板句 / 退回 / 反风格 / 可发布
No third-party IP, no official seal imitation, no poster style, no dense explainer.
```

## 线团人

### 外形

由几根松散黑线组成的主体，可以有小夹子或线结作为身体。眼睛用缺口或短线表达，不做圆润萌感。

### 性格

从混乱里找线索。认真、耐心，有一点笨拙。

### 动作库

接线、剪断、夹住、拉出路径、打结、解结、贴签。

### 适合

- 信息过载。
- 流程关系。
- 从混乱素材里提炼风格线索。
- 内容结构和脚本分镜。

### 禁止

- 不要画成毛线吉祥物。
- 不要线条太密导致看不懂。
- 不要把所有关系都画出来。

### 示例 prompt

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.
Use a clean white page, loose black line drawing, sparse handwritten Chinese notes, and clear empty space.
Original subject: 线团人, a small figure made of loose black threads with a tiny clip body, serious and not cute.
Topic: 从混乱作品里拉出个人风格线索。
Meaning: The user does not need a perfect style at first; they need a few stable threads to test.
Scene: The thread figure pulls three colored strings from a messy pile of notes, clips them onto cards labeled "语气", "结构", "禁用词", and leaves the rest as "待校准".
Short notes: 混乱样本 / 语气 / 结构 / 禁用词 / 待校准
Avoid copied examples, third-party IP, slide layout, and overly dense connections.
```

## 空心方盒

### 外形

一个手绘空心盒子主体，有极简眼睛和短线手脚。可以开盖、嵌套、吐出卡片或装入样本。

### 性格

像产品系统里的小容器。稳定、朴素、适合模块化表达。

### 动作库

装入、吐出、分类、打开、嵌套、递交、收纳。

### 适合

- 产品功能。
- 工具链。
- UI 文案。
- 风格资产包结构。

### 禁止

- 不要做成科技感 3D 方块。
- 不要画成复杂架构图。
- 不要把文件树截图搬进画面。

### 示例 prompt

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.
Use white background, black hand-drawn lines, spacious composition, and a few short Chinese handwritten notes.
Original subject: 空心方盒, a hand-drawn hollow box character with small line limbs, calm and system-like.
Topic: 个人风格资产包不是一个 prompt，而是一组可复用模块。
Meaning: Style should be stored as several reusable files instead of a single vague instruction.
Scene: The box character opens its lid and sorts small cards into compartments: "style", "anti", "patterns", "QA". A simple output note comes out on the right.
Short notes: style / anti / patterns / QA / 输出
Avoid third-party IP, file-tree screenshots, formal architecture diagrams, and visual clutter.
```
