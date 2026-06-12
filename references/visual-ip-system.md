# Visual IP System

用于生成 `visual-style-seed.md`、`ip-subject.md`、`composition-patterns.md` 和视觉 prompt 模板。

需要根据用户上传内容自动选择布局、规划连续配图或避免构图重复时，先读取 `layout-selection-engine.md`，再回到本文件套用主体和 prompt 模板。

需要适配小红书、微信公众号、X、Instagram、竖屏短视频、PPT、论坛或用户指定尺寸时，先读取 `platform-image-sizes.md`，把尺寸、比例、安全区和重排规则写进视觉 prompt。不要把默认 16:9 构图直接裁成其他比例。

如果用户想要更强的反 AI 味，先读取 `handdrawn-style-seeds.md` 选择具体手绘工具风格。默认用铅笔草图风；需要更温暖、更个人 IP 时用蜡笔涂鸦风；需要诊断、批改或反风格清单时用红笔批改风。再套用本文件的主体和构图规则。

## 核心边界

可以借鉴的抽象结构：

- 白底。
- 手绘线稿。
- 留白。
- 少量中文批注。
- 固定原创主体参与核心动作。
- 用低科技、物理化隐喻解释抽象观点。

不能复刻的东西：

- 第三方角色名、外形、案例构图、作品样例。
- 在世创作者、画师、博主、品牌的可识别风格。
- “换个主体但保留原 IP 识别点”的换皮。
- 把公开案例里的标志性物件组合、主体动作或画面节奏当默认模板。

## 主体锁定优先级

连续配图先锁定主体，再设计动作和隐喻。主体锁定优先级如下：

1. **用户上传的角色图**：最高优先级。保留颜色、体型、五官、标志部件和比例，再转换为手绘风格。短期任务可以直接使用当前对话上传图；长期复用时，提醒用户把授权角色图放到 `assets/references/characters/<subject-slug>-reference.png`，并在 `ip-subject.md` 记录参考图路径。
2. **用户点名的自有角色**：按用户给出的名字、文字设定或固定参考图锁定外形，不读取默认主体种子。
3. **无角色图、无角色名、无文字设定**：才允许读取 `ip-subject-seeds.md`，推荐候选主体。

一组连续配图只能使用一个主视觉主体。不得在同一组图里混用空心方盒、线团人、红章操作员、墨点操作员、纸片工人等多个默认主体。默认主体种子只用于“没有用户主体”的起步方案，不得替代用户上传或点名的角色。

## 角色参考图落位

固定角色参考图放在 `assets/references/characters/`。

- 用户自己的 IP：建议命名为 `assets/references/characters/<subject-slug>-reference.png` 或 `.jpg`。
- 只放用户自己的原创角色、用户明确授权的品牌/项目角色，或用户有权使用的素材。
- 不放第三方 IP、名人形象、在世创作者可识别角色、未授权品牌角色，也不把第三方角色改色当作用户 IP。
- 每放入一张长期参考图，都要生成或更新 `ip-subject.md`：写明参考图路径、来源授权、识别点、禁改点、动作库、常见道具和连续配图一致性规则。
- 如果用户只是一次性测试，不必要求他改文件；直接使用当前对话上传图，并提醒“要长期复用时再放入固定目录”。

## 画面密度档位

默认自动选择密度，不让用户先选菜单。不确定时优先轻配图；如果内容既适合正文配图又适合深度拆解，可以给“轻配图 / 中密度解释图 / 高密度工作台”三种方案供用户取舍。

| 档位 | 适用场景 | 核心意思 | 中文标注 | 信息承载物 | 箭头/连线 | 留白 |
| --- | --- | --- | --- | --- | --- | --- |
| 轻配图 | 正文配图、小红书图、产品介绍、用户只想清爽去 AI 味 | 1 个核心动作 | 2-4 个 | 1-3 个 | 0-1 条 | 至少 55% |
| 中密度解释图 | 功能说明、教程步骤、案例拆解、单张讲清一个小机制 | 1 个主场景 + 2 个信息区 | 4-6 个 | 4-7 个 | 1-2 条 | 至少 35% |
| 高密度工作台 | 方法论、复盘、课程讲义、PPT、无限画布、用户明确要“一张图讲清楚” | 3 个清晰分区 | 8-12 个 | 12-20 个 | 3-6 条 | 至少 15% |

