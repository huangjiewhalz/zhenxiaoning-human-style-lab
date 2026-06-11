---
name: style-avatar-workshop
description: Build a reusable personal style asset Skill from the user's own works, preferences, anti-style notes, writing voice, content structures, visual taste, and optional original IP subject. Use when the user asks to make AI "write like me", reduce AI flavor, create a personal style clone/avatar, generate a style DNA pack, define a brand voice from authorized material, design a replaceable visual mascot/IP subject, turn a project/chat window into hand-drawn experiment-log images, or produce a personal style Skill. Do not use for generic Skill creation unrelated to personal style assets.
---

# 我的风格分身工坊

## 定位

帮助用户把自己的表达方式、审美偏好、内容结构、视觉符号和反风格清单，沉淀成一个可复用的个人风格资产 Skill。

核心不是“帮用户随便造 Skill”，而是解决一个具体痛点：让 AI 记住用户自己的风格，不要每次都从零猜，也不要输出默认 AI 味。

## 资源索引

- `references/intake-and-modes.md`：选择已有作品、空白起步、反风格起步、个人风格回归、视觉主体模式。
- `references/style-dna-schema.md`：个人风格 DNA 的提炼维度和证据写法。
- `references/starter-style-seeds.md`：用户没有作品时可用的原创风格种子。
- `references/ai-flavor-recovery-system.md`：把默认 AI 味诊断并修回用户本人风格的流程、知识卡片和编辑学习记录。
- `references/handdrawn-style-seeds.md`：反 AI 味手绘工具风格种子，包括默认铅笔草图风、蜡笔涂鸦风和红笔批改风。
- `references/visual-ip-system.md`：白底手绘解释图种子、可替换 IP 主体和构图规则。
- `references/layout-selection-engine.md`：根据用户上传内容自动选择布局、规划系列配图和沉淀避重规则。
- `references/presentation-carriers.md`：选择信息呈现载体，避免总是回到纸、笔、卡片和文件夹。
- `references/platform-image-sizes.md`：小红书、微信公众号、X、Instagram、竖屏短视频等自媒体平台的尺寸、比例、安全区和多平台重排规则。
- `references/model-runtime-requirements.md`：不同模型环境下的能力要求、降级模式和生图链路。
- `references/window-experiment-log.md`：彩蛋模式，把当前窗口、项目迭代或长对话整理成 3-5 张手绘实验日志图。
- `references/ip-subject-seeds.md`：用户没有角色图时可选的原创主体种子和示例 prompt。
- `references/skill-pack-template.md`：生成个人风格 Skill 文件夹时使用的文件结构和模板。
- `references/qa-checklist.md`：交付验收、漂移排查和自测规则。
- `references/compliance-boundaries.md`：合规边界、拒绝范围和改写方式。
- `assets/examples/subjects/`：原创候选主体小样，仅用于展示可替换主体方向，不作为固定复刻模板。
- `examples/`：展示案例和自测用的输入样例。

## 默认工作流

### 1. 识别用户入口

先判断用户属于哪种模式：

- **已有作品模式**：用户提供 3-10 个自有作品、链接、片段、截图或文件。
- **空白起步模式**：用户还没有稳定作品，需要先选择 1-2 个原创风格种子。
- **反风格起步模式**：用户只知道讨厌什么，例如“AI 味太重”“别像营销号”。
- **个人风格回归模式**：用户给出草稿、图片或系列内容，反馈“不像我”“AI 味重”“太模板”“太光滑”，需要诊断并修回用户本人风格。
- **视觉主体模式**：用户想要一个可替换的原创 IP 主体，用于配图、封面、脚本或 UI 解释图。没有角色图时，从 `ip-subject-seeds.md` 推荐 1-2 个候选主体；需要更强反 AI 味时，先从 `handdrawn-style-seeds.md` 选择手绘工具风格。
- **窗口实验日志模式**：用户要求“把当前窗口/这次对话/这个项目过程做成几张图”“一窗实验日志”“把这次打磨过程可视化”时，读取 `window-experiment-log.md`，把窗口里的起因、卡点、选择、结果和下一步整理成 3-5 张手绘连续图或生图 prompt。

