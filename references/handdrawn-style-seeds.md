# Handdrawn Style Seeds

用于给个人风格资产包选择“手绘工具感”。这些种子都服务同一个目标：降低默认 AI 精修感，让画面更像人用真实材料画出来的。

## 使用规则

- 先选手绘工具风格，再选原创 IP 主体。
- 一次只推荐 1-2 种手绘风格。
- 每种风格都要写清适合、不适合、颜色、线条、失败信号。
- 不模仿具体画师、博主、品牌或可识别作品。
- 如果用户没有偏好，默认从“铅笔草图风”起步；需要更温暖或更个人 IP 时选“蜡笔涂鸦风”；需要诊断、批改或去 AI 味修复时选“红笔批改风”。

## 当前正式风格

只维护三种核心手绘风格，避免变成风格大全：

- **铅笔草图风**：默认主风格，适合大多数正文配图、产品解释、轻知识和教程。
- **蜡笔涂鸦风**：温暖变体，适合个人 IP、情绪感、轻松内容和更有新鲜感的正文配图。
- **红笔批改风**：诊断专用，适合去 AI 味、反风格清单、标题修改和文案 QA。

暂不默认加入 Riso、拼贴、木刻、纸艺等风格。它们可以作为未来实验方向，但不进入自动选择，除非用户明确要求“更封面感”“更强视觉冲击”或“想试实验风格”。

## 铅笔草图风

### 一句话

像创作者在白纸上用铅笔认真推演一个想法：线条松、轻重有变化，结构清楚但不精修，像真实思考留下的草稿。

### 适合

- 默认正文配图。
- 产品解释、功能说明、轻知识、教程步骤。
- 个人风格资产、写作结构、内容工作流、AI 味诊断前的轻量解释。
- 用户没有指定画风，但希望“别太 AI、别太花、别太幼稚”的场景。
- 需要留白多、主体小、局部轻描的配图。

### 不适合

- 需要强情绪、强封面视觉冲击的内容。
- 需要彩色记忆点或更温暖个人 IP 氛围的内容。
- 已经明确要红笔批改、错误诊断或 before/after 修改痕迹的任务。
- 复杂数据图、正式架构图和需要精确 UI 复刻的内容。

### 视觉材料

- 白纸或轻微纸纹背景。
- 铅笔、自动铅笔、灰黑草图线。
- 轻微重复描边、擦除痕、淡淡阴影。
- 少量红、蓝或橙色手写批注。
- 局部道具和主体动作，不画满完整场景。

### 颜色规则

- 主线：灰黑、蓝黑或深灰，不要纯黑硬边。
- 填色：默认少量或不填色；如果需要角色识别，可保留 1-2 个低饱和识别色。
- 批注：红、蓝、橙最多 1-2 种，像小手写注，不做大标题。
- 文字：只使用 prompt 里列出的短词，不自动新增标题、解释句或段落。
- 背景：保持白底或浅纸色，不加渐变、光效和大面积色块。

### 线条规则

- 线条允许断裂、轻微抖动、重复描边。
- 阴影用稀疏斜线、轻擦痕或淡灰涂抹。
- 箭头、框线、标签都要像临时手写，不要像矢量组件。
- 轻配图主体群缩小，保留明显外圈留白。
- 不追求完美透视和精密结构，优先保留“正在想”的痕迹。

### 适合的主体

- 空心方盒：适合产品、模块、工具机制。
- 纸片工人：适合写作、文档、风格资产整理。
- 线团人：适合混乱线索、流程和关系。
- 用户上传角色：适合保留角色识别点，但要降低光滑感和商业插画感。

### 禁止画法

- 不要做成商业矢量插画。
- 不要做成漂亮 UI mockup 或 PPT 架构图。
- 不要变成儿童简笔画。
- 不要加 3D 光影、玻璃感、霓虹、复杂渐变。
- 不要把铅笔风理解成“黑白草稿低完成度”；结构仍然要清楚。
- 不要模仿任何具体画师、博主、品牌或可识别作品。

### 示例 prompt