高密度不是默认值。只有用户明确要完整拆解、复盘、画布、课程讲义、PPT 或“一张图讲清楚”时才使用。

生成前先写：

- 本图密度：轻配图 / 中密度解释图 / 高密度工作台。
- 选择理由：基于平台、材料复杂度、用户目标。
- 本图只画什么：一句话限定核心动作。

如果内容超出当前档位预算，优先拆成系列图，不要硬塞进单张图。

密度差异要能从缩略图看出来：轻配图是一个小局部里的生活动作，高密度是一个系统，中密度是一个机制。不要只靠增加纸片、卡片或文字数量来假装升密度。

## 构图尺度和留白

轻配图默认使用“局部轻描”，不是完整场景。画面保留一个小局部、一个主体动作、2-4 个参与动作的物件和一个露出的结果，像文章旁边的小呼吸图。

- 轻配图主体群建议占画布宽度 30%-45%、高度 25%-40%，四周保留至少 25% 空白安全边。
- 如果用户反馈“太满”“留白太少”“不精致”，主体群缩到画布宽度 30%-40%、高度 25%-35%，四周安全边至少 30%。
- 如果用户明确要“留白多一点”，主体群缩到画布宽度 25%-38%、高度 20%-32%，四周安全边至少 35%，中文批注 1-3 个。
- 如果用户明确要“内容更丰富”，可以升到中密度或高密度，但必须先安排分区和阅读路径，不能只是放大主体、增加纸片或堆更多批注。
- 批注是小手写注，不是标题。不要让红字、箭头或标签成为画面里最大的视觉元素。
- 图片中文字必须来自 prompt 里的短词白名单，不自动新增解释句、标题或检查清单。
- 新颖载体也要能动作化：收音调频可以画手指把噪声旋钮拧到清晰刻度，裁缝试衣可以画一块布样被粗线缝回边角，暗房显影可以画照片从水里露出一点轮廓，小店货架可以画价签被掀开露出真实卖点。
- 只有用户明确要“完整场景”“一张图讲清楚”“无限画布”“PPT 工作台”时，才扩展成完整空间或多区块工作台。
- 低密度必须先选日常动作隐喻，例如掀开、摸索、拖出来、按住、贴胶带、晾干、揉纸、夹住、蹲下找、抖落、捞出、撕开、拼回去。
- 如果使用场景，场景要粗糙、手作、不精致：允许歪线、轻微透视错误、粗糙边缘和草稿阴影；禁止精致房间、精致餐厅、精致 UI、商业海报、潮流大片和 3D 渲染。

## visual-style-seed.md 生成模板

