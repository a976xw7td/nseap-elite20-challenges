# Challenge C10H：安装并驾驭 Hermes Agent（Install & Master Hermes Agent）

> 🔥 你的第一个真正的 AI 智能体——不是聊天机器人，是一个会学习、会记忆、会跨平台工作的数字分身。
> Your first real AI agent — not a chatbot, but a self-improving digital twin that learns, remembers, and works across platforms.

---

## 背景

C10 的目标是"构建个人智能体"——但从零构建一个完整的 Agent 系统需要大量基础设施工作：记忆管理、工具调用、多平台接入、技能系统……

好消息是：**Nous Research 已经帮你做了大部分脏活。**

[Hermes Agent](https://github.com/NousResearch/hermes-agent) 是一个开源的自我进化 AI Agent 平台（MIT 协议，36k+ GitHub stars），它内置了：

- **闭环学习系统**——自动创建技能、定期知识整合、跨会话用户建模
- **持久化记忆**——SQLite + FTS5 全文搜索，LLM 驱动的摘要与回忆
- **多平台接入**——CLI + Telegram + Discord + Slack + WhatsApp + Signal
- **40+ 内置工具**——文件操作、网络搜索、代码执行、定时任务……
- **技能系统**——兼容 agentskills.io 开放标准，复杂任务后自动创建技能
- **模型无关**——支持 OpenRouter（200+ 模型）、OpenAI、Nous Portal、Kimi、MiniMax 等

**C10H 就是要你安装这个系统、跑通它、理解它、然后用它来加速你的 C8/C9/C10 进度。**

这不是"学一个新工具"——这是给你的 C10 个人智能体选定一个操作系统。

---

## 与 C10 的关系

| | C10 | C10H |
|--|-----|------|
| 你做什么 | 构建个人智能体 | **安装并配置一个生产级 Agent 平台** |
| 起点 | 从零开始或从技能组装 | 从 Hermes Agent 出发（拿来主义） |
| 复杂度 | 开放式 | **有明确的里程碑（安装→配置→集成→定制）** |
| 验证方式 | Agent 技能库 + 使用记录 | **多平台对话 + 自动技能创建 + 定时任务** |
| 本质 | 系统构建 | **系统驾驭——先学会用，再学会改** |

完成 C10H 直接满足 C10 的基础要求。若你在 Hermes Agent 上构建了自定义技能，可同时计入 C4（技能分享）。

---

## 系统架构

```
┌─────────────────────────────────────────────────────────────────┐
│  YOU (用户)                                                      │
│                                                                  │
│  CLI (TUI) ←──┐                                                 │
│  Telegram  ←──┤                                                 │
│  Discord   ←──┼── Gateway (统一消息网关)                         │
│  Slack     ←──┤                                                 │
│  WhatsApp  ←──┘                                                 │
└──────────────────────┬──────────────────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────────────────┐
│  HERMES AGENT CORE                                               │
│                                                                  │
│  ┌──────────┐  ┌──────────────┐  ┌──────────────┐              │
│  │ LLM      │  │  Memory      │  │  Skills      │              │
│  │ Provider  │  │  System      │  │  System      │              │
│  │          │  │              │  │              │              │
│  │ OpenRouter│  │ SQLite+FTS5 │  │ Auto-create  │              │
│  │ Nous     │  │ MEMORY.md   │  │ Self-improve │              │
│  │ OpenAI   │  │ USER.md     │  │ agentskills  │              │
│  │ Kimi     │  │ Summaries   │  │ .io standard │              │
│  │ Custom   │  │              │  │              │              │
│  └──────────┘  └──────────────┘  └──────────────┘              │
│                                                                  │
│  ┌──────────┐  ┌──────────────┐  ┌──────────────┐              │
│  │ Tools    │  │  Cron        │  │  Terminal     │              │
│  │ (40+)    │  │  Scheduler   │  │  Backend      │              │
│  │          │  │              │  │              │              │
│  │ File ops │  │ Natural lang │  │ Local        │              │
│  │ Web      │  │ scheduling   │  │ Docker       │              │
│  │ Code     │  │ Cross-plat   │  │ SSH / Modal  │              │
│  │ Search   │  │ delivery     │  │ Daytona      │              │
│  └──────────┘  └──────────────┘  └──────────────┘              │
│                                                                  │
│  ┌──────────────────────────────────────────────────────┐       │
│  │  SOUL.md — 人格定义 / Personality Configuration       │       │
│  └──────────────────────────────────────────────────────┘       │
└─────────────────────────────────────────────────────────────────┘
```

---

## 挑战结构

| 阶段 | 时间 | 性质 | 产出 |
|------|------|------|------|
| **安装与初始配置** | Day 1 | 环境搭建 | 能跑通 CLI 对话 |
| **多平台接入** | Day 2–3 | 集成 | 至少一个消息平台可用 |
| **技能与记忆探索** | Day 3–5 | 使用 + 理解 | 自动创建的技能 + 记忆演示 |
| **定制与 AAR** | Day 5–7 | 定制 + 反思 | 个性化配置 + 完整 AAR |

**🏆 首个在群里用 Hermes Agent 自动发送消息/完成任务的同学，直接获得 C10 里程碑认可。**

---

## 适用原则

**⚡ AI-First 原则：** C10H 本身就是 AI-First 的终极体现——你在安装一个 AI Agent。安装和配置过程也应该用 AI 辅助（遇到报错直接问 Claude/ChatGPT）。

**📚 拿来主义原则：** Hermes Agent 整个就是"拿来"的。你需要说明：拿了什么（整个平台）、怎么配置的（你的选择）、在哪里做了个性化修改。

**📛 命名规范：** `姓名拼音_C10H_内容描述.扩展名`

---

## 前置条件

| 条件 | 要求 | 备注 |
|------|------|------|
| 操作系统 | Linux / macOS / WSL2 | 不支持原生 Windows |
| Python | 3.11+ | 安装脚本会检查 |
| Node.js | 需要 | 安装脚本会处理 |
| LLM API Key | 至少一个 | 推荐 OpenRouter（免费额度 + 200+ 模型）|
| 网络 | 需能访问 GitHub | 安装时下载依赖 |

---

## 四级任务（由浅入深）

### Level 1：安装与首次对话（🥉 Bronze）

> **在你的设备上安装 Hermes Agent，完成首次 CLI 对话。**

**任务清单：**

- [ ] 运行安装脚本：
  ```bash
  curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash
  ```
- [ ] 运行 `hermes setup` 完成初始配置向导
- [ ] 运行 `hermes model` 选择并配置一个 LLM provider（推荐 OpenRouter）
- [ ] 启动 CLI 对话，和 Hermes 聊一段有实质内容的对话（不是"hello"——让它帮你做一件事）
- [ ] 截图或录屏记录整个安装过程
- [ ] 记录遇到的问题和解决方法（这就是你的 AI 日志基础）
- [ ] 回答以下问题：
  - Hermes Agent 的记忆存储在哪个文件/数据库？
  - `SOUL.md` 的作用是什么？
  - `hermes tools` 列出了多少个可用工具？

**交付：** 安装截图 + 对话截图 + 问题回答文档

---

### Level 2：多平台接入 + 工具探索（🥈 Silver）

> **让 Hermes Agent 接入至少一个消息平台，并探索工具和技能系统。**

**选择一个平台接入：**

| 平台 | 难度 | 说明 |
|------|------|------|
| Telegram | ★☆☆ | 最简单——创建 Bot，配置 token 即可 |
| Discord | ★★☆ | 需创建 Discord Application + Bot |
| Slack | ★★☆ | 需配置 Slack App |
| WeChat | ★★★ | 可能需要额外适配 |

**任务清单：**

- [ ] 运行 `hermes gateway setup` 配置消息平台
- [ ] 在选定平台上和 Hermes 进行一次完整对话
- [ ] 探索至少 5 个内置工具（`hermes tools`），记录每个工具的功能和使用场景
- [ ] 触发至少一次**自动技能创建**——让 Hermes 完成一个复杂任务，观察它是否自动生成了技能
- [ ] 使用 `/skills` 命令查看已创建的技能列表
- [ ] 设置至少一个 **cron 定时任务**（例如：每天早上发送一条提醒/摘要）
- [ ] 体验**跨平台对话连续性**——在 CLI 开始一个话题，在消息平台继续

**交付：** 平台接入截图 + 工具探索报告 + 技能创建演示 + cron 任务配置

---

### Level 3：个性化定制 + 记忆系统深度使用（🥇 Gold）

> **把 Hermes Agent 变成"你的"智能体——定制人格、积累记忆、创建自定义技能。**

**任务清单：**

- [ ] **定制 SOUL.md**——为你的 Hermes Agent 编写个性化人格（名字、说话风格、专业领域、行为准则）
- [ ] **积累记忆**——连续使用 Hermes 至少 3 天，让它积累关于你的用户模型（USER.md）
- [ ] 使用对话搜索功能，验证 Hermes 能回忆过去的对话内容
- [ ] **创建至少 1 个自定义技能**——不是让 Hermes 自动创建的，而是你手动编写的
  - 技能必须兼容 agentskills.io 标准
  - 技能必须解决你的一个真实需求（学业、工作、生活均可）
- [ ] **配置至少 2 个不同的 LLM 模型**，对比它们在相同任务上的表现
  - 使用 `/model` 切换模型
  - 记录模型选择理由和对比结果
- [ ] 探索 **subagent 功能**——让 Hermes 派生子 Agent 并行处理任务
- [ ] 使用 `/insights` 查看使用分析，反思你的使用模式

**交付：** 自定义 SOUL.md + 自定义技能文件 + 模型对比报告 + 3天使用记忆演示

---

### Level 4：深度集成 + 系统贡献（💎 Platinum）

> **把 Hermes Agent 变成你的 C8/C9/C10 核心基础设施，或者为开源社区做贡献。**

**选择一条路径：**

#### Path A：C8/C9 项目集成
- [ ] 把 Hermes Agent 用于你的 C8 项目或 C9 自驱项目中
- [ ] 创建项目专用技能（至少 3 个），让 Hermes 能协助项目核心任务
- [ ] 配置项目专用 cron 任务（日报、提醒、数据收集等）
- [ ] 展示 Hermes 在项目中至少节省了多少时间/精力

#### Path B：MCP 集成扩展
- [ ] 为 Hermes Agent 配置 MCP server 集成
- [ ] 连接至少一个外部数据源或服务
- [ ] 创建自定义工具（tool）扩展 Hermes 的能力
- [ ] 文档化集成过程，让其他同学能复现

#### Path C：开源贡献
- [ ] 阅读 Hermes Agent 源码架构（agent/ 目录）
- [ ] 提交至少一个 Pull Request（bug fix、feature、文档改进、中文翻译均可）
- [ ] 或者：在 agentskills.io 上发布你创建的技能
- [ ] 记录你的开源贡献过程

#### Path D：部署架构探索
- [ ] 将 Hermes Agent 部署到 Docker 容器
- [ ] 或部署到云端（Daytona / Modal / SSH 远程服务器）
- [ ] 验证"无服务器持久化"——Agent 休眠时不消耗资源，唤醒后恢复状态
- [ ] 创建部署指南，让非 CS 同学也能跟着做

**交付：** 工作代码/PR + 演示 + 架构说明 + 详细文档

---

## 技术选型指南

### LLM Provider 对比

| Provider | 优势 | 劣势 | 推荐场景 |
|----------|------|------|----------|
| OpenRouter | 200+ 模型、免费额度 | 延迟稍高 | **首选——灵活、经济** |
| Nous Portal | Hermes 原生优化 | 模型选择少 | 追求最佳兼容性 |
| OpenAI | GPT-4o 品质高 | 贵 | 需要最强推理 |
| Kimi/Moonshot | 中文优化 | 国际访问问题 | 中文场景 |
| MiniMax | 性价比 | 英文较弱 | 预算有限 |

### Terminal Backend 对比

| Backend | 优势 | 劣势 | 推荐场景 |
|---------|------|------|----------|
| Local | 最简单、零延迟 | 占用本机资源 | **首选——L1/L2 阶段** |
| Docker | 隔离、可复现 | 需要 Docker | 安全性要求高 |
| SSH | 可用远程算力 | 需要服务器 | 有 VPS 的同学 |
| Modal/Daytona | 无服务器、按需付费 | 配置复杂 | L4 探索 |

---

## 必须提交的文件

| 文件 | 命名格式 | 说明 |
|------|----------|------|
| 安装记录 | `姓名_C10H_安装记录.md` | 安装过程截图 + 遇到的问题 + 解决方法 |
| 使用演示 | `姓名_C10H_demo.mp4` 或截图 | CLI 对话 + 平台接入 + 技能演示 |
| 配置说明 | `姓名_C10H_配置说明.md` | LLM 选择、平台配置、SOUL.md 定制 |
| 技能文件 | `姓名_C10H_自定义技能/` | 自定义创建的技能（如有） |
| ⚡ AI 日志（必须） | `姓名_C10H_AI日志.md` | 安装和配置过程中的 AI 使用记录。**无此项无法评审。** |
| 拿来说明 | `姓名_C10H_拿来说明.md` | 从 Hermes Agent 拿了什么、自己做了什么 |

---

## 评审标准

| 维度 | 权重 | 说明 |
|------|------|------|
| **安装与运行** | 25% | Hermes Agent 是否成功安装并能正常对话？ |
| **功能探索深度** | 25% | 探索了多少功能？记忆、技能、工具、定时任务？ |
| **完成级别** | 20% | Level 1–4 到哪一级？ |
| **个性化与创造** | 20% | SOUL.md 定制质量、自定义技能、实际使用深度 |
| **拿来主义质量** | 10% | 对 Hermes Agent 架构的理解程度 |

### Bonus Points

| Bonus | 加分 | 条件 |
|-------|------|------|
| 中文本地化 | +5% | 为 Hermes Agent 贡献中文翻译/中文文档 |
| 帮助他人安装 | +5% | 在群里帮至少 2 个同学成功安装 |
| 原创技能发布 | +10% | 在 agentskills.io 上发布技能 |
| 开源贡献 | +10% | 被 Hermes Agent 官方合并的 PR |

---

## 起步指南

### Step 1：准备环境（Day 1 上午）

确认你的系统满足前置条件：

```bash
# 检查 Python 版本（需要 3.11+）
python3 --version

# 检查 Node.js
node --version

# 如果缺少，先安装（macOS）
brew install python@3.11 node

# 或者（Ubuntu/WSL2）
sudo apt update && sudo apt install python3.11 nodejs npm
```

### Step 2：安装 Hermes Agent（Day 1 上午）

```bash
# 一键安装（自动处理所有依赖）
curl -fsSL https://raw.githubusercontent.com/NousResearch/hermes-agent/main/scripts/install.sh | bash

# 验证安装
hermes --version
```

### Step 3：初始配置（Day 1 下午）

```bash
# 运行配置向导
hermes setup

# 选择 LLM（推荐先用 OpenRouter）
hermes model

# 查看可用工具
hermes tools
```

### Step 4：第一次对话（Day 1 下午）

```bash
# 启动 CLI
hermes

# 试试这些命令：
# /new — 新对话
# /model — 切换模型
# /skills — 查看技能
# /usage — 查看用量
```

### Step 5：向深度探索（Day 2+）

开始 Level 2 任务：接入消息平台、探索工具、触发技能创建。

---

## 参考资源

| 资源 | 说明 |
|------|------|
| [GitHub Repo](https://github.com/NousResearch/hermes-agent) | **起点——源码 + README** |
| [官方文档](https://hermes-agent.nousresearch.com/docs) | 完整安装和使用指南 |
| [agentskills.io](https://agentskills.io) | 技能市场——浏览和发布技能 |
| [Nous Research Discord](https://discord.gg/NousResearch) | 社区支持 |
| [OpenRouter](https://openrouter.ai) | 推荐的 LLM Provider（免费额度） |

---

## 激励维度

| 维度 | 在 C10H 中的体现 |
|------|----------------|
| 🥇 先行者 | **首个在群里用 Hermes 自动完成任务的同学获得 C10 里程碑认可** |
| 📤 分享者 | 在群里分享安装经验、配置技巧、踩坑记录 |
| 📈 进步者 | 从 Level 1 安装到 Level 3 定制的能力跃迁 |
| 🤝 助人者 | 帮其他同学解决安装问题、配置难题 |

---

## 为什么 C10H 值得做

```
C10  = 构建个人智能体（开放式，可能不知道从哪开始）
C10H = 安装一个生产级 Agent 平台（明确的起点 + 渐进式探索）
```

很多同学对 C10"构建个人智能体"感到无从下手——因为从零构建意味着你要同时解决记忆、工具、平台、模型、调度等所有问题。

C10H 的核心思路是：**先站在巨人的肩膀上。**

Hermes Agent 是一个 36k+ stars 的成熟开源项目，MIT 协议，有活跃的社区和完善的文档。它不是玩具——它是一个生产级 Agent 平台。

安装它、理解它、定制它——这个过程本身就是 C10 最有效的学习路径。当你理解了 Hermes Agent 的架构（记忆系统、技能系统、工具系统、多平台网关），你就理解了构建 Agent 的核心模式。然后你可以选择：

- **继续在 Hermes 上构建**——添加自定义技能、接入更多平台、贡献开源
- **迁移到自己的架构**——带着从 Hermes 学到的设计模式，构建更适合自己需求的系统

无论哪条路，你都不是从零开始。

**更深层的价值：** C10H 训练的是"系统驾驭能力"——面对一个复杂的开源系统，如何快速安装、理解架构、找到定制点、发挥价值。这是每个工程师都需要的能力，也是拿来主义的高级形态。

---

> 📣 **C10H 的终极价值：**
>
> 不要重复发明轮子——先学会驾驭最好的轮子，然后在它上面建造你的车。
> Hermes Agent 是轮子，你的个人智能体是车，C8/C9 的项目是你要去的地方。
