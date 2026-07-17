📣 Elite20 同学们：

**重磅挑战发布 —— C2G：参数高尔夫 Parameter Golf**

这是 Elite20 迄今为止**技术难度最高、职业回报也最高**的一个挑战。做好了，年薪 $200,000 的 OpenAI / DeepMind / Anthropic / xAI offer 不是广告词，是过去一年里已经在发生的事实。

---

🤔 这是什么

OpenAI 在 2026 年 3 月发了一个公开比赛，规则简单到残酷：

> **所有人用同样的 8 张 H100，同样的 10 分钟训练时间，同样的 16MB 模型大小上限。**
> **比的不是资源，是你的架构 + 系统 + 优化能力。**

- 评估指标：**BPB**（bits-per-byte），越低越好
- Naive baseline：**1.2244 BPB**（9 层 512 维 Transformer）
- 当前全球榜首：**1.0810 BPB**（SP8192 + 3-Layer Recurrence）
- 赛事窗口：**2026-03-18 → 2026-04-30**

**OpenAI 公开说：** 这个比赛的重点招聘对象是**本科生、应届生、奥赛奖牌得主**。榜单前 20 名过去一年已经有超过一半进了顶级 AI 实验室。

---

💰 这不是夸大宣传

```
一般 ML 岗位招聘流程：
简历 → 在线测评 → HR 面 → 技术面 x3 → 系统设计 → 文化面 → offer（3–6 个月）

Parameter Golf 流程：
上榜 → OpenAI 主动发 DM → 跳过前 5 轮 → 直接 onsite（2 周）
```

这个比赛**本身就是前沿实验室的招聘漏斗**。因为 BPB 数字不会说谎——没有背景包装、没有关系户、没有面试技巧——**你的能力就是你在榜单上的位置**。

---

📦 起步包（需要你自己 Fork）

```bash
git clone https://github.com/openai/parameter-golf.git
cd parameter-golf

# 装依赖
pip install torch sentencepiece flash-attn --break-system-packages

# 跑 baseline（约 9 分 30 秒）
torchrun --nproc_per_node=8 train_gpt.py --config baselines/naive_9l512d.py
# 预期输出：BPB ≈ 1.2244
```

群里已放置 `c2g-parameter-golf-starter.zip`（含官方 repo 镜像 + 我整理的训练日志模板 + 历史 top 方案清单）。

