# Visual IP System

用于生成 `visual-style-seed.md`、`ip-subject.md`、`composition-patterns.md` 和视觉 prompt 模板。

需要根据用户上传内容自动选择布局、规划连续配图或避免构图重复时，先读取 `layout-selection-engine.md`，再回到本文件套用主体和 prompt 模板。

需要适配小红书、微信公众号、X、Instagram、竖屏短视频、PPT、论坛或用户指定尺寸时，先读取 `platform-image-sizes.md`，把尺寸、比例、安全区和重排规则写进视觉 prompt。不要把默认 16:9 构图直接裁成其他比例。

如果用户想要更强的反 AI 味，先读取 `handdrawn-style-seeds.md` 选择具体手绘工具风格。默认用白底彩铅草稿风；需要更克制、更清爽、更像思考草稿时用铅笔草图风；需要诊断、批改或反风格清单时用红笔批改风；用户明确要求“虚实结合、实物拼贴、真实工作台、照片物件 + 手绘角色”时，才使用实物拼贴手绘风；用户明确要求“抽象镇小宁、随手画、涂鸦、乱线彩铅、像真人但不是肖像、更艺术的镇小宁”时，才使用抽象镇小宁涂鸦风。再套用本文件的主体和构图规则。若本机存在 `references/style-reference.local.md`，先读取它锁定默认风格参考。

## 核心边界

可以借鉴的抽象结构：

- 白底。
- 手绘线稿。
- 留白。
- 少量中文批注。
- 固定原创主体参与核心动作。
- 用低科技、物理化隐喻解释抽象观点。
- 可选实物拼贴：用真实物件搭工作现场，再叠加手绘角色和短批注。正文轻配图可以少量物件；自我介绍、能力展示或多风格对比时，虚实结合应使用更多真实场景品种，而不是增加物件数量。
- 可选抽象镇小宁变体：用乱线彩铅、涂出边和幼拙比例表现镇小宁的人味、情绪和艺术感，但仍保留固定 IP 识别点。
- 抽象镇小宁变体中的场景也必须抽象手绘化：道具、纸张、线缆、桌角、工具和信息载体要和角色共享同一乱线彩铅/蜡笔草稿画风。
- 背景统一白纸底：白底彩铅、抽象镇小宁、虚实结合和常规手绘正文图必须使用同一个白纸底系统。纯白和很浅的纸白 / 浅纸色都可以，但同一篇 / 同一组图必须锁定一种；抽象风不得单独改成明显奶油黄、旧纸、暗角或粗纸纹；虚实结合不得单独漂成灰棚、商业摄影棚或另一套底色。粗糙感来自线条、角色、道具和涂痕，不靠换底色制造差异。

不能复刻的东西：

- 第三方角色名、外形、案例构图、作品样例。
- 在世创作者、画师、博主、品牌的可识别风格。
- “换个主体但保留原 IP 识别点”的换皮。
- 把公开案例里的标志性物件组合、主体动作或画面节奏当默认模板。
- 把实物拼贴做成商业产品广告、真实 UI 截图、stock photo 或品牌样机图。
- 把“像真人”误解成真人肖像、拟真人头像、自拍、职业照或半身人像；抽象镇小宁只能更有人味和艺术感，不能替换成真人。

## 主体锁定优先级

连续配图先锁定主体，再设计动作和隐喻。主体锁定优先级如下：

1. **当前对话上传的角色图**：最高优先级。保留颜色、体型、五官、标志部件和比例，再转换为蜡笔或其他手绘风格。只要用户本轮上传了角色图，就不得自动改用 `assets/references/characters/` 里的其他图片，即使目录里存在旧参考图。
2. **本机私有默认角色绑定**：如果存在 `references/ip-subject.local.md`，且其中写明默认角色名、参考图路径、授权说明和“允许本机默认使用”，则它属于第一梯队。创作者本人本机使用时，可以把这个私有角色作为默认主体；普通公开仓库不应包含这个文件。
3. **用户明确指定的固定参考图路径**：只有用户明确说“使用 `assets/references/characters/<subject-slug>-reference.png`”或给出等价路径时，才读取该固定图。
4. **`ip-subject.md` 绑定的固定参考图**：只有 `ip-subject.md` 明确写了当前角色名、参考图路径和授权来源，且用户没有在本轮上传新角色图、也没有本机私有默认角色绑定时，才使用该路径。
5. **用户点名的自有角色或文字设定**：按用户给出的名字、文字设定锁定外形，不读取默认主体种子，也不扫描参考图目录。
6. **无角色图、无角色名、无私有默认绑定、无文字设定**：才允许读取 `ip-subject-seeds.md`，推荐候选主体。

一组连续配图只能使用一个主视觉主体。不得在同一组图里混用空心方盒、线团人、红章操作员、墨点操作员、纸片工人等多个默认主体。默认主体种子只用于“没有用户主体”的起步方案，不得替代用户上传或点名的角色。

如果 `assets/references/characters/` 里存在与当前用户上传图不同的旧图、示例图或私有项目图，默认忽略。不要根据文件名、修改时间或图片存在性自动选择目录里的角色；无法确认当前角色和目录参考图是否一致时，先使用当前上传图，或向用户确认。

