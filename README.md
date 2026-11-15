# Advisor Board · 专家董事会与战略顾问统一技能

一套高水准的 AI 战略顾问与决策支持技能（Codex / Claude Code / Antigravity / Cursor 等 Agent 环境通用）。

不同于传统将十几个子技能分别导入的割裂方案，本项目已重构为**一体化单一 Skill 入口（Single Skill Entry）**：
- **安装时只需导入本仓库为单个 Skill**（例如 `advisor-board`），不会污染或占满您的技能列表；
- **调用时由 Agent 智能决策，或由用户直接指定**：既支持 13 位跨学科大师的“单专家深度会诊”，也支持 3 位互补专家的“闭门董事会圆桌辩论与终审裁决”，并原生内置报刊级 A4 PDF 决策报告导出。

---

## 包含能力

### 1. 专家董事会听证（Expert Council Hearing）
针对重大的战略选择、商业转型、投资权衡与方向纠结，系统自动调度（或由用户指定）**3 位互补专家**组成席位：
- **正面主攻手**：提出进取假设与增长逻辑；
- **风险审阅者**：排查盲点、脆弱性与毁灭性风险；
- **落地压舱石**：回归执行约束与交付可行性；
展开多轮自然交锋与底层假设碰撞，并由主席给出决断性的终审裁决与行动项（Action Items）。

### 2. 13 位大师单视角深度会诊（Solo Perspective）
内置 13 位思想大师的完整心智模型、表达风格与深度研究档案（存放于 `references/personas/`）：

| 专家 | 认知透镜 | 擅长领域与标志性思维 |
| :--- | :--- | :--- |
| **查理·芒格** (`munger`) | 逆向思考 / 25 种认知偏误 / 能力圈 | 商业底线守御、排查蠢事、识别利益错配 |
| **埃隆·马斯克** (`elon-musk`) | 物理第一性原理 / 极限成本拆解 / 五步法 | 突破行业常规约束、工程落地、激进迭代 |
| **纳西姆·塔勒布** (`taleb`) | 反脆弱 / 黑天鹅 / 切身痛感 / 杠铃策略 | 尾部风险暴露排查、非对称收益识别、下行防守 |
| **杰夫·贝索斯** (`jeff-bezos`) | 客户需求反向推导 / Day 1 / 单向门决策 | 长期主义商业架构、区分可逆与不可逆决策 |
| **彼得·蒂尔** (`peter-thiel`) | 从 0 到 1 / 反共识秘密 / 逃避竞争建立垄断 | 护城河构建、反直觉战略下注、小市场垄断 |
| **安迪·格鲁夫** (`andy-grove`) | 10 倍速剧变 / 战略转折点 / 偏执狂管理 | 行业生命周期拐点、生存危机应对、组织迟钝 |
| **霍华德·马克斯** (`howard-marks`) | 周期钟摆 / 第二层思维 / 风险收益非对称 | 宏观与行业周期位置、克制等待安全边际 |
| **瑞德·霍夫曼** (`reid-hoffman`) | 闪电式扩张 / 双边网络流动性 / 人脉资本 | 平台冷启动、构建多归属成本、规模拐点 |
| **瑞·达利欧** (`dalio`) | 经济机器运行因果 / 极度求真 / 原则复盘 | 宏观周期因果推演、制度化决策机器构建 |
| **乔治·索罗斯** (`soros`) | 反射性理论 / 市场预期与现实背离 | 资本市场博弈、从共识失真中寻找反转暴利 |
| **吴恩达** (`andrew-ng`) | 以数据为中心 / Agent 工作流 / 渐进交付 | AI 与大模型实际落地、工程化阻力拆解 |
| **大野耐一** (`taiichi-ohno`) | 丰田精益生产 / 消除七大浪费 / 现场 5 Why | 流程阻滞根除、交付链路提速、一线现物诊断 |
| **张小龙** (`zhangxiaolong`) | 产品克制 / 触达即走 / 自然演化优于自顶设计 | 消费级核心体验把控、商业与用户价值平衡 |