```markdown
# Visual Style Seed

## 一句话视觉方向

用一句可执行的话定义画面气质，例如“白底手绘解释图，像在草稿纸上把复杂想法拆成可操作的小现场”。

## 适用场景

- 正文配图：
- 平台尺寸：
- 产品解释：
- 脚本分镜：
- UI 空状态：
- 不适用场景：

## 手绘工具质感

- 主工具：
- 线条：
- 填色：
- 纸面/留白：
- 批注颜色：
- 允许的不完美：

如果用户要求更强去 AI 味，先读取 `handdrawn-style-seeds.md`，选择一个具体工具风格后再填写本节。

## 画面原则

- 每张图只讲一个核心意思。
- 用户上传或点名角色时，必须使用该角色作为主视觉主体；先保留颜色、体型、五官、标志部件和比例，再转换手绘画风。
- 用户上传或点名角色时，必须使用该角色；不得替换成空心方盒、线团人、红章操作员、墨点操作员或纸片工人。
- 已有用户角色时，不使用 `ip-subject-seeds.md` 的默认主体，也不把默认主体改色冒充用户角色。
- 连续配图必须使用同一个主体，只变化动作、角度、道具和构图，不变化角色物种或主体类型。
- 主体必须参与核心动作，不做角落装饰。
- 保留明显留白，不画满。
- 正文配图和轻配图优先局部轻描：主体群缩小，外圈白边清楚，不画完整场景。
- 中文标注短而少，优先像手写批注，不像标题排版。
- 低科技、物理化、现场化表达抽象概念。
- 根据用途选择隐喻方式：正文配图优先延迟型，教程/功能说明优先秒懂型，方法论/复盘优先系统型。
- 低密度优先用一个小局部里的动作关系代替完整场景；中密度才允许粗糙小场景；高密度才允许工作台或完整系统。
- 平台尺寸是构图输入，不是最后裁切：小红书竖图用上中下结构，公众号头图守住中心方形安全区，X/正文横图用横向阅读路径，9:16 竖屏避开顶部和底部 UI 遮挡。

## 色彩范围

- 主色：
- 辅色：
- 批注色：
- 禁用色彩：

## 信息密度

- 默认档位：轻配图。
- 可选档位：轻配图 / 中密度解释图 / 高密度工作台。
- 自动选择依据：平台、发布位置、目标尺寸、材料复杂度、是否教程/复盘/画布、用户是否要求“一张图讲清楚”。
- 平台尺寸：读取 `platform-image-sizes.md` 后填写推荐尺寸、比例和安全区；没有平台时默认 16:9 通用正文配图。
- 多平台策略：优先横版、竖版、方版同源多版，不把一张图裁切到所有平台。
- 留白偏好：自动 / 留白多 / 平衡 / 内容更丰富。用户没说时自动判断；用户明确表达留白或信息量偏好时优先执行。
- 轻配图尺度：主体群占画布宽度 30%-45%、高度 25%-40%，四周至少 25% 空白安全边；用户反馈太满时进一步缩小到宽度 30%-40%、高度 25%-35%。
- 禁止出现：未说明密度档位就堆满信息；把所有诊断点同时上画面；高密度却没有清晰分区；低密度和高密度缩略图看起来只是文字多少不同。

## 和文字风格的关系

视觉图不是重复标题，而是把文章里的一个判断、动作、冲突或转变画出来。

- 文章偏判断：画“判断发生的动作”。
- 文章偏教程：画“用户正在完成的步骤”。
- 文章偏产品介绍：画“功能解决问题的现场”。
- 文章偏复盘：画“证据、时间或版本如何被整理”。

## 禁止画法

- 不做商业矢量插画。
- 不做 PPT 架构图。
- 不做儿童卡通。
- 不做赛博、霓虹、3D 光滑质感，除非用户明确要求。
- 不复刻第三方 IP、公开案例物件组合、在世创作者可识别风格。
- 不把同一个左中右流程布局连续套用到整组图片。

## 待校准假设

记录证据不足但可以测试的视觉判断。
```

## IP 主体定义模板

```markdown
# IP Subject

## 来源

用户上传角色 / 固定参考图 / 用户文字设定 / 原创主体种子

## 参考图路径

- 短期上传图：
- 长期固定图：`assets/references/characters/<subject-slug>-reference.png`
- 授权说明：用户原创 / 用户授权品牌资料 / 待确认

## 识别点锁定

列出必须保留的颜色、体型、五官、标志部件、比例、表情气质和禁改点。

## 名字

## 一句话定义

## 外形

## 性格

## 核心职责

## 动作库

## 常见道具

## 禁止画法

## 参与核心动作的判断标准
```

## 可选原创主体种子

完整种子、适用场景和示例 prompt 见 `ip-subject-seeds.md`。本节只保留快速选择摘要。

### 墨点操作员

- 外形：不规则墨迹、印痕或水滴状小主体；眼睛可用短横线、空心小孔或单个缺口表达；四肢可用细线支架、夹子或小脚架表达。
- 性格：冷静、认真、笨拙，不卖萌。
- 适合：知识型内容、系统解释、AI 工作流。
- 动作：搬、塞、挡、压、拉、标记、守门。
- 禁止：不要使用第三方角色名；不要使用“黑色实心小怪物 + 白点眼 + 细腿”的完整组合；不要复用第三方案例构图。