## 固定 IP 参考图执行规则

固定 IP 成稿不能只靠文字 prompt。只要使用当前对话上传图、本机私有默认角色绑定、用户指定路径或 `ip-subject.md` 绑定的角色，最终成稿应把对应参考图作为实际图像参考输入或图像编辑输入。但在本机快速测试、自我介绍展示或方向预览中，如果当前生图工具只能文本生图，可以先生成绑定角色方向预览图，前提是必须明确它不是最终 IP 一致性成稿，并进行角色漂移 QA。

抽象镇小宁固定风格已有唯一母版时，不走普通文本生图方向预览逻辑。当前工具不能接入母版图时，多风格对比、风格选择或小图测试直接展示/引用母版图作为抽象风格小图；如果聊天环境不能展示本地图片，则要求用户把母版图上传到当前对话或换支持参考图/图像编辑的工具。不要把文本生图生成的普通蓝色卡通交付为抽象镇小宁。

- 生成前先确认参考图来源：当前上传图 / `ip-subject.local.md` 路径 / 用户指定路径 / `ip-subject.md` 路径。
- 生成前确认参考图文件存在；如果路径不存在，先提示缺失，不要凭文字描述补画。
- 如果当前生图工具支持参考图输入或图像编辑，必须使用参考图作为 identity source，再把动作、道具、布局和白底彩铅草稿风作为变换要求。
- 如果当前生图工具只支持文本到图像，不能传入参考图，但任务是本机快速测试、自我介绍展示或方向预览，可以主动生成绑定角色方向预览图；生成前写明这是方向预览，不是最终固定 IP 成稿。
- 如果用户明确要求“最终成稿 / 严格一致 / 官方发布 / 固定 IP 不能跑偏”，且当前生图工具不能传入参考图，先说明：`当前生图工具不能接入角色参考图，只靠文字会画成相似角色，不能保证是你的固定 IP。请在当前对话上传角色图，或换用支持参考图/图像编辑的生图工具。`
- 方向预览图也必须以镇小宁为主角，不得画真人肖像、普通人物照片、抽象人像、无角色图、线团人、空心方盒或普通蓝色吉祥物。
- prompt 里可以写识别点，但识别点只是辅助，不替代参考图输入。

抽象镇小宁唯一母版执行规则：

- 如果 `ip-subject.local.md`、`ip-subject.md` 或用户当前上传材料绑定了抽象镇小宁唯一母版，生成抽象镇小宁时必须固定使用这张母版，而不是只靠文字描述生成，也不是从多张抽象图里随机选择。
- 角色小样、头像、表情、近景风格实验、正文配图、通用展示或工作流图，都使用同一张唯一母版锁定脸型、耳朵结构、眼距、红鼻位置、白肚皮比例和乱线密度。
- 连续图全组使用同一张唯一母版，只变化动作、表情、视角、道具和构图，不更换抽象版本。
- 当前工具支持参考图输入或图像编辑时，必须把这张唯一母版作为实际图像输入、identity source 或 style source。
- 当前工具只能文本生图时，不生成新的抽象镇小宁角色。多风格对比、风格选择或小图测试中，直接展示/引用唯一母版作为抽象风格小图；如果聊天环境不能展示本地图片，则说明需要上传母版图或换支持参考图/图像编辑的工具。只有用户明确接受“无母版输入的松散方向预览”，才可文本生图尝试，且不得声称已复用了唯一母版，也不得交付为最终 IP 一致性成稿。
- 使用抽象镇小宁时，整张图都按母版的抽象草稿语言延展。场景和道具不得写实化；如果旁边出现照片级桌面、真实物件、产品样机、真实 UI 或摄影棚阴影，即使角色像，也判定为画风割裂。

固定 IP 合格标准：第一眼能对应参考图的物种、轮廓、五官比例、颜色分布和标志部件；不是“蓝色、红鼻子、黄耳朵所以差不多”。方向预览图低于这个标准时，不要交付为成稿，只能重试或提示需要参考图输入。

## 私有默认角色方向预览硬约束

当本机私有默认角色绑定生效，但当前生图工具不能接入本地参考图时，可以为本机快速测试、自我介绍展示或方向预览主动生成图片。此时必须同时满足：