### 3. 出版级 A4 PDF 报告引擎（Editorial PDF Engine）
内置报刊级 A4 印刷排版工作流：
- 白纸黑字、酒红点缀（Wine `#722f37`）、Serif 标题与 Sans SC 正文；
- 严格遵循 Page Roles 页面角色体系，包含封面刊头、陈词版面、辩论纪要与决策备忘录；
- 内置 Headless Chrome 自动导出与分页/密度质量检验门禁（Quality Gate）。

---

## 目录结构

```text
advisor-board-skill/
├── SKILL.md                 # 统一单一入口（总控路由规则、交互协议与 JSON Schema）
├── README.md                # 技能说明文档
├── council-reports/         # 生成的结构化报告与 PDF 产物目录
├── scripts/
│   ├── render_report.py     # 报刊级 A4 PDF 渲染与质量检验引擎
│   ├── example-report.json  # 结构化标准报告样例
│   └── requirements.txt     # 依赖说明（免安装第三方 Python 包）
└── references/
    ├── personas/            # 13 位专家的核心心智模型、表达 DNA 与研究文献
    │   ├── munger/
    │   ├── elon-musk/
    │   ├── taleb/
    │   ├── jeff-bezos/
    │   ├── peter-thiel/
    │   ├── andy-grove/
    │   ├── howard-marks/
    │   ├── reid-hoffman/
    │   ├── dalio/
    │   ├── soros/
    │   ├── andrew-ng/
    │   ├── taiichi-ohno/
    │   └── zhangxiaolong/
    ├── pdf-system/          # A4 印刷排版规范与模板
    │   ├── starter-template.html
    │   ├── pdf-design-rules.md
    │   └── pdf-system-architecture.md
    ├── matrix/              # 专家透镜速查矩阵
    └── council-hearing-guide.md # 听证会详细规范指南
```

---

## 安装方式

### 方式 1：Git Clone 安装（推荐）

直接将本仓库克隆至您 Agent 的技能目录中（例如命名为 `advisor-board`）：

```bash
# Codex / Codex App 默认路径：
git clone https://github.com/yiguang20/advisor-board-skill.git ~/.codex/skills/advisor-board

# 或其他 Agent 平台的 skills 目录：
git clone https://github.com/yiguang20/advisor-board-skill.git <your-skills-dir>/advisor-board
```

### 方式 2：手动拷贝

将本仓库整个文件夹复制到您的技能目录下，确保目标目录结构为：
```text
~/.codex/skills/advisor-board/SKILL.md
~/.codex/skills/advisor-board/scripts/...
~/.codex/skills/advisor-board/references/...
```

> **注意**：整个项目只向 Agent 暴露一个统一入口 `SKILL.md`，无需重复导入 17 个独立技能！

---

## 使用方式

安装完成后，在任意对话中即可自然触发：

### 1. 召开专家董事会讨论重大决策
用户直接说：
- *“调用董事会讨论这个问题：[你的议题]”*
- *“让董事会帮我做一次决策会诊”*
- *“请专家组深入讨论并输出 PDF 决策报告”*

Agent 会自动根据议题类型（战略、商业、AI、风险等）选配最佳的 3 位专家出席；您也可以显式指定专家（如 *“让芒格、贝索斯和蒂尔开会讨论”*）。

### 2. 单独调用某位专家视角
用户直接说：
- *“用贝索斯的视角审视这个商业模式”*
- *“从马斯克第一性原理分析这个产品的成本”*
- *“用彼得·蒂尔的反共识视角看我们有没有护城河”*
- *“芒格会怎么评价这个投资机会？”*
- *“用塔勒布的反脆弱理论检查这个架构的风险”*

Agent 会调取该专家的专属档案，以沉浸的第一人称和独特心智模型为您展开深度剖析。

### 3. PDF 报告生成环境要求
`scripts/render_report.py` 通过调用无头 Chromium 内核浏览器生成 PDF，已原生支持 macOS、Windows 与 Linux：
- 系统会自动探测已安装的 **Google Chrome**、**Microsoft Edge** 或 **Chromium**；
- 若环境特殊，可通过环境变量指定：
  ```bash
  export EXPERT_COUNCIL_CHROME_PATH="/path/to/chrome"
  ```
