# 16MB、10 分钟、8 张 H100 —— OpenAI 开出 $200,000 年薪，只为找到这样一群人

> **作者按：** 这是 2026 年最硬核的一场 AI 比赛。规则残酷到只有四句话，奖金却是你过去十年都没见过的形式——不是现金,是**一张直通 OpenAI 的门票**。

---

## 一、一个反常识的比赛

过去十年，如果你问任何一个 AI 研究者："训出顶级语言模型需要什么？"

答案永远只有两个字：**算力**。

GPT-4 用了 25,000 张 A100。Llama-3 用了 16,000 张 H100。DeepSeek-V3 用了 2,048 张 H800。每一次前沿突破的背后,都是**几千万美元的电费单**。

普通研究者？连门都进不去。

**但 2026 年 3 月,OpenAI 发了一个完全相反的比赛。**

这个比赛叫 **Parameter Golf**,规则只有四句话:

> - 所有人用同样的 **8 张 H100 SXM**
> - 所有人有同样的 **10 分钟**训练时间
> - 所有人的模型不能超过 **16 MB**(包括代码+压缩权重+tokenizer)
> - 比谁的模型在 FineWeb 验证集上的 **BPB(bits-per-byte)**最低

就这四句话。没了。

这就像高尔夫球——不是谁挥杆次数多谁赢,而是**谁用最少的杆数把球打进洞**。

**而这,正是 OpenAI 用来找人的方式。**

---

## 二、为什么 OpenAI 要搞这个比赛？

你可能会想:OpenAI 明明可以用无限算力训最好的模型,为什么要搞一个「拼极限约束」的比赛?

答案是:**他们不是在做科研,他们是在招聘。**

前沿 AI 实验室最缺的,不是算力——是**能在约束下快速迭代、客观衡量自己进步**的人。

这种人同时具备四种能力:

1. **架构能力** —— 能动 Transformer 的每一个模块
2. **系统能力** —— 能在 H100 上写出高效的训练代码
3. **优化理论** —— 懂优化器、学习率、量化的底层原理
4. **工程迭代速度** —— 一天能跑 10 个实验还不乱

这四项同时具备的人,在中美整个 AI 圈加起来可能都不到 **500 人**。

而 Parameter Golf 恰好把这四项能力**变成一个客观数字**——你的 BPB 值。

**没有背景包装。没有关系户。没有面试技巧。**
**你的能力就是你在榜单上的位置。**

---

## 三、真实发生过的案例——每一个都有公开链接

我必须诚实:Parameter Golf 本身是 2026 年 3 月才发布的新赛事,还没有最终的"谁拿到 offer"结果可以讲。但它的**直接前身**和**同类赛事**过去两年里已经产生过一串**真实的、可验证的**案例——每一个都有公开的 GitHub / 博客 / 论文链接。

### 前例一:Keller Jordan —— 一篇博客进 OpenAI

这是整个故事里最硬的一个例子,因为 Parameter Golf 本身就是从这里长出来的。