- 交付说明写明：`方向预览，非最终 IP 一致性成稿`；不得把方向预览称为正式 IP 成稿、官方图或严格一致版本。
- prompt 必须声明：使用本机私有绑定的角色作为主视觉主体；如果该角色是镇小宁，则保留蓝色圆润小兽、白色肚皮、红色圆鼻子、两只大白眼和黑色瞳孔、黄色眉毛、头顶两根黄色长耳/触角、两侧尖耳和蓬松侧边轮廓、短胖圆润四肢。
- prompt 必须声明：不画真人肖像，不画拟真人头像，不画普通人物照片，不画抽象人像，不画无角色图，不画线团人，不画空心方盒，不画普通蓝色角色，不画通用蓝色吉祥物。
- “更像你自己”只指表达风格、结构节奏、判断方式和视觉偏好更像用户；不得解释成画用户真人、自拍、半身像、职业照或拟真人角色。
- 如果用户要求“更像真人 / 更有人味 / 更艺术”的抽象镇小宁，只能理解为表情、姿态、手绘不完美和情绪张力更像人；不得把镇小宁替换成真人脸、人类头像或写实人物。
- 默认画风读取本机 `references/style-reference.local.md`：白底彩铅草稿风、彩铅颗粒、松弛铅笔线、明显留白、短中文手写批注；不要退回商业矢量、低幼贴纸、3D 渲染或光滑 mascot 海报。
- 生成后做角色漂移 QA：如果成图变成人像、无角色图、线团人、空心方盒、普通蓝色角色或其他主体，先重试并强化识别点；重试后仍失败，则要求用户上传对应角色参考图或换支持参考图/图像编辑的生图工具。

## 点名角色但缺少参考图

用户说“镇小宁形象”“镇小宁 IP”“我的 IP 形象”“用这个角色”“用某某角色”时，视为已经点名具体角色。此时：

- 不得读取 `ip-subject-seeds.md`。
- 不得使用线团人、空心方盒、红章操作员、墨点操作员、纸片工人等默认主体顶替。
- 不得把默认主体改成相近颜色来冒充该角色。
- 如果存在 `references/ip-subject.local.md`，且它明确绑定了被点名角色并允许本机默认使用，优先使用该私有绑定，不要再要求上传。
- 如果没有当前上传图、本机私有绑定、固定参考图路径或 `ip-subject.md` 绑定，先输出一句明确限制：`当前没有可用的 <角色名> 参考图，不能用默认主体代替。请上传角色图或指定参考图路径；在此之前我只能先做文案、布局规划和不含具体角色的 prompt。`
- 如果用户只是说“镇小宁风格实验室”这个 Skill 名，没有说“镇小宁形象 / IP / 角色”，公开通用环境里不要误判为要求使用镇小宁角色；但在创作者本人本机环境里，如果 `ip-subject.local.md` 明确写了“无其他角色时默认使用镇小宁”，则可以按该文件执行。
- 如果本机私有绑定生效但当前生图工具不能把绑定路径里的参考图作为图像输入：快速测试和自我介绍展示可以主动生成绑定角色方向预览图；最终成稿必须要求用户把参考图上传到当前对话，或换用支持参考图/图像编辑的生图工具。

## 角色参考图落位

固定角色参考图放在 `assets/references/characters/`。

- 用户自己的 IP：建议命名为 `assets/references/characters/<subject-slug>-reference.png` 或 `.jpg`。
- 只放用户自己的原创角色、用户明确授权的品牌/项目角色，或用户有权使用的素材。
- 不放第三方 IP、名人形象、在世创作者可识别角色、未授权品牌角色，也不把第三方角色改色当作用户 IP。
- 每放入一张长期参考图，都要生成或更新 `ip-subject.md`：写明参考图路径、来源授权、识别点、禁改点、动作库、常见道具和连续配图一致性规则。
- 如果用户只是一次性测试，不必要求他改文件；直接使用当前对话上传图，并提醒“要长期复用时再放入固定目录”。
- 目录不是自动候选池。除非用户明确指定路径，或 `ip-subject.md` / `ip-subject.local.md` 明确绑定当前角色，否则不要扫描并选用目录中的图片。

## 画面密度档位

默认自动选择密度，不让用户先选菜单。不确定时优先轻配图；如果内容既适合正文配图又适合深度拆解，可以给“轻配图 / 中密度解释图 / 高密度工作台”三种方案供用户取舍。图中文字也默认由 Agent 从内容里提取短词，不要求用户提供白名单。

固定角色一致性是自动密度之前的前置门槛。先判断固定主体在该密度里是否还能被识别，再决定信息量；如果角色会被压小、被道具淹没或只剩颜色特征，当前密度不合格。合格方案必须让红鼻子、白肚皮、黄耳/触角、大眼睛、脸型和物种轮廓清楚可读。

抽象镇小宁唯一母版的自动尺度底线：

| 场景 | 推荐角色高度 | 自动处理 |
| --- | --- | --- |
| 角色小样 / 头像 / 表情实验 | 画布短边 32%-45% | 允许近景，优先母版一致性 |
| 轻配图 / 自我介绍展示 / 方向预览 | 画布短边 26%-34% | 保留留白，减少道具，不压小角色 |
| 中密度解释图 | 画布短边 22%-30% | 保留 1-2 个信息区，角色识别点优先 |
| 高密度工作台 | 画布短边 20%-26% | 如果一致性不通过，自动拆成系列或降到中密度 |

如果自动密度和角色一致性冲突，角色一致性优先。不要接受“信息密度正确但镇小宁不像”的图。

多风格对比时的差异底线：