**前置知识：** nanoGPT 视频至少看一遍（[Karpathy · 2h build-nanogpt](https://www.youtube.com/watch?v=l8pRSuU81PU)）。不看你会痛苦。

---

⚡ 核心要求：AI-First + 拿来主义

**严禁从零写 Transformer。** 正确起点：
- `nanoGPT`（所有现代方案的祖先）
- OpenAI 官方 `train_gpt.py`（脚手架）
- 历史 top 方案（按规则可复用）

**每一次改动都必须**用 Claude / GPT 先讨论假设 → 再跑对照实验 → 再写分析。手动调试要反向举证："这一步为什么没让 AI 帮忙？"

---

🎯 四级任务

| 级别 | 目标 BPB | 全球位置 | 职业信号 |
|------|---------|---------|---------|
| 🥉 Level 1 | ≈ 1.2244（复现 baseline） | —— | 跑通了 LM 训练 pipeline |
| 🥈 Level 2 | < 1.18（单点改进） | 前 500 | 能做实验设计 |
| 🥇 Level 3 | < 1.12（组合优化） | 前 50 | **OpenAI 推荐信触发线** |
| 💎 Level 4 | < 1.085（挑战 SOTA） | 前 20 | **直通顶级实验室 onsite** |

**🏆 首个达成 Level 3 的同学，直接获得 Elite 20 最高荣誉 + 推荐信 + OpenAI 招聘通道内推。**

---

🚪 算力申请门槛（第一道门不是代码，是思考）

**重要：C2G 不是「报名即给算力」。** 即使是 Level 1 的 **$25 Elite20 赞助算力额度**，也必须**先交方案草案，审核通过后才发放算力券**。

| 等级 | Elite20 赞助 | 申请门槛 |
|------|-------------|---------|
| 🥉 Level 1 | **$25** 算力券 | `姓名_C2G_方案草案.md`（≥ 500 字） |
| 🥈 Level 2 | **$100** 算力券 | Level 1 通过 + 单点改进 RFC |
| 🥇 Level 3 | **$300** 算力券 + OpenAI 积分申请辅导 | Level 2 完成 + 组合优化 RFC |
| 💎 Level 4 | 独立谈（可对接 GPU 赞助商 / 学校集群 / OpenAI 官方） | Level 3 结果 + 英文 tech report |

**方案草案必答的 4 个问题：**

1. 你打算往哪个方向压 BPB？（tokenizer / optimizer / 架构 / 量化，**只选一个**）
2. 你凭什么觉得这个方向有效？引用 ≥ 1 篇论文或 ≥ 1 条 modded-nanoGPT 历史提交
3. 你的 $25 怎么花？预估跑几次实验、每次要看什么
4. 失败了怎么办？BPB 变差你的下一步是什么？

**为什么设这道门？** 因为 OpenAI / NVIDIA / Anthropic 的研究员就是这么工作的——他们在拿到 GPU 之前先写 research plan，经过 mentor 审核才开跑。**C2G 就是在训练你这个习惯。**

💸 其他算力来源（搭配使用）

| 方案 | 成本 | 备注 |
|------|------|------|
| **Elite20 Level 1 算力券** | $25（审核通过后发放） | 见上 |
| **OpenAI $1M 算力积分** | $0 | 申请制，本科生/应届生优先 |
| Lambda Cloud 8×H100 | ~$24/小时 | 按需 |
| AutoDL（国内） | ~¥150/小时 | A100 居多 |
| 学校集群 | $0 | 排队 |

**Level 2 → Level 3 自费总预算估算：$150–$500**（或 ¥1000–¥3500）

**省钱技巧：** 80% 的实验在单张 A100 上用 nanoGPT 小模型验证思路，最后只在 8×H100 上跑**最后 3 次提交**。

---

📎 需要提交什么

```
姓名_C2G_方案草案.md（算力申请用）  ← ≥500 字，无此项无法领算力券、无法入 Level 1
姓名_C2G_方案设计.md         ← 目标 Level + 技术选型 + 实验矩阵（草案基础上扩展）
姓名_C2G_train_gpt.py        ← 最终训练脚本
姓名_C2G_submission.tar.gz   ← 16MB artifact（代码+权重+tokenizer）
姓名_C2G_submission.json     ← BPB、训练时间、硬件、seed
姓名_C2G_logs/               ← 至少 3 个独立 seed 日志
姓名_C2G_ablation.md         ← 消融实验表
姓名_C2G_leaderboard.md      ← 你 vs baseline vs SOTA
姓名_C2G_AI日志.md（必须）    ← 无此项无法评审
姓名_C2G_拿来说明.md          ← 改了什么、为什么
（Level 4 额外）姓名_C2G_tech_report.pdf   ← 6+ 页英文技术报告
```

---

🚨 几个血的教训（先看再下场）

| 坑 | 避坑法 |
|---|--------|
| BPB 不稳定 | 至少 3 个 seed 取平均，报 ±stderr |
| 超 16MB 被拒 | 训练末尾自动检查 artifact 大小 |
| 10 分钟踩边 | 用 8:00 目标时间，留 20% buffer |
| 过拟合验证集 | 不要用 val 调超参，用 train loss |
| 量化后精度崩 | 只量化 embedding 和 output head，attention 保留 bf16 |
| Muon 不收敛 | 先读 Muon 原论文，理解 newton-schulz 迭代 |

---

⏰ 时间线

| 日期 | 做什么 |
|------|--------|
| **4/11（今天）** | Fork repo，开始写 `方案草案.md` |
| **4/11–4/13** | 提交方案草案 → 挑战组审核 |
| **4/13–4/14** | 通过后领 **$25 算力券** → 正式开跑 |
| 4/14–4/16 | Level 1：跑通 baseline |
| 4/17–4/20 | Level 2：单点改进 RFC → 领 $100 算力券 |
| 4/19–4/24 | Level 3：冲全球前 50 |
| 4/25–4/29 | Level 4（可选）：挑战 SOTA |
| **4/30** | **OpenAI 官方榜单截止** |
| 5/1 | 群内分享会 |

---

⚠️ 诚实预期

- **不是每个人都能打进前 20**（全球上千人参赛）
- **时间不是 0**（全力做需要 4 周，每天 4–8 小时）
- **成本不是 0**（至少 $150–$500 算力）

**但即使你只做到 Level 1，你已经：**
- 训过真正的语言模型
- 跑通了完整 LM pipeline
- 知道自己和全球顶尖水平的差距在哪

**这个挑战的真正价值**，不是奖金、不是 offer，而是让你**第一次从全球 AI 研究者的视角看自己**。

---

🔥 谁应该做 C2G？

✅ **应该做：**
- 你想进入顶级 AI 实验室做研究员 / ML 工程师
- 你已经跑过 nanoGPT 或训过任何小模型
- 你想用一个具体的数字证明自己的能力
- 你愿意为「比别人快 0.005 BPB」熬几个通宵

❌ **可以先跳过：**
- 你还没训过任何神经网络（先做 C4 / C4C）
- 你这学期同时要交 5 篇期末论文
- 你只想做「差不多就行」的项目（C2G 是极致主义者的游戏）

---

详细规范见群文件 **C2G.md**（24KB，写得很细，含所有级别、预算、自测决策树、三个真实招聘案例）。

**第一步：** Fork [openai/parameter-golf](https://github.com/openai/parameter-golf)，通读 README，理解 baseline 的结构。

**第二步：** 写 `姓名_C2G_方案草案.md`（≥ 500 字，回答 4 个门槛问题），提交给挑战组审核。

**第三步：** 审核通过后领 **$25 算力券**，正式开跑 Level 1。

**同时请在群里发一句话：** "我决定做 C2G，目标 Level [X]，方案方向是 [tokenizer / optimizer / 架构 / 量化]。" —— 这是一个公开承诺，帮你坚持下去。

有问题群里问。这个挑战难,但真的值得 🚀

---

> 💡 **最后一句话：**
> 这个比赛不保证你拿到 OpenAI offer，但它保证你成为一个真正理解 AI 的人。
> 去 Fork 那个 repo，开始你的第一次训练。