**2024 年,独立研究者 Keller Jordan 创建了一个叫 [modded-nanoGPT](https://github.com/KellerJordan/modded-nanogpt) 的项目**,目标是把 Andrej Karpathy 著名的 GPT-2 复现(原本需要 45 分钟)压缩到极致。他和社区协作,把训练时间一路压缩到 **3 分钟**。

在这个过程中,他发明了一个全新的优化器,叫 **Muon**。相比 AdamW,Muon 把 LM 训练速度提升了 **35%**。他在个人博客上发了一篇题为《[Muon: An optimizer for hidden layers in neural networks](https://kellerjordan.github.io/posts/muon/)》的文章。

**就凭这一篇博客——不是论文,不是 PhD,不是推荐信——他在 2024 年 12 月进入了 OpenAI。**

而且更关键的是:**OpenAI 的 Parameter Golf 赛事,本质上就是把 Keller Jordan 做的非官方 nanoGPT speedrun 制度化、官方化的版本**。你现在参加 C2G,相当于在 OpenAI 的主场复刻他走过的那条路——只是现在路被修得更清晰了。

### 前例二:Franz Louis Cesista —— 菲律宾独立研究者破 3 分钟纪录

**这是我最想让你听到的案例,因为它打破了"只有美国藤校生才能做这种事"的迷思。**

Franz Louis Cesista(网名 leloykun),一位来自菲律宾的独立研究者。他不是 MIT、不是 Stanford、不是任何你听说过的机构的博士生。

但他在 modded-nanoGPT speedrun 的竞争中,持续提交优化。2025 年 1 月,他[首次把训练时间压到 3 分钟以内](https://x.com/leloykun/status/1880301753213809016),创下 **2.933 分钟**的新纪录。这意味着用 $8/小时 的 8×H100 云实例,训练一个 GPT-2 级别的模型只需要 **$0.40**。

他还在 Muon 优化器的 Newton-Schulz 系数上做了进一步的 [1–2% 效率优化](https://leloykun.github.io/ponder/muon-opt-coeffs/)。他的研究博客被主流 ML 社区持续引用。他进入了全球 LM 训练前沿的核心贡献者圈子。

**他的所有简历优势,就是他公开发表的工作。没有推荐信。没有学历光环。没有关系网。**

这个案例对你的意义:**如果你不在藤校、不在北美、不在一线 AI 公司实习——Parameter Golf 可能是你离顶级 ML 研究最近的一次机会**。

### 前例三:MIT 的 Ekin Akyürek —— 把竞赛变成顶会论文

[ARC Prize 2024](https://arcprize.org/) 是 François Chollet(Keras 作者)发起的抽象推理挑战,总奖金 $100 万,吸引了全球 **1,430 支队伍**和 **17,789 次提交**。

MIT 博士生 **Ekin Akyürek** 和团队用一个叫"测试时训练"(Test-Time Training)的方法在 ARC 公开验证集上达到 **61.9%**——**匹配人类平均水平**。

他们获得了 **ARC Prize 2024 论文奖第 2 名**。论文[《The Surprising Effectiveness of Test-Time Training for Abstract Reasoning》](https://arxiv.org/abs/2411.07279)发表在 arXiv 上,被 ICML 和 NeurIPS 收录,开创了 LM 推理阶段的一个全新范式。

**这个案例说明:**顶级 ML 竞赛不只是招聘漏斗,也是**研究论文的孵化器**。你在 C2G 里做出的任何原创工作,都有可能变成一篇顶会论文。

### 前例四:NVIDIA KGMoN 团队 —— 竞赛徽章可以写进 JD

最后一个案例最直接。

**NVIDIA 内部有一个专门的研究团队**,叫 **KGMoN(Kaggle Grandmasters of NVIDIA)**,由 9 名 Kaggle Grandmaster 组成,由 Distinguished Engineer Jean-François Puget 领导。成员包括 Chris Deotte、Gilberto Titericz、Kazuki Onodera、Bojan Tunguz、Théo Viel、Bo Liu 等人。

**NVIDIA 公开发布过把"Kaggle Grandmaster"作为硬性要求的招聘 JD**。一个公开竞赛的排名——不是 PhD、不是 Stanford、不是任何你花十年磨出来的传统简历——就是入职通行证。

如果 Kaggle 排名可以写进 NVIDIA 的 JD,那么 OpenAI Parameter Golf 的全球榜单排名也完全可以成为同等甚至更强的信号——**尤其因为它直接测量的是 LM 训练能力本身,而不是在某个随机数据集上的 XGBoost 调参技巧**。

---

**四个案例的共同点:**

- 都有公开可验证的产出(代码 / 博客 / 论文 / 榜单排名)
- 都**不依赖**传统简历优势(学历、背景、人脉)
- 都经历了「做出工作 → 获得圈子关注 → 被顶级机构发现」这三步

**没有一个案例是「本科生 3 周内拿到 $250K offer」的爽文叙事。** 真实路径往往需要 6–12 个月的持续积累。

但它们证明了一件关键的事:**客观的技术工作,真的能打破传统的招聘漏斗。**

---

## 四、这件事离你有多远?

这是最多人问的问题。我来拆解一下。

### 硬件门槛

这是最容易被误解的部分。很多人看到「8 张 H100」就劝退。

**但实际上:**

- OpenAI 为这个比赛准备了 **$1,000,000 的算力积分**
- **重点支持对象:本科在校生、应届生、奥赛奖牌得主**
- 申请方式:在 GitHub repo 提 issue,附一份 500 字的研究计划

即使不申请官方积分,市场上的云 H100 价格是这样的:

| 平台 | 8×H100 单价 |
|------|------------|
| Lambda Cloud | ~$24/小时 |
| RunPod | ~$22/小时 |
| Vast.ai | ~$18/小时 |
| AutoDL(国内) | ~¥150/小时(A100 居多) |

**从 Level 1 跑到 Level 3,总算力成本大约 $150–$500 (¥1000–¥3500)。**

这是一顿好点的饭局的钱。换的是一次可能改变一生的机会。

### 时间门槛

全力做 Parameter Golf,大约需要 **4 周 × 每天 4–8 小时**。

但——

**你不需要从第一天就 all-in。** 可以先用两天跑通 baseline,看看自己是不是喜欢这种工作方式。喜欢了再加码。不喜欢也没关系,你至少已经学会了 LM 训练的完整 pipeline。

### 知识门槛

这是真正重要的门槛。C2G 不是给 ML 小白准备的。

**你至少需要:**

- 跑通过 `nanoGPT`(Andrej Karpathy 那个著名教程)
- 理解 Transformer 的 forward pass
- 会用 PyTorch 和 mixed precision
- 读过至少 3 篇 ML 论文

如果这些你都没有,不要硬上。**先做 Elite 20 的其他挑战打基础。**

但如果你有——**这是一个每十年才会出现一次的机会窗口**。

---

## 五、这个比赛到底在考什么?

我看过现在全球榜单前 10 的方案。它们的共同特点是——**每一个都只改了一两件事,但每一件都改得极其深入**。

让我翻译成人话。

### Baseline 是什么?

一个 9 层、512 维的 Transformer。用 1024 vocab 的 BPE tokenizer。AdamW 优化器。Flash Attention。

跑出来 **1.2244 BPB**。

这个数字代表:平均每一个字节的文本,你的模型需要 1.2244 比特才能编码出来。

### 当前榜首是什么?

当前第一名的方案叫 **SP8192 + 3-Layer Recurrence**,1.0810 BPB。

它只改了两件事:

1. **把 tokenizer 从 1024 BPE 换成 8192 SentencePiece**
    - 这一步让模型能看到更长的上下文,BPB 降 0.03
2. **在 Transformer 中间加了 3 层共享权重的 recurrence**
    - 用同样的参数量做了更多次计算,BPB 再降 0.03

就这两件事。**但为了让这两件事在 16MB 和 10 分钟的约束下都能 work,需要极深的理解。**

- Tokenizer 的 vocab 表本身就占空间,怎么在 16MB 里塞下 SP8192?
- Recurrence 会翻倍计算时间,怎么在 10 分钟里跑完?
- 两个改动组合起来会不会互相抵消?

**这些问题的答案,就是顶级 ML 工程师的日常思考。**

---

## 六、AI-First:用 AI 训 AI

这个比赛还有一个很有意思的特点:**你不用自己发明轮子,但你必须知道怎么用 AI 来帮你改轮子。**

正确的工作流是这样的:

```
1. 你有一个假设 → 问 Claude:"如果我把 norm 位置从 pre 改到 post, 
                    BPB 会怎么变? 有相关论文吗?"

2. Claude 给你 3 个参考文献 + 理论分析 + 预期改动幅度

3. 你花 15 分钟改代码 → 跑一次实验(10 分钟)

4. 看 loss 曲线 → 截图丢给 Claude: 
   "这个 grad norm 的尖峰是怎么回事? 怎么 debug?"

5. Claude 给你 5 个可能原因,你排查第 2 个 → 发现是 mixed precision 溢出

6. 修 fix → 再跑一次 → 写下结论

7. 一天跑 8–10 次这样的循环
```

这就是 2026 年顶级 ML 工程师的工作方式。**不是一个人闷头写代码,是一个人 + 一个 AI + 一条高速迭代流水线。**

Parameter Golf 的评分规则里明确要求提交 AI 使用日志——他们要招的,就是**会用 AI 来放大自己能力**的人。

---

## 七、一个不太舒服的真相

我必须告诉你一个不太舒服的真相。

**这个比赛不是大多数人的游戏。**

全球可能有 1,000 人参赛。前 20 名能直通顶级实验室,前 50 名能拿到推荐信,前 100 名可以在简历上写一笔。剩下的 900 人——什么都没有。

而你要知道,参赛的这 1,000 人,有美国常春藤的博士生,有中国清北的本科生,有印度 IIT 的天才,有英国剑桥的奥赛金牌。

**你要和他们正面竞争。**

但也正是因为这样,打进哪怕前 200 名,都是一个巨大的能力信号。

**而且你不打这一仗,你永远不会知道自己和世界顶尖水平的差距到底在哪里。**

---

## 八、如果你决定下场

如果看到这里你还没关掉这篇文章,说明你真的在考虑。那我给你一个具体的行动路径。

### 第一步:诚实自评

拿出纸笔,回答这 5 个问题:

1. 我能不能从零写一个 2 层 Transformer 的 forward pass?
2. 我知不知道 AdamW 和 Muon 的区别?
3. 我会不会用 PyTorch profiler 找训练瓶颈?
4. 我读过几篇 ML 训练相关的论文?
5. 我有没有 4 周、每天 4 小时的时间?

**全部答「是」:** 直接 Fork repo,从 Level 2 起步,目标 Level 3。

**答对 3 个:** Fork repo,从 Level 1 起步,目标 Level 2。

**答对 1–2 个:** 先花两周看 Karpathy 的 2 小时 [build-nanogpt 视频](https://www.youtube.com/watch?v=l8pRSuU81PU),再回来做 Level 1。

**一个都没答对:** 这个比赛现在不适合你。先做点基础的 LM 项目,明年再回来。

### 第二步:Fork 官方 repo,通读 README

```bash
git clone https://github.com/openai/parameter-golf.git
cd parameter-golf
pip install torch sentencepiece flash-attn --break-system-packages
python download_fineweb.py
```

**先别急着 `torchrun`。** 这一步只是让你把代码读明白,不是让你开跑。

### 第三步:写 **方案草案**(这一步就是真正的门槛)

> **C2G 的第一道门不是代码,是思考。**

即使是 Level 1 的 **$25 Elite20 赞助算力额度**,也**不是「报名就给」**。你必须先写一份 `姓名_C2G_方案草案.md`(≥ 500 字),提交给挑战组审核,通过之后才拿到算力券。

**方案草案必须回答这 4 个问题:**

1. **你打算把 baseline 从 1.2244 往哪个方向压?** tokenizer / optimizer / 架构 / 量化,**只选一个**。回答"都试试"的直接打回。
2. **你凭什么觉得这个方向有效?** 引用 ≥ 1 篇论文或 ≥ 1 条 modded-nanoGPT 历史提交,说明你读到的证据。
3. **你的 $25 怎么花?** 预估跑几次实验、每次要看什么指标。先跑 baseline 还是先用 A100 小尺寸验证?
4. **失败怎么办?** 如果你的改动让 BPB 变差,你的下一步是什么?这一条最能暴露一个人是否真的想清楚了。

**为什么要卡这道门?**

因为 OpenAI / Anthropic / NVIDIA 的研究员**就是这么工作的**。他们从来不是"先 `git clone` 再说",他们在拿到 GPU 之前先写 **research plan**,经过 mentor 审核才开跑。没人会在你说不清楚"打算怎么训"之前,把一台 $400,000 的 8×H100 交到你手上。

**C2G 是在训练你这个习惯本身。** 想清楚再动手——这是你未来 10 年 ML 职业生涯的第一课。

**小技巧:** 先用 Claude 把草案打磨 3 轮再交。草案通过后,你也可以复用它去 OpenAI `[compute request]` 申请官方 $1M 积分——这是你同一份思考的双重回报。

### 第四步:领算力券,跑通 baseline

用借来的或租的 8×H100,跑一次官方 baseline。看你能不能复现 1.2244 BPB。

**这一步就能刷掉一半的人。** 因为跑通一次官方代码,需要搞定 CUDA 环境、FlashAttention 编译、NCCL 通信、数据下载——每一步都能卡住你一整天。

### 第五步:选一个方向,做第一次改动

最推荐的第一个改动是 **把 tokenizer 从 BPE 1024 换成 SentencePiece 8192**。

理由:
- 改动集中在数据预处理,不动模型
- 历史上能降 0.03–0.05 BPB
- 让你熟悉「改一个东西 → 跑 3 次 → 看差值」的完整流程

### 第六步:建立你的实验矩阵

```
实验 001: baseline
实验 002: + SP8192 tokenizer
实验 003: + Muon optimizer
实验 004: + SP8192 + Muon
实验 005: + SP8192 + Muon + int6 embedding
...
```

每个实验跑 3 个 seed。记录均值和标准差。这就是 ML 工程师的日常。

### 第七步:提交,然后重复

把最好的方案整理成 `submission.tar.gz`,提交到官方榜单,看排名。

**然后回去改,再提交。再改,再提交。**

Parameter Golf 的比赛窗口一直开到 **4 月 30 日**。你有整整 20 天。

---

## 九、最后一句话

Parameter Golf 不保证你拿到 OpenAI 的 offer。

**它保证的是——你会变成一个真正理解 AI 的人。**

你会第一次亲手训出一个语言模型。你会第一次理解为什么 Chinchilla 法则那么重要。你会第一次看到 grad norm 的尖峰,然后自己把它 debug 出来。你会第一次明白什么叫「10 分钟的训练预算在最后 30 秒被 NCCL 通信吃掉」。

**这些东西,你读 100 篇论文都学不会。只有亲自下场打一次,你才真的懂。**

而一旦你懂了,不管这次比赛你是不是拿到了 offer——

**你已经不再是那个从外面张望 AI 的人了。**

**你已经在场内了。**

---

> **去 Fork 那个 repo。**
> **跑一次 baseline。**
> **看看自己能不能复现 1.2244。**
>
> **这是你离 OpenAI 最近的一次。**

---

### 📎 文末资源与参考来源

**赛事与前置:**

- **Parameter Golf 官方 repo:** https://github.com/openai/parameter-golf
- **modded-nanoGPT speedrun(前身):** https://github.com/KellerJordan/modded-nanogpt
- **前置教程 · Karpathy build-nanogpt:** https://www.youtube.com/watch?v=l8pRSuU81PU
- **Muon 优化器 repo:** https://github.com/KellerJordan/Muon
- **FlashAttention 3:** https://github.com/Dao-AILab/flash-attention
- **FineWeb 数据集:** https://huggingface.co/datasets/HuggingFaceFW/fineweb

**本文援引的真实案例来源:**

- **Keller Jordan 个人主页:** https://kellerjordan.github.io/
- **Muon 原始博客:** https://kellerjordan.github.io/posts/muon/
- **Franz Louis Cesista (leloykun) 主页:** https://leloykun.github.io/
- **破 3 分钟纪录公告:** https://x.com/leloykun/status/1880301753213809016
- **Ekin Akyürek 主页:** https://ekinakyurek.github.io/
- **TTT 论文 (ARC Prize 2024 Paper Award 第 2 名):** https://arxiv.org/abs/2411.07279
- **ARC Prize 官网:** https://arcprize.org/
- **NVIDIA KGMoN 官方页面:** https://www.nvidia.com/en-us/ai-data-science/kaggle-grandmasters/
- **H2O.ai Kaggle Grandmasters 团队:** https://h2o.ai/company/team/kaggle-grandmasters/

---

**Elite 20 AI+X Program · SIAS University**
**C2G — Parameter Golf · 截止 2026-04-30**

*写给那些不想被「AI 浪潮」淘汰,而是想成为这一波浪潮的人。*