- 白底彩铅：稳定、清楚、白底手绘，主体和道具都偏干净。
- 抽象镇小宁涂鸦：必须明显更抽象、更幼拙、更乱线，接近唯一母版；不要只是白底彩铅版多几条乱线。抽象图仍必须跟随同组白纸底，不能靠换成另一种底色来制造风格差异。
- 抽象镇小宁涂鸦不能接入唯一母版时，直接用固定母版作为抽象小图，不要文本生图重画一只新的普通蓝色卡通。
- 虚实结合：必须明显更有真实材料感，但仍遵守密度预算。差异来自真实场景品种的自动选择，例如电脑线缆、打印稿、便签标签、收纳盒、旧相框、工具胶带、样稿堆、笔记本边角或桌面小器具；不要每次都用同一种电脑 + 线缆 + 便签组合，也不要把画面塞满。

## 三风格调度

三种风格不是平级菜单，先判断每张图的功能，再选择主风格。一张图只选一个主风格；同一篇文章可以混用三种风格，但必须有主次和视觉节奏。

- **白底彩铅 = 文章骨架 / 解释图**：用于核心观点、分类、机制、教程、方法、产品说明和“读者需要看懂什么”的图。
- **抽象镇小宁 = 情绪闪点 / 状态图**：用于一个状态、一个情绪或一个瞬间动作，例如卡住、冒出来、过载、跑偏、松口气、粉丝少也能开始。它不负责解释复杂逻辑。
- **虚实结合 = 现实证据 / 工作现场**：用于过程、实验、改稿、寄送、票据、样稿、工具使用、Before/After 和“读者需要相信这事真的发生”的图。

自动判定时先问：

1. 这张图要让人看懂一个观点、机制或路径吗？用白底彩铅。
2. 这张图只要让人感到一个状态或情绪吗？用抽象镇小宁。
3. 这张图要让人看到真实材料、现场证据或工作流程吗？用虚实结合。

### 风格候选测试和正式配图的区别

当用户说“测试一下”“看看效果”“用这段内容试试”“对比几种风格”且没有指定单一风格时，先进入风格候选测试，而不是立即按内容推荐唯一主风格。候选测试必须让三种风格都出现：

- 白底彩铅候选：选择内容里最需要解释的观点、机制或路径，做一张清楚的中低密度解释图。
- 抽象镇小宁候选：只选择内容里的一个状态词或情绪瞬间，做状态小图；不能承载整段观点。若已有抽象镇小宁唯一母版且当前工具不能接入参考图，直接展示/引用母版图作为抽象候选，不用文本生图重画。
- 虚实结合候选：选择内容里的现实证据、工作现场、原型、工具、样稿或改稿过程，按密度预算自动更换真实场景品种。

候选测试不是“三张同构图换材质”。每张图都要回答不同的视觉任务，并在最后推荐后续锁定哪一种风格。用户选定风格后，才进入正式单风格配图；正式配图时仍按图的任务调度，不必每次都出三张。

抽象镇小宁的硬门槛：

- 能用一个状态词或一个瞬间动作概括。
- 不看解释，3 秒内能感到这个状态。
- 最多 1 个动作 + 2 个短词。
- 如果内容需要表达“因为 A 所以 B 最后 C”，直接判定不适合抽象，改用彩铅或虚实结合。

文章级视觉节奏建议：

| 位置 | 图的任务 | 推荐风格 |
| --- | --- | --- |
| 头图 | 核心观点或总览 | 白底彩铅，除非文章本身就是情绪主题 |
| 中段 | 机制、方法、分类、步骤 | 白底彩铅 |
| 转场 | 状态、卡点、鼓励、松口气 | 抽象镇小宁 |
| 过程 / 证据 | 工作台、寄送、票据、样稿、改稿 | 虚实结合 |
| 结尾 | 留下一个情绪或行动感 | 抽象镇小宁或白底彩铅 |