```text
Create a single horizontal 16:9 pencil sketch style illustration for a Chinese article.
Use a clean white paper background, loose gray-black pencil lines, light sketch shadows, slight repeated strokes, and a few small handwritten Chinese notes in red or blue. The image should feel like a real thinking sketch on paper, not a polished vector infographic, UI screen, poster, or children's drawing.

Original subject:
空心方盒, a small original hollow box character with simple eyes and thin pencil-like legs, calm and practical, not cute.

Topic:
让 AI 记住我的风格，而不是每次从零猜。

Meaning:
The user needs reusable style assets, not a longer prompt every time.

Scene:
Use a light local close-up, not a full scene. In the center, the hollow box character gently places one small note labeled "语气" into a simple open drawer. Beside it are two tiny pencil notes labeled "结构" and "禁用词". A soft arrow points to a small output slip labeled "像我一点".

Short Chinese notes:
语气 / 结构 / 禁用词 / 像我一点

Exact Chinese text allowed:
语气 / 结构 / 禁用词 / 像我一点

Framing:
Keep the subject/object cluster small, around 35% of canvas width, with large blank white margins on all sides. No full desk, no full room, no big title.

Color:
Use gray-black pencil lines, very light gray shading, and only tiny red or blue handwritten notes.

Avoid:
polished vector art, 3D rendering, glossy gradients, dense arrows, full scene, slide layout, commercial mascot style, copied examples, third-party IP, recognizable living-artist style, and large title text.
```

### QA 失败信号

- 看起来像未完成草稿，核心意思不清楚。
- 线条太干净、边缘太锐，像矢量图。
- 主体或道具太大，四周没有呼吸感。
- 批注变成大标题或信息图标签。
- 为了“铅笔感”变成全黑白，丢掉角色识别点。
- 只有道具，没有主体参与核心动作。

## 蜡笔涂鸦风

### 一句话

像创作者拿几支蜡笔在白纸上认真解释一个想法：颜色不均匀，边缘有颗粒感，线条有笨拙感，但结构仍然清楚。

### 适合

- 个人 IP 和原创主体。
- 创作者状态、成长、情绪、轻知识。
- “AI 不像我”“从混乱到清楚”“把风格沉淀成资产”这类有一点人的手感的主题。
- 需要比黑白线稿更温暖、更有新鲜感的正文配图。

### 不适合

- 严肃 B2B 架构图。
- 复杂系统图。
- 需要精确可读的小字信息图。
- 法律、医疗、金融等高严肃度内容。

### 视觉材料

- 白纸或浅色纸面。
- 蜡笔质感线条。
- 不均匀色块。
- 边缘轻微颗粒和断裂。
- 少量手写中文短词。

### 颜色规则

- 主线：深灰、蓝黑或深棕，不要纯数字黑的硬边。
- 主色：选 2-3 个蜡笔色，例如蓝、黄、红、橙、绿色。
- 背景保持干净，不要做满版彩色。
- 色块不追求涂满，允许露白。

### 线条规则

- 线条可以歪、抖、重复描边。
- 形状可以不完全闭合。
- 箭头和框都要像手画的。
- 不能变成矢量图标、商业插画或儿童贴纸。

### 适合的主体

- 纸片工人：适合文档、风格归档。
- 线团人：适合从混乱样本里抽线索。
- 空心方盒：适合风格资产包和模块化表达。

### 禁止画法

- 不要画成幼儿园儿童画。
- 不要满屏彩色，保持克制。
- 不要可爱吉祥物化。
- 不要 3D、渐变、光影、精修插画。
- 不要模仿任何具体画师。

### 示例 prompt

```text
Create a single horizontal 16:9 crayon-style illustration for a Chinese article.
Use a clean white paper background. Draw with uneven wax-crayon strokes, slightly broken edges, visible hand pressure, and imperfect hand-drawn shapes. Keep the layout sparse and readable.

Original subject:
线团人, a small original figure made of loose crayon-like threads with a tiny clip body, serious and not cute.

Topic:
让 AI 记住我的风格，而不是每次从零猜。

Meaning:
The user needs reusable style assets, not a longer prompt every time.

Scene:
On the left, messy crayon notes labeled "旧作品", "讨厌词", "常用结构" are tangled together.
The thread figure pulls three colored crayon strings from the mess and clips them onto three cards labeled "语气", "结构", "禁用词".
On the right, a small output card says "像我一点".

Short Chinese notes:
旧作品 / 语气 / 结构 / 禁用词 / 像我一点 / 待校准

Exact Chinese text allowed:
旧作品 / 语气 / 结构 / 禁用词 / 像我一点 / 待校准

Color:
Use a small crayon palette: blue, yellow, red, orange, and dark gray. Leave plenty of white space. Color blocks should be uneven and handmade.

Avoid:
polished vector art, 3D rendering, glossy gradients, dense arrows, slide layout, commercial mascot style, children's poster style, copied examples, third-party IP, and corner titles.
```