如果信息不足，最多问 5 个问题，优先问会影响资产包质量的问题：使用场景、作品样本、讨厌风格、目标受众、是否需要视觉主体。

### 2. 建立证据地图

从用户材料中区分三类信息：

- **用户证据**：来自用户自己的作品或明确偏好。
- **合理推断**：由多个证据共同支持的风格判断。
- **待校准假设**：没有足够证据，但可作为第一版种子测试。

不要把待校准假设写成“用户真实风格”。每个重要风格判断都要能指出依据。

### 3. 生成风格资产

先按 `references/intake-and-modes.md` 判断入口模式，再按下面的模板引用链产出文件：

1. 读取 `references/style-dna-schema.md`，生成 `style-dna.md`：语气、节奏、结构、标题、判断方式、视觉审美、内容价值观。
2. 读取 `references/skill-pack-template.md` 的 `anti-style.md` 模板，生成 `anti-style.md`：禁用词、禁用句式、讨厌套路、禁止的 AI 味。
3. 读取 `references/skill-pack-template.md` 的 `content-patterns.md` 模板，生成 `content-patterns.md`：常用标题、开头、段落、结尾、脚本、配图结构。
4. 需要视觉风格时，读取 `references/visual-ip-system.md` 的 `visual-style-seed.md` 生成模板；如果用户强调去 AI 味或手绘感，再读取 `references/handdrawn-style-seeds.md`，生成 `visual-style-seed.md`。
5. 需要固定主体时，读取 `references/visual-ip-system.md` 的 `ip-subject.md` 模板，生成 `ip-subject.md`；如果用户上传或点名了角色，必须锁定该角色的识别点并用于后续配图，不得回退到默认主体；只有用户没有角色图和角色设定时，才读取 `references/ip-subject-seeds.md` 选择 1-2 个候选原创主体。
6. 需要视觉风格、连续配图、平台尺寸适配或布局避重时，读取 `references/layout-selection-engine.md`、`references/presentation-carriers.md`、`references/platform-image-sizes.md` 和 `references/visual-ip-system.md` 的构图规则，生成 `composition-patterns.md`。
7. 读取 `references/skill-pack-template.md` 的 `prompt-template.md` 模板，生成写作、标题、脚本、配图、UI 文案的复用提示词模板。
8. 读取 `references/skill-pack-template.md` 的 `qa-checklist.md` 模板，并结合 `references/qa-checklist.md`，生成可执行的 `qa-checklist.md`。
9. 用户强调去 AI 味、风格回归或长期校准时，读取 `references/ai-flavor-recovery-system.md`，生成 `ai-flavor-diagnostics.md`、`knowledge-cards.md` 和 `style-evolution-log.md`。
10. 用户要求把当前窗口、项目过程、对话迭代或 AI 实验过程做成图文复盘时，读取 `references/window-experiment-log.md` 和 `references/platform-image-sizes.md`，先生成实验卡、平台尺寸计划、布局规划表和中文短词白名单；有生图能力时再生成图片，没有生图能力时输出可复制 prompt。
11. 读取 `references/skill-pack-template.md` 里的正例和反例模板段落；必要时参考 `examples/blank-start-example.md` 和 `examples/existing-works-example.md` 的写法，生成正例文件和反例文件，只学习结构，不照抄内容。

### 4. 生成可安装 Skill

用户要求“直接写文件”“生成我的风格 Skill”“做成可复用 Skill”时，按 `references/skill-pack-template.md` 在当前 workspace 创建一个独立 Skill 文件夹。

写文件时：

- 文件夹名使用小写英文和连字符，例如 `my-style-avatar` 或用户指定 slug。
- `SKILL.md` 保持短，只写触发、流程、资源导航和边界。
- 细节全部放入 `references/` 和 `examples/`。
- 不覆盖同名文件夹；如果目标已存在，先说明冲突并换新 slug 或等待用户确认。
- 不生成 README、安装说明、长篇创作记录等无关文件。

### 5. 交付口径

交付时说明：

- 创建了哪个 Skill 文件夹。
- 哪些文件是核心资产。
- 当前版本基于用户证据还是风格种子。
- 哪些部分需要用户后续用真实作品校准。
- 如何用一句话触发该 Skill。

## 质量标准