一篇短文通常 0-1 张抽象图；长文通常 1-2 张抽象图；抽象图不要连续出现，也不要做主图，除非整篇文章主题本身就是状态或情绪。

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
- 固定角色默认是“中等小角色”：正文配图、通用展示、工作流复盘和方向预览中，普通镇小宁或其他固定角色单体高度通常占画布短边 15%-22%，最高不超过 24%。抽象镇小宁使用上方“唯一母版自动尺度底线”，通常要比普通固定角色更大一些。为了避免生图模型把角色压得过小，prompt 必须同时给可读性要求：红鼻子、白肚皮、黄色长耳/触角、大眼睛清楚可读；相对尺度是比主道具略小或相近，像在便签、纸堆、线缆或盒子旁边工作的角色。画面关系主要由道具、纸张、线缆、工作台局部和信息载体承担，角色不能变成远处小贴纸，也不能居中正面近景、大头或比信息载体更抢眼。只有角色设定图、封面主视觉、头像、表情或用户明确要求近景时，才允许放大到 24%-32%。
- 如果使用实物拼贴手绘风，真实物件可以比角色大，但角色必须和物件发生拉扯、贴住、压住、夹住、露出、修补等关系；不要把角色贴成大号吉祥物或角落装饰。
- 如果是自我介绍、能力展示或多风格对比里的实物拼贴，真实感来自场景品种变化，而不是物件数量加码。先按密度档位确定物件预算，再自动选择适合内容的真实场景品种，并围绕一个核心动作组织。
- 如果使用抽象镇小宁涂鸦风，乱线和彩铅涂痕只改变表现方式，不改变主体身份。镇小宁仍要保留蓝色圆润主体、白肚皮、红鼻子、大白眼黑瞳、黄色眉毛和头顶黄色长耳/触角；不能退化成普通蓝色涂鸦角色。若存在抽象镇小宁唯一母版，必须从这张母版延展，不要每次随机生成新的抽象画法。
- 抽象镇小宁涂鸦风必须根据内容关系生成自身变形，而不是从固定动作模板里抽取，也不是普通镇小宁和抽象道具互动。先判断内容里的受力方式，例如被压住、被拉长、被缠住、被撑开、被挤扁、被点亮、被打结、被剪开、被吹散、被吸进去、被托起来或被拽回来；再决定耳朵、鼻子、肚皮、眼睛、身体轮廓、手脚、侧耳、颜色线团或影子如何变形。外部纸缝、便签、线缆、标签只能做压力源或触发点，不能成为主视觉。不得连续复用同一套变形。
- 抽象变形不能只回答“被什么力作用”，还必须先写清主题对立轴和形状语义：这张图里哪两股力量相互冲突，以及圆/方、软/硬、散/齐、弯/直、开/合分别代表什么。只有形状语义成立，受力方式才成立；如果去掉外部道具和短词后，镇小宁本体的变形读不出状态，判定失败。
- 抽象变形先发散再收敛。出图前必须先列 3-5 个候选变形，且候选来自不同身体系统：轮廓/重心、耳朵/触角、眼睛/鼻子、手脚/姿态、影子/颜色线团、局部材料状态。用主题贴合度、角色识别度、新鲜度和道具依赖度选 1 个；不要只把第一个想到的变形写进 prompt。
- 身体部位选择也要有语义，不得默认都用肚皮 / 白肚子作为主变形。肚皮只在内在核心、承载、消化、自我中心或被看见时优先；方向和外界声音优先用耳朵，注意力和锚点优先用红鼻子，失焦/聚焦优先用眼睛，边界和压力优先用身体轮廓，行动卡住优先用手脚，漂移和余波优先用影子或颜色线团。同组或连续测试里，上一张已用肚皮主变形，下一张优先换身体部位。
- “接回 / 恢复 / 重新开始 / 找回来”默认不是接断线、接线束、修电线或缝合裂缝；除非内容明确是线缆、缝合或维修，否则应画成状态恢复：重心回中、身体轮廓收拢、眼神重新聚焦、耳朵回弹、脚重新踩住纸面、影子回到身体下面。
- 抽象变形的主语是镇小宁自身的个体变形，压力源不是必备主角。能用镇小宁身体轮廓、肚皮、耳朵、鼻子、眼睛、手脚或影子的变化表达状态时，不额外加入外部压力源；若必须使用纸缝、便签、线缆或标签，它们只能是小触发点或参照物。抽象变形的强度不能通过放大到快铺满画面实现。状态图、方向预览和正文轻配图里，变形后的镇小宁本体仍按局部轻描处理：画面关系默认控制在画布宽度 30%-42%、高度 25%-36%，四周至少 30% 白纸留白；用户反馈太满时缩到宽度 25%-38%、高度 20%-32%。外部触发点不能大于镇小宁本体，也不能贴边、压边或成为最大视觉块；如果必须近景展示变形，要标注为角色小样/头像/表情实验，而不是正文配图。
- 抽象变形每次至少组合 2 个轴：受力方向、材料状态、身体部位、运动轨迹或情绪姿态。可选项包括上压、下坠、侧推、反向拉扯、向内吸、向外撑、绕圈卷、斜向滑走；揉皱、折叠、撕开、融化、结晶、起泡、漏气、弹回、静电炸开、影子错位；耳朵变方向标、红鼻子变堵点/启动点、白肚皮变小窗口、眼睛失焦/聚焦、侧耳变毛边、手脚变夹子/钩子/短线；被拖出、钻进去、弹出来、悬停、沉下去、绕远路、卡在边缘、从纸缝里露出一点；硬撑、偷看、憋住、松掉、愣住、探头、犹豫、突然醒来。同一组图里连续 3 张抽象图不得重复同一种“受力方向 + 身体部位”组合。
- 抽象镇小宁涂鸦风下，画面关系主要由同一手绘语言里的抽象小道具承担：乱线便签、歪线线缆、纸片边角、手绘按钮、草稿桌角、粗糙小工具、云朵批注。除非用户明确要求虚实结合，否则不要使用真实照片物件、写实桌面、摄影棚阴影、真实 UI 截图或产品样机场景。
- 如果用户明确要“内容更丰富”，可以升到中密度或高密度，但必须先安排分区和阅读路径，不能只是放大主体、增加纸片或堆更多批注。
- 批注是小手写注，不是标题。不要让红字、箭头或标签成为画面里最大的视觉元素。
- 图片中文字必须来自 prompt 里的短词白名单，不自动新增解释句、标题或检查清单。短词白名单由 Agent 从目标文案、核心观点和平台语境里自动提取，除非用户主动指定文字。默认要把白名单里的短词直接画进图里，像手写批注、云朵短词、小标签或纸角字迹；不要把气泡、标签、卡片或纸条全部留空。如果成图已经自然画出可读、贴合内容且不跑偏的短词，直接保留原图。禁止使用本地排版、Pillow、ImageMagick、本地字体、截图叠字或后期排字补标题、副标题、说明条和正文。若关键短词连续写坏或漏画，减少短词并重生成；仍失败时交付少字/无字图，把准确文字放在图外文案里。
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
- 可选虚实结合：是否使用实物拼贴手绘风；若使用，列出 1-3 个通用真实物件和手绘角色的具体互动关系。
- 可选抽象镇小宁：是否使用抽象镇小宁涂鸦风；若使用，说明这是固定主体的艺术变体，列出必须保留的识别点和允许的乱线/涂鸦程度。