### 纸片工人

- 外形：折起来的一张纸，有简笔眼睛和细线手脚。
- 性格：像认真整理文档的临时工。
- 适合：写作、笔记、知识库、文档生产。
- 动作：折叠、归档、盖章、递纸、贴标签。

### 红章操作员

- 外形：一个小红印章或印泥块，有细腿。
- 性格：严谨、判断直接、有一点冷幽默。
- 适合：审核、判断、观点、反风格清单。
- 动作：盖章、否决、标红、压住废话、确认边界。

### 线团人

- 外形：由一团黑线组成，有两只小眼睛。
- 性格：从混乱里找线索。
- 适合：流程、关系、信息过载、从乱到清晰。
- 动作：解线、穿针、拉路径、打结、剪断。

### 空心方盒

- 外形：一个手绘空心盒子，有眼睛和细腿。
- 性格：像产品系统里的小容器。
- 适合：产品、工具、模块、UI、组件化表达。
- 动作：装入、吐出、分类、打开、嵌套。

## 构图模式

一次只用一种结构。完整布局库、自动选择流程和系列规划规则见 `layout-selection-engine.md`；本节只保留核心模式摘要。

同一系列连续配图时，不能连续 2 张以上使用“左侧输入 -> 中间主体 -> 右侧输出卡片”的横向流程排布。每张图先选一个不同的空间隐喻，再安排主体动作。优先让主体位置、视角、道具和信息承载方式发生变化，而不是只替换标签。

遇到流程卡点、素材复用、信息筛选、想法成型、经验沉淀、信任建立等常见抽象主题时，先按 `layout-selection-engine.md` 的公开案例避让规则重构画面。不要只把公开案例里的物件换成新主体；要从用户自己的材料里重新选择空间关系、主体动作和信息承载物。

### 输入到输出

适合：把作品沉淀成风格资产、把原始想法变成内容。

画法：左侧输入，中间主体操作一个低科技装置，右侧输出。箭头少，文字短。

### 前后对比

适合：默认 AI 味 vs 像用户、混乱素材 vs 风格资产。

画法：左侧混乱，右侧稳定，中间由主体完成转换动作。

### 反风格拦截

适合：禁用词、营销味、标题党、过度总结腔。

画法：主体守在入口，挡住废话云、模板盒或红色警示牌。

### 资产工具箱

适合：展示 style DNA、anti-style、patterns、QA 等文件。

画法：一个打开的盒子或抽屉，主体在整理卡片，不要画成正式文件树截图。

### 小漫画分镜

适合：从“AI 不像我”到“逐步校准”的故事。

画法：2-4 格，每格一个动作。少字。

### 俯视桌面

适合：证据整理、文书草稿、清单核对、素材归类。

画法：像从桌面上方看，主体只露出手、角或半个身体，核心信息散落在纸张、便签、证据袋、夹子和笔之间。不要再做左中右流程排布。

### 剖面盒子

适合：解释 App 内部流程、云端同步、数据保护、工具模块。

画法：把一个盒子、云朵、生态舱或抽屉画成剖面，主体在内部移动卡片或修理部件。信息上下分层，而不是横向排队。

### 地图路线

适合：连续步骤、用户路径、从混乱到下一步。

画法：把流程画成弯曲路线、楼层、格子地图或脚印路径，主体沿路线移动。避免直线箭头串卡片。

### 特写动作

适合：强调一个关键动作，例如按下录音、盖章、锁住证据、圈出异常。

画法：画面聚焦主体的手、道具和一个结果，不追求全流程展示。留白更大，文字更少。

## 避重规则