- 钉子痛点必须清楚：让 AI 更稳定地像用户，而不是默认 AI 味。
- 不做泛 Skill Creator；所有输出都服务个人风格资产。
- 有作品时优先提炼真实证据；没作品时只给“风格种子”，不得冒充真实个人风格。
- 视觉风格可以把“白底、手绘、留白、少量批注、固定主体参与核心动作”作为可选工具语言，但默认目标是用户自己的风格资产；必须生成原创主体、原创构图和来自当前内容的新隐喻，不能复刻第三方 IP、公开案例物件组合或画面骨架。
- 视觉输出先自动判断密度档位、隐喻方式、构图尺度和留白偏好：轻配图、中密度解释图或高密度工作台；秒懂型、延迟型或系统型；局部轻描、小场景、完整场景或工作台；自动、留白多、平衡或内容更丰富。不确定时优先轻配图、延迟型隐喻和局部轻描；用户明确说“留白多一点”“更精致”“内容更丰富”“一张讲清楚”时，优先执行用户偏好。
- 密度差异必须是结构差异，不只是文字或纸片数量差异：轻配图是一个小局部里的日常动作关系，高密度是一个系统；连续配图要轮换纸片、卡片、日历、地图、控制台、对话、空间剖面和真实道具等信息承载物。
- 视觉隐喻先从日常动作出发，再选载体：这件事像“从被子下面找纸条”“把桌布一抖留下有用颗粒”“把太光滑的稿纸揉皱再贴补丁”“把同一张图塞进不同旧相框”中的哪一种动作关系。载体只作辅助，必须带隐喻方式、日常动作隐喻、遮挡关系、露出线索和视觉隐喻动作；低密度配图允许 2-4 个物件，但必须围绕一个清楚动作，不要变成道具摆拍、图标说明或靠文字解释。
- 如果必须使用场景，场景要粗糙、手作、不精致：允许线条歪、透视不准、边缘不整齐、物件像随手画出来；不要做精致房间、精致餐厅、精致 UI、商业海报、潮流大片或 3D 渲染。延迟型隐喻可以第一眼孤独、有留白，但第二眼必须能从物件关系里读出内容关系。
- 图片尺寸必须适配平台和位置：小红书、微信公众号、X、Instagram、竖屏短视频、PPT、论坛等不能默认都用 16:9。需要平台发布时先读取 `platform-image-sizes.md`，输出平台尺寸计划、比例、安全区和是否需要重排构图；同一内容多平台发布时优先生成横版、竖版、方版的同源多版，不把一张图简单裁切到所有平台。
- 窗口实验日志模式只提炼当前窗口的实验节点，不转写完整聊天记录，不暴露私密信息、密钥、未授权素材或第三方可识别风格。每张图只讲一个节点，默认 3-5 张，必须先给布局规划表和允许中文短词。
- 遇到流程卡点、素材复用、信息筛选、想法成型、经验沉淀、信任建立等常见抽象主题时，先读取 `layout-selection-engine.md` 的公开案例避让规则，再从用户自己的材料、行业场景、角色动作和平台语境里重新发明画面。
- 反风格清单要具体到词、句式、结构、画面套路和失败信号。
- 去 AI 味不是绕过检测器，而是识别默认 AI 痕迹后，用用户自己的风格证据、知识卡片和编辑反馈把内容拉回本人。
- QA checklist 必须可执行，能判断“像不像用户”和“哪里漂了”。
- Skill 本体保持模型无关；用户要求生成图片时，必须先判断当前环境是否有生图能力。没有生图能力时，先明确提示“当前模型/环境不能直接生成图片”，再按 `model-runtime-requirements.md` 降级为文本资产、布局计划和可复制的生图 prompt 输出。

## 合规边界

默认只处理用户自己的作品、用户明确授权的品牌资料，或抽象风格方向。

拒绝帮助用户复刻名人、在世创作者、同事、博主、画师、设计师等可识别个人风格；拒绝伪装成他人发言；拒绝抓取第三方内容制作风格分身。

如果用户要求模仿第三方，把任务改写为抽象风格方向，例如“更克制、更短句、更纪实、更少营销感”，并读取 `references/compliance-boundaries.md`。