如果用户要求更强去 AI 味，先读取 `handdrawn-style-seeds.md`，选择一个具体工具风格后再填写本节。

## 画面原则

- 每张图只讲一个核心意思。
- 用户上传、点名角色，或本机私有默认角色绑定生效时，必须使用该角色作为主视觉主体；先保留颜色、体型、五官、标志部件和比例，再转换手绘画风。
- 固定角色默认是参与动作的中等小角色，不是大幅主角海报，也不是远处小贴纸；正文配图和通用展示中单体高度通常控制在画布短边 15%-22%，最高不超过 24%。prompt 里必须把这个尺度翻译成相对关系：角色比主要道具略小或相近，贴近纸角、线缆、盒子或便签边缘工作，红鼻子、白肚皮、黄色长耳/触角和大眼睛清楚，不站成正面近景大头。
- 当前对话上传角色图时，必须优先使用当前上传图；不得因为固定目录里有其他角色图就切换主体。
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
- 实物拼贴手绘风只在用户明确要求虚实结合、真实工作台或展示感时使用；真实物件必须是通用物件，不出现品牌 logo、真实账号、真实 UI 截图或未授权素材。
- 抽象镇小宁涂鸦风只在用户明确要求抽象、随手画、涂鸦、乱线彩铅或更艺术的镇小宁时使用；这是镇小宁的抽象艺术变体，不是替换主体，也不是画真人肖像。若有抽象镇小宁唯一母版，本节必须写明母版路径，并说明本次固定使用这张母版。抽象风一旦选中，角色、道具、场景和批注都要统一成乱线彩铅草稿语言，不把抽象角色放进写实场景。
- 当本节用于多风格对比，必须写出三张图的差异：白底彩铅 = 稳定手绘；抽象涂鸦 = 母版驱动、明显更乱线更幼拙；虚实结合 = 真实材料感和场景品种自动变化。虚实结合仍按轻/中/高密度预算控制物件数量，镇小宁只需和关键物件发生明确互动。
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
- 固定角色尺度：正文配图、通用展示和方向预览中，单体高度通常占画布短边 15%-22%，最高不超过 24%；同时写清相对尺度和可读性，例如“比主道具略小或相近、不是远处贴纸、红鼻子/白肚皮/黄耳/大眼清楚”。只有角色设定、封面主视觉或用户明确要求近景时可放大。
- 抽象角色变体尺度：正文配图仍按中等小角色尺度；只有用户明确要求角色小样、头像、表情或近景风格实验时，才允许把抽象镇小宁放大为主体近景。
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

If local private default subject binding is active, use Zhenxiaoning as the main visual subject. Do not draw a human portrait, realistic avatar, abstract person, empty scene, thread person, hollow box, generic blue mascot, ordinary blue character, or any other replacement subject. If this is only a direction preview because the generator cannot receive the reference image, label it as "方向预览，非最终 IP 一致性成稿" and do not present it as a final IP-consistent artwork.

If the user explicitly asks for an abstract / doodle / more artistic Zhenxiaoning variant, keep Zhenxiaoning as the subject and transform only the drawing language: loose colored-pencil scribbles, rough sketchbook marks, uneven coloring, childlike proportions, and more human emotional expression. This means emotional human-like presence, not a realistic human face, human portrait, selfie, or professional avatar.

Subject scale:
For ordinary recurring subjects in normal article illustrations, self-showcase images, workflow recaps, and direction previews, keep the subject as a readable medium-small operator: about 15%-22% of the canvas short side in height, never above 24%. For abstract Zhenxiaoning using a unique master reference, choose scale automatically by density and require identity consistency: 32%-45% for character studies, avatars, or expression tests; 26%-34% for light illustrations, self-showcase images, and direction previews; 22%-30% for medium-density explainers; 20%-26% for high-density workbenches, and only if identity still reads. The red nose, white belly, yellow ears/antennae, big eyes, face shape, and scribble density must remain readable. Do not make the subject a tiny sticker, centered close-up, big head, giant mascot, or poster hero unless the user explicitly asks for a character hero image, avatar, or cover close-up.

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