- 一组 3 张以上连续配图，至少使用 3 种构图模式。
- 如果上一张使用左中右流程，下一张优先改用俯视桌面、剖面盒子、地图路线、特写动作或小漫画分镜。
- 道具不要重复：不要每张都用“箱子 + 三张卡片”。可换成证据袋、桌面、夹板、图鉴墙、云朵保险箱、控制台、路线图、放大镜、录音按钮。
- 信息承载物不要重复：卡片、便签、图鉴格、表格、清单、印章、抽屉、地图节点要轮换。
- 纸片、卡片、便签、文件夹属于同一承载物家族。连续两张不能都主要靠这类物件承载信息；下一张要换成日历、地图、控制台、对话、空间剖面、真实道具或局部特写。
- 主体位置要轮换：居中、侧边、俯视只露手、局部特写、走在路线中、站在盒子内部。
- 同一表达任务不要沿用公开案例的物件组合或画面骨架；先换成来自用户材料的新空间关系和动作，再写 scene plan。
- 如果缩略图缩略图看起来只是“换了文字的同一张图”，判定为失败，重写 scene plan。

## Prompt 模板

```text
Create a single illustration for a Chinese article, composed natively for the target platform size and aspect ratio. If no platform or size is specified, use a horizontal 16:9 composition.

Art direction:
Use a clean white canvas, loose black sketch lines, quiet spacing, and a few short handwritten Chinese notes in red, orange, or blue. The image should feel like a rough thinking sketch for a product/content idea, not a slide, poster, polished vector graphic, UI screen, or children's cartoon.

Original recurring subject:
{主体名字}: {外形}. Temperament: {性格}. The subject must be responsible for the main action that explains the idea.

Topic:
{主题}

Meaning to show:
{核心意思}

Scene plan:
{主体的位置、动作、道具、输入输出关系、视觉动线}

Density tier:
{轻配图 / 中密度解释图 / 高密度工作台}. Follow the selected density budget from this file. If no density is specified, use 轻配图.

Whitespace preference:
{自动 / 留白多 / 平衡 / 内容更丰富}. If the user does not specify, choose automatically from the content. If 留白多, shrink the main cluster to 25%-38% of canvas width and 20%-32% of canvas height, keep at least 35% blank margin on all sides, and use only 1-3 short handwritten notes. If 内容更丰富, use medium or high density only when the content requires it, with clear sections and a reading path.

Presentation carrier:
{基础或新颖载体，见 presentation-carriers.md。例如：纸面文具 / 时间记录 / 操作面板 / 路线地图 / 空间剖面 / 对话现场 / 样本图鉴 / 实验检测 / 票据档案 / 舞台展示 / 工具修理 / 生活实物 / 微型街区 / 地铁换乘 / 暗房显影 / 收音调频 / 邮局分拣 / 裁缝试衣 / 厨房备料 / 博物馆展柜 / 舞台后台 / 天气观测 / 沙盘推演 / 小店货架 / 维修工位 / 观测星图}. Use this carrier as the place where the everyday action happens. Do not default to paper cards, sticky notes, folders, timelines, UI panels, or pencils unless the action needs them.

Metaphor mode:
{秒懂型 / 延迟型 / 系统型}. Use 延迟型 for normal article illustrations, 秒懂型 for tutorials/product explanations/platform sizing, and 系统型 for methodology/review/canvas images.

Everyday action metaphor:
{低密度必须填写一个生活动作，例如从被子下面摸出纸条 / 掀开卡纸露出线索 / 抖旧桌布留下有用颗粒 / 揉皱太光滑的稿纸再贴补丁 / 把图塞进不同旧相框 / 胶带贴住吵闹红点。}

Occlusion relationship:
{谁盖住、压住、夹住、藏住或挡住了什么。没有遮挡时写清处理关系。}

Revealed clue:
{少量露出的线索，例如皱纸条一角、杯底字迹、旧日期标签、被贴住红点旁边的小纸条。}

Roughness rule:
Use rough hand-drawn staging: imperfect lines, uneven perspective, slightly crooked objects, visible sketch marks, and unpolished edges. Avoid polished rooms, polished restaurants, clean UI mockups, commercial posters, glossy 3D rendering, and highly finished illustration.

Framing scale:
{局部轻描 / 小场景 / 完整场景 / 工作台}. For 轻配图, default to 局部轻描: one small action cluster with 2-4 objects and one occlusion/reveal/process relationship, not a complete room, street, shop, dashboard, or workbench. Keep the cluster at 30%-45% of canvas width and 25%-40% of canvas height, with at least 25% blank margin on all sides. If the user complained about crowded edges, shrink the cluster to 30%-40% width and 25%-35% height, with at least 30% blank margin.

Series variety:
If this is part of a series, state which composition mode is used and how it differs from the previous images. Avoid repeating left-input / center-character / right-output cards unless this is the first image or there is a strong reason.

Short Chinese notes:
{按密度档位填写：轻配图 2-4 个；中密度解释图 4-6 个；高密度工作台 8-12 个}

Exact Chinese text allowed:
{列出允许出现在图里的所有中文短词。生成图不得新增解释句、标题、段落、检查清单或未列出的中文。}

Hard limits:
Follow the selected density tier. 轻配图 must stay sparse and leave at least 45%-55% white space; show one everyday action relationship with 2-4 objects, not an overview and not a static prop arrangement. For 轻配图, keep the subject/object cluster visibly smaller than the canvas, avoid edge-to-edge composition, and make handwritten notes small annotations rather than titles. All visible Chinese text must be short and must come only from the exact allowed text list; do not invent headlines, explanatory sentences, paragraph text, checklist items, or extra labels. 中密度解释图 must have two clear information zones at most and leave at least 35% white space; it may use a rough small scene, but the scene must be driven by the action, not by card stacking, and must not be a polished full room, full shop, full station, full restaurant, or full workbench. 高密度工作台 may contain more material, but must have three clear sections, a main reading path, and at least 15% white space; keep the scene rough and hand-drawn, not commercial or glossy. Do not draw every diagnostic point unless the selected tier is 高密度工作台 and the user asked for a workbench, canvas, review, lesson, PPT, or one-image overview. Do not make density differ only by adding paper cards or handwritten labels. The presentation carrier must be visible through props, action, occlusion, revealed clues, and spacing, not through explanatory text. If the framing scale is 局部轻描, use a daily action such as lifting a blanket corner, pulling a note from under cardboard, taping down a noisy red dot, shaking an old tablecloth, wrinkling a too-smooth draft, fitting a picture into mismatched frames, or fishing a clue from a cup bottom. Avoid polished interiors, polished restaurants, clean UI mockups, commercial posters, glossy 3D rendering, top-left category titles, structure labels, chaotic dense arrows, repeated left-to-right pipeline layouts, repeated paper/card/folder/timeline carrier families across adjacent series images, copied examples, public-case metaphor templates, third-party IP, recognizable living-artist styles, and any mascot-like copy of another character.
```