### QA 失败信号

- 看起来像 AI 精修插画，而不是蜡笔。
- 太儿童画，读者会觉得低幼。
- 色彩太满，正文配图变成海报。
- 主体只是可爱装饰，没有完成核心动作。
- 中文标签太多或太小。

## 红笔批改风

### 一句话

像编辑或作者本人拿红笔在 AI 草稿上做批改：圈掉模板句、划掉空话、写下边注，最后留下更像人的表达。

### 适合

- 去 AI 味。
- 反风格清单。
- 标题修改。
- 文案诊断。
- “这句话不像我”的 before/after 对比。
- 把风格 QA 做成一张可视化检查图。

### 不适合

- 温柔陪伴类内容。
- 需要完整世界观或角色动作的插图。
- 产品架构和复杂流程。
- 只想要漂亮配图、不想展示修改痕迹的内容。

### 视觉材料

- 白色稿纸、横线纸或打印稿。
- 黑色或蓝黑色原文。
- 红笔圈、叉、划线、箭头、边注。
- 少量蓝笔补充说明。
- 可以有便签、回形针、夹子，但不要堆满。

### 颜色规则

- 黑/蓝黑：原文和稿纸线。
- 红色：删除、退回、圈重点、边注。
- 蓝色：保留建议或新写法。
- 背景保持干净，不做彩色海报。
- 图片中文字只允许使用 prompt 里列出的短词。

### 线条规则

- 红笔线要有手写抖动和真实批改感。
- 删除线、圈注、箭头可以不完美。
- 边注要短，不写长段话。
- 不要做成整齐 UI 或表格。
- 轻配图只画稿纸碎片，不画完整页面、完整检查清单或长段落。

### 适合的主体

- 红章操作员：适合“退回模板句”。
- 纸片工人：适合“整理修改后的稿纸”。
- 空心方盒：适合“把批改规则归档成 QA”。

### 禁止画法

- 不要满屏红字，保持可读。
- 不要像老师批改小学生作业。
- 不要做成恐吓或审判感。
- 不要伪造真实机构印章。
- 不要生成第三方文章的逐字批改，除非用户有授权。
- 不要自动扩写检查清单、标题或完整段落；只使用允许的短词。

### 示例 prompt

```text
Create a single horizontal 16:9 red-pen editing style illustration for a Chinese article.
Use a clean white manuscript page with blue-black draft text lines, hand-drawn red pen marks, circles, strike-throughs, arrows, and short margin notes. The image should look like a real human editing pass, not a polished infographic.

Original subject:
红章操作员, a small original red stamp operator with tiny feet and a strict calm face, not an official seal, not cute.

Topic:
去 AI 味不是把词换掉，而是把不属于自己的表达退回去。

Meaning:
Generic AI phrases should be rejected before publishing; only voice-matched phrases remain.

Scene:
On the left, a draft page contains bland phrases such as "赋能", "重塑", "综上所述", "爆款". Red pen marks circle and cross them out.
In the center, the red stamp operator marks "退回" on the worst phrase.
On the right, a small clean note keeps two short phrases: "先判断" and "说人话".

Short Chinese notes:
模板句 / 退回 / 先判断 / 说人话 / 可发布

Exact Chinese text allowed:
模板句 / 退回 / 先判断 / 说人话 / 可发布

Color:
Use blue-black for draft text, red for edits and rejection marks, and a small amount of blue for kept suggestions. Keep the page mostly white.

Avoid:
official seal imitation, school homework feeling, polished vector art, 3D rendering, glossy gradients, dense layout, commercial poster style, copied examples, third-party IP, and corner titles.
```

### QA 失败信号

- 看起来像整齐的信息图，而不是批改稿。
- 红色太多导致压迫感。
- 文字太小或太多。
- 自动生成了标题、长句或检查清单。
- 只有红笔，没有“保留/改好”的结果。
- 主体只是盖章，没有参与判断。