Optional photo-object sketch collage:
Use only if the user explicitly asks for 虚实结合 / 实物拼贴 / 真实工作台 / photo-object sketch collage. Place 1-3 generic real objects on a clean white tabletop or studio background, then let the hand-drawn subject physically interact with them. Avoid brand logos, real UI screenshots, stock-photo office scenes, product advertising, and a pasted-on sticker feeling.

Optional abstract Zhenxiaoning doodle variant:
Use only if the user explicitly asks for 抽象镇小宁 / 随手画 / 涂鸦 / 乱线彩铅 / more artistic Zhenxiaoning. Preserve Zhenxiaoning's identity marks: rounded blue creature body, white belly, red round nose, two big white eyes with black pupils, yellow eyebrows, two yellow long ears/antennae on top, side pointed ears or fluffy side silhouette, and short rounded limbs. The drawing may feel more emotionally human, but it must not become a realistic human portrait, generic blue mascot, thread person, hollow box, or unreadable blue scribble.
If a unique abstract Zhenxiaoning master reference is available, use that single image as the actual image input / identity source / style source when the tool supports it. Match the master reference's scribble density, blue/yellow/red color behavior, red nose placement, yellow ear/antenna shape, big-eye spacing, white belly proportion, side ear/fluffy silhouette, and overall face structure. The master reference locks the character, not the output background: keep the final background in the same unified white-paper family as the series, either pure white or very light paper white, with no separate cream/beige/old-paper tint, vignette, or heavy full-background paper texture for the abstract image. Do not invent a fresh abstract Zhenxiaoning design from text alone, and do not mix in other abstract variants. If the current tool cannot receive reference images, label the result as an abstract Zhenxiaoning direction preview, not final IP-consistent artwork.

Abstract deformation logic:
Use abstract Zhenxiaoning only for one status, one emotion, or one instant action. Derive the deformation from the current content's force, not from a fixed template list. First name the force (pressed, stretched, tangled, wedged open, squeezed, lit up, knotted, cut, blown away, pulled back, lifted), then choose which body part transforms (ears, nose, belly, eyes, body outline, limbs, side ears, color lines, shadow). Avoid a static Zhenxiaoning standing beside abstract symbols.
Before naming the force, write the theme opposition axis and shape semantics: what two forces are in conflict, and what round/square, soft/hard, scattered/aligned, curved/straight, open/closed shapes mean in this topic. The deformation must still read as the intended status if all external props and Chinese notes are removed.

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
{局部轻描 / 小场景 / 完整场景 / 工作台}. For 轻配图, default to 局部轻描: one small action cluster with 2-4 objects and one occlusion/reveal/process relationship, not a complete room, street, shop, dashboard, or workbench. Keep the cluster at 30%-45% of canvas width and 25%-40% of canvas height, with at least 25% blank margin on all sides. If the user complained about crowded edges, shrink the cluster to 30%-40% width and 25%-35% height, with at least 30% blank margin. Keep the recurring subject itself smaller than the prop/action cluster; it should operate the scene, not dominate it.

Series variety:
If this is part of a series, state which composition mode is used and how it differs from the previous images. Avoid repeating left-input / center-character / right-output cards unless this is the first image or there is a strong reason.

Short Chinese notes:
{Agent 从本图目标文案自动提取，按密度档位填写：轻配图 0-2 个；中密度解释图 3-6 个；高密度工作台 8-12 个。不要要求用户手动列词。}

Exact Chinese text allowed:
{Agent 从目标文案自动列出允许出现在图里的所有中文短词。默认直接把这些短词画进图里，作为小手写批注、云朵短词、小标签或纸角字迹；生成图不得新增解释句、标题、段落、检查清单或未列出的中文；不得把所有文字容器留空。}

