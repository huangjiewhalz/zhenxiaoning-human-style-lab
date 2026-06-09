# Window Experiment Log

彩蛋模式：把当前窗口、项目迭代或长对话整理成 3-5 张手绘实验日志图。适合用户说“把当前窗口做成几张图”“一窗实验日志”“把这次打磨过程可视化”“把这个项目过程做成手绘复盘图”。

核心目标：把 AI 使用过程也沉淀成个人风格资产。不是截图聊天记录，而是提炼这一窗的起因、卡点、选择、结果和下一步。

## 触发语

- 把当前窗口做成 3-5 张图。
- 把这次对话整理成手绘实验日志。
- 用我的角色，把这个项目打磨过程可视化。
- 生成一窗实验日志。
- 把这次 AI 实验做成几张可以发布的图。

## 边界

- 不逐字转写完整聊天记录。
- 不把密钥、账号、私密路径、联系人、未授权素材或不适合公开的信息画进图里。
- 不编造用户身份、奖项、产品事实或项目结果。
- 不使用第三方 IP、名人、在世创作者或公开案例的可识别风格。
- 不把每张都画成聊天窗口、文件树、截图或便签墙。
- 如果当前环境读不到完整窗口，先要求用户提供窗口摘要、关键对话片段或项目路径。

## 输入

优先使用当前上下文中已经存在的信息。缺少信息时最多问 3 个问题：

1. 这组实验日志要公开发布，还是只给自己复盘？
2. 要使用哪个固定角色或 IP 主体？
3. 有哪些信息不能出现在图里？

可选输入：

- 用户身份或署名，例如“心满”。
- 项目或产品事实，例如“镇小宁是我的 AI 领域试验田”。
- 已授权奖项、链接、角色图、产品截图或作品样本。
- 目标平台：论坛、公众号、小红书、X、PPT、Notion。
- 目标张数：默认 4 张；内容很短用 3 张，过程复杂用 5 张。

## 执行流程

1. **确定范围**：当前窗口 / 用户粘贴的对话 / 项目路径 / 摘要。
2. **做隐私过滤**：列出不能进图的信息，必要时用“私密内容已省略”替代。
3. **生成实验卡**：只写事实和用户已授权信息。
4. **选择叙事结构**：按 3、4 或 5 张规划。
5. **读取视觉规则**：需要角色时读取 `visual-ip-system.md`；需要手绘去 AI 味时读取 `handdrawn-style-seeds.md`；需要布局避重时读取 `layout-selection-engine.md` 和 `presentation-carriers.md`。
6. **生成布局表**：每张图写清节点、密度、载体、布局、主体动作、允许中文短词。
7. **判断生图能力**：读取 `model-runtime-requirements.md`。有生图能力再生成图片；没有时先提示限制，再输出 prompt。
8. **按 QA 复查**：读取 `qa-checklist.md`，检查隐私、事实、角色、密度、留白、布局避重和中文白名单。

## 实验卡模板

```markdown
# Window Experiment Card

## 范围

- 来源：当前窗口 / 粘贴对话 / 项目路径 / 用户摘要
- 用途：公开发布 / 内部复盘 / 参赛展示 / 项目记录
- 目标平台：
- 角色主体：

## 起因

## 目标

## 卡点

## 关键选择

## 打磨动作

## 当前结果

## 下一步

## 不能进图的信息

## 可公开事实
```

## 叙事结构

### 3 张

用于小复盘或轻量发布：

1. 起因：为什么开始这次实验。
2. 打磨：中间遇到什么卡点，如何选择。
3. 结果：现在沉淀出什么，下一步怎么用。

### 4 张

默认结构，适合“试验田”叙事：

1. 试验田：项目、角色或窗口从哪里开始。
2. 卡点：默认 AI 味、风格不稳、配图重复或边界不清。
3. 打磨：加入证据地图、反风格、手绘规则、布局密度。
4. 交付：形成可复用资产，留下下一轮校准入口。

### 5 张

用于过程复杂或参赛展示：

1. 灵感：一句话痛点。
2. 调研：看见相邻竞品、痛点或真实场景。
3. 搭建：把想法拆成文件、规则和工作流。
4. 测试：用角色、文章或产品说明生成样例。
5. 发布：沉淀成可复用 Skill，并开放给别人使用。

## 视觉规则

- 默认使用白底手绘解释图，不做商业海报。
- 默认优先铅笔草图风；如果用户想更松弛，可以用蜡笔涂鸦风。
- 用户上传角色或点名角色时，角色必须参与核心动作，不做角落装饰。
- 每张图只讲一个节点，不把整个窗口全部塞进单图。
- 默认 16:9；正文配图优先轻配图或中密度解释图；参赛展示、PPT 或“一张讲清楚”可以使用高密度工作台。
- 每张图至少保留明显留白。低密度至少 55% 留白，中密度至少 35%，高密度至少 15%。
- 中文只允许短词，必须列入 `Exact Chinese text allowed`。不要让模型自动生成标题、长句、段落或检查清单。

## 载体建议

不要默认画聊天窗口。根据节点选择载体：

| 节点 | 推荐载体 | 说明 |
| --- | --- | --- |
| 灵感/起因 | 试验田、桌角、灯泡草稿、路口门牌 | 一个念头开始，不画宏大场景 |
| 卡点 | 工具修理、实验检测、控制台、堵住的路线 | 表达问题被发现 |
| 调研/选择 | 地图路线、样本图鉴、天平、博物馆展柜 | 表达比较和取舍 |
| 搭建 | 工具箱、抽屉收纳、维修工位、裁缝试衣 | 表达规则和模块沉淀 |
| 测试 | 实验台、显影盘、对照台、操作面板 | 表达反复试图 |
| 发布/交付 | 舞台后台、小店货架、档案袋、路线出口 | 表达可复用和可交接 |

连续 3 张以上时，至少使用 3 类载体；不要连续使用纸片、便签、文件夹。

## 输出格式

```markdown
## 窗口实验卡

## 隐私过滤

## 系列规划

| 序号 | 节点 | 密度 | 载体 | 布局 | 主体动作 | 允许中文短词 | 避重理由 |
| --- | --- | --- | --- | --- | --- | --- | --- |

## 生图能力判断

## 图片 Prompt

### 图 1

- Scene plan：
- Exact Chinese text allowed：
- Prompt：

### 图 2

- Scene plan：
- Exact Chinese text allowed：
- Prompt：
```

## Prompt 模板

```text
Create a 16:9 white-background hand-drawn explanatory illustration for a personal AI experiment log.
Use the user's original IP subject as the active character. The subject must perform the core action, not stand as decoration.

Scene node: {起因/卡点/打磨/结果/下一步}
Density: {轻配图/中密度解释图/高密度工作台}
Carrier: {chosen carrier}
Layout: {chosen layout}
Main action: {subject action}
Visual style: {pencil sketch / crayon doodle / red-pen review}, visible hand-drawn texture, imperfect lines, spacious composition.

Exact Chinese text allowed: {short words only}
Do not add any other Chinese or English text.

Avoid polished vector art, 3D rendering, glossy gradients, commercial mascot style, chat transcript screenshots, file-tree screenshots, dense arrows, copied examples, third-party IP, recognizable living-artist style, and large title text.
```

## 示例触发

```text
使用我的风格分身工坊，把当前窗口整理成 4 张“一窗实验日志”手绘图。使用我上传的角色，风格保持铅笔草图，留白多一点，适合发参赛帖。
```