## QA 判断

如果去掉主体，画面仍然完全成立，主体就是装饰，需要重写构图。

如果第一眼像 PPT、课程页、架构图、儿童卡通或商业插画，不合格。

如果选择的是轻配图或中密度解释图，但第一眼像资料墙、便签墙、复杂关系网，或者需要放大才能看懂，判定为信息过密，需要降密度或拆成系列图。高密度工作台也必须有清晰分区和主阅读路径。

如果选择的是轻配图，但主体群铺得太大、贴近画面边缘、四周没有明显白边，或红字批注像标题一样抢眼，判定为尺度失败，需要缩小主体群并改成局部轻描。

如果生成图出现 prompt 未列出的中文、长句、标题化红字、段落或检查清单，判定为文字漂移，需要重写 prompt 并使用 `Exact Chinese text allowed` 白名单。

如果轻配图和高密度工作台缩略图看起来差不多，只是后者多了几张纸或多几个标签，判定为密度失败，需要把轻配图改成单动作特写，或把高密度改成有分区的工作台。

如果同一系列里连续多张都是“左边混乱输入、中间主体、右边输出卡片”，不合格。

如果一组图里角色总是在拿笔、圈纸、贴便签，判定为呈现载体过窄；读取 `presentation-carriers.md` 后重写为操作面板、路线地图、对话现场、时间记录、空间剖面或样本图鉴等载体。

如果只是把公开案例里的标志性物件换成自己的角色，而空间关系、动作和信息承载方式没变，不合格。

如果主体和第三方角色只有名字不同，但外形和动作识别点很像，不合格。