Hard limits:
Follow the selected density tier, but fixed-character consistency is the gate before density. 轻配图 must stay sparse and leave at least 45%-55% white space; show one everyday action relationship with 2-4 objects, not an overview and not a static prop arrangement. For 轻配图, keep the subject/object cluster visibly smaller than the canvas, avoid edge-to-edge composition, and make handwritten notes small annotations rather than titles. Keep ordinary Zhenxiaoning or any locked recurring subject as a readable medium-small operator in normal explanatory images: about 15%-22% of the canvas short side, max 24%, unless explicitly making a character hero image. For abstract Zhenxiaoning with a unique master reference, use the automatic density scale: 32%-45% for character studies, 26%-34% for light illustrations/self-showcase/direction previews, 22%-30% for medium-density explainers, and 20%-26% for high-density workbenches only if the identity still reads. Do not shrink it so much that the red nose, white belly, yellow ears/antennae, big eyes, face shape, or scribble density disappear. All visible Chinese text must be short and must come only from the exact allowed text list; directly render the allowed short words in the image as rough handwritten annotations, cloud notes, tiny labels, or exposed note corners. Do not invent headlines, explanatory sentences, paragraph text, checklist items, or extra labels. Do not leave all speech bubbles, labels, cards, note papers, or UI-like text areas blank when allowed short words are provided. 中密度解释图 must have two clear information zones at most and leave at least 35% white space; it may use a rough small scene, but the scene must be driven by the action, not by card stacking, and must not be a polished full room, full shop, full station, full restaurant, or full workbench. 高密度工作台 may contain more material, but must have three clear sections, a main reading path, and at least 15% white space; keep the scene rough and hand-drawn, not commercial or glossy. If high density makes the fixed subject inconsistent, split the content into a series or lower the density. Do not draw every diagnostic point unless the selected tier is 高密度工作台 and the user asked for a workbench, canvas, review, lesson, PPT, or one-image overview. Do not make density differ only by adding paper cards or handwritten labels. The presentation carrier must be visible through props, action, occlusion, revealed clues, and spacing, not through explanatory text. If the framing scale is 局部轻描, use a daily action such as lifting a blanket corner, pulling a note from under cardboard, taping down a noisy red dot, shaking an old tablecloth, wrinkling a too-smooth draft, fitting a picture into mismatched frames, or fishing a clue from a cup bottom. For photo-object sketch collage, use generic real objects only and make the hand-drawn subject interact with them through occlusion, touch, pulling, taping, tying, or repair; do not create a polished product ad, stock-photo office scene, real UI screenshot, giant mascot, or pasted-on sticker. For abstract Zhenxiaoning doodle variants, treat scribbles as texture and emotional expression, not as a new subject; preserve the red nose, white belly, yellow ears/antennae, big eyes, blue rounded creature shape, and side ear/fluffy silhouette, and do not create a realistic human portrait, generic blue mascot, thread person, hollow box, or unreadable blue scribble. In abstract Zhenxiaoning doodle variants, props, scene, notes, and carriers must share the same scribbly colored-pencil paper style as the character; do not place the abstract character inside a photorealistic desktop, real-object studio scene, product mockup, real UI screenshot, or stock-photo office scene unless the user explicitly switches to photo-object collage. If a unique abstract Zhenxiaoning master reference exists, use that single image as the source of the abstract design instead of random text-only reinvention; text-only output is only a direction preview. Avoid polished interiors, polished restaurants, clean UI mockups, commercial posters, glossy 3D rendering, top-left category titles, structure labels, chaotic dense arrows, repeated left-to-right pipeline layouts, repeated paper/card/folder/timeline carrier families across adjacent series images, copied examples, public-case metaphor templates, third-party IP, recognizable living-artist styles, and any mascot-like copy of another character.
```

## QA 判断

如果去掉主体，画面仍然完全成立，主体就是装饰，需要重写构图。

如果第一眼像 PPT、课程页、架构图、儿童卡通或商业插画，不合格。

如果选择的是轻配图或中密度解释图，但第一眼像资料墙、便签墙、复杂关系网，或者需要放大才能看懂，判定为信息过密，需要降密度或拆成系列图。高密度工作台也必须有清晰分区和主阅读路径。

如果选择的是轻配图，但主体群铺得太大、贴近画面边缘、四周没有明显白边，或红字批注像标题一样抢眼，判定为尺度失败，需要缩小主体群并改成局部轻描。

如果生成图出现 prompt 未列出的中文、长句、标题化红字、段落或检查清单，判定为文字漂移，需要重写 prompt 并使用 `Exact Chinese text allowed` 白名单。

如果 prompt 已列出 `Exact Chinese text allowed`，但成图里的气泡、标签、卡片或纸条全部空白，判定为文字漏画；先重生成并明确要求“直接画入这些短中文手写批注”。不要进入本地排版或本地字体补字；连续失败时减少文字、交付少字/无字图，并把准确文字放在图外说明里。

如果轻配图和高密度工作台缩略图看起来差不多，只是后者多了几张纸或多几个标签，判定为密度失败，需要把轻配图改成单动作特写，或把高密度改成有分区的工作台。

如果同一系列里连续多张都是“左边混乱输入、中间主体、右边输出卡片”，不合格。

如果一组图里角色总是在拿笔、圈纸、贴便签，判定为呈现载体过窄；读取 `presentation-carriers.md` 后重写为操作面板、路线地图、对话现场、时间记录、空间剖面或样本图鉴等载体。

如果只是把公开案例里的标志性物件换成自己的角色，而空间关系、动作和信息承载方式没变，不合格。

如果主体和第三方角色只有名字不同，但外形和动作识别点很像，不合格。

如果用户要求抽象镇小宁涂鸦风，但成图变成真人脸、拟真人头像、普通蓝色吉祥物、线团人、空心方盒，或只剩不可识别的蓝色乱线，不合格。抽象可以降低精确度，但不能丢掉镇小宁的红鼻子、白肚皮、黄色长耳/触角、大眼睛和蓝色圆润小兽轮廓。

如果已有抽象镇小宁唯一母版，但生成时没有固定接入这张母版，或每次都生成一套明显不同的抽象画法，不合格。先回到唯一母版，确认母版识别点和当前信息密度下的角色尺度；如果一致性仍不通过，降低密度、减少短词和道具、拆成系列或改用支持参考图/图像编辑的工具。
