---
title: 上下文工程与Agent系统学习路线
date: 2026-10-22
type: 学习路线
tags: [AI学习, Context工程, Agent, 学习路线, 2026-10]
status: 待学习
---

# 🧭 上下文工程与Agent系统学习路线

> [!abstract] 一句话
> 从"优化单次对话的措辞（提示词）"升级到"**设计一套让 AI 在正确时间获得正确信息、并能自主执行任务的动态系统**"。
> 主线公式：**Prompt（如何说）→ Context（看到什么）→ Harness（系统级约束与验证）→ Agent Loop（自主执行循环）**
> 比喻：**模型是马，Harness（驾驭工程）是缰绳、马鞍与路**。对 Agent 而言，**大多数失败不是模型能力的失败，而是上下文的失败**。

> [!info] 定位
> 本笔记是 [[AI学习总览]] 模块三（Agent → Context 工程 → 记忆系统）的延伸路线图，2026-10-22 由豆包整理、补充并逐一核验。

---

## 一、核心认知框架（四层递进）

| 层级 | 关注问题 | 一句话 | 对应能力 |
|---|---|---|---|
| 1. Prompt | 如何说 | 措辞、角色、示例、格式约束 | 单次对话质量 |
| 2. Context | 看到什么 | 窗口内放什么信息、怎么放、何时放 | 信息选择与组织 |
| 3. Harness | 系统级约束与验证 | 围栏：权限、步数上限、输出校验、成本 | 可靠性 |
| 4. Agent Loop | 自主执行循环 | LLM → 判断 → 工具 → 结果回喂 → 循环到完成 | 自主完成任务 |

> 💡 越往上越值钱：上下文工程管"看到什么"，Harness 管"不出错"，Loop 管"能跑完"。

---

## 二、学习资源清单（2026-10-22 已逐一核验）

### 🎯 上下文工程（核心中的核心）

| 资源 | 定位 | 适合阶段 | 核验 |
|---|---|---|---|
| [`Corneldj/context-engineering`](https://github.com/Corneldj/context-engineering) | 2026 年更新的免费迷你课程，严格按 prompt→context→harness→loop 四层递进，共 9 个模块，适合当主干课 | 入门→进阶 | ✅ 88★，2026-08 更新 |
| [`sabernagato/Context-Engineering-Intro-ZH`](https://github.com/sabernagato/Context-Engineering-Intro-ZH) | 上下文工程入门模板（中文翻译版）：CLAUDE.md 定规则 + INITIAL.md 描述需求 → 自动生成 PRP 并执行，适合立刻落地 | 实战入门 | ✅ 56★ |
| [`nie2764/Context-Engineering`](https://github.com/nie2764/Context-Engineering) | Karpathy 启发的第一性原理手册：Token 预算、记忆系统、上下文修剪，含代码与可视化 | 进阶深入 | ✅ 存在（较新） |

### 🤖 Agent 系统与 Harness（从"能聊"到"能办"）

| 资源 | 定位 | 适合阶段 | 核验 |
|---|---|---|---|
| [`microsoft/ai-agents-for-beginners`](https://github.com/microsoft/ai-agents-for-beginners) | 微软官方免费入门课，15-18 节，配文章+视频+代码，零基础建立 Agent 整体认知 | 零基础入门 | ✅ 77.6k★，2026-10 更新 |
| [`datawhalechina/hello-agents`](https://github.com/datawhalechina/hello-agents) | Datawhale 中文实战，从零手写最小 Agent，代码结构清晰 | 实战入门 | ✅ 84.1k★，本地已有副本（test_1/hello-agents-1.0.3） |
| [`cdavid817/awesome-agent-tutorial`](https://github.com/cdavid817/awesome-agent-tutorial) | 《企业级 Agent 从入门到专家(2026)》：40 行最小 ReAct → 27 章增量构建到"安全/观测/评测/成本"生产四件套 | 进阶→生产级 | ✅ 30★ |
| [`sarkarsaurabh27/agent-loop-learning`](https://github.com/sarkarsaurabh27/agent-loop-learning) | Agent Loop 审计与最佳实践库：多 Agent 编排、上下文记忆（可提升 26% 准确率、减少 90% token）、安全权限 | 生产级优化 | ✅ 3★ |
| Harness 工程（原文未给链接） | 12 节课从零搭 Harness；三层工程体系、六层架构 | 系统化深入 | ⚠️ 原文无链接，见 3.6 |

### 🏗️ 综合参考与延伸

- [`arthaks/anthropic-engineering-guide`](https://github.com/arthaks/anthropic-engineering-guide)：中文 AI Agent 工程实践指南，主线 Prompt → Workflow → Agent → Context Engineering → Tool/Memory/Harness → MCP/Multi-Agent ✅
- [`rohitg00/ai-engineering-from-scratch`](https://github.com/rohitg00/ai-engineering-from-scratch)：Phase 14 含 42 节 Agent 工程（Loop/记忆/规划/基准测试/生产化），第一性原理 ✅ 72.2k★
- 在线课程：DeepLearning.AI 免费《Context Engineering》（约 9 小时，Chroma 合作）⚠️ 未核验到对应课程，见 3.4

---

## 三、豆包补充内容（2026-10-22）

### 3.1 概念补强：把"上下文"拆透

- **Context = AI 当下能看到的一切**：系统提示 + 检索结果 + 工具返回 + 对话历史 + 用户输入。
- 上下文工程三问：**放什么**（选择/裁剪）· **怎么放**（结构/格式/优先级）· **何时放**（时机/缓存/压缩）。
- 与 RAG 的关系：RAG 是"把外部知识送进上下文"的手段之一。**长上下文负责"想得深"，RAG 负责"找得对"**——呼应 [[AI学习总览]] 里"RAG 五代"的判断。
- Anthropic 官方三大实战技术（2025-09-29 文章）：**context compaction（上下文压缩）**、**structured note-taking（结构化笔记/记忆外置）**、**multi-agent（多智能体分工）**；另有 tool-result clearing（工具结果清理）。

### 3.2 Agent 四大失败模式与 Harness 对策

| 失败模式 | 表现 | Harness 对策 |
|---|---|---|
| 上下文腐烂 Context Rot | 信息过时、互相矛盾 | 定期压缩、重取、新鲜度检查 |
| 工具调用失误 | 结果不校验直接信 | 输出 Schema 校验 + 失败重试 |
| 死循环 | 没有终止条件 | 最大步数 + 观察者退出 |
| 权限越界 | 工具权限过大 | 最小权限 + 白名单 |

> 💡 这正是"生产四件套"：**安全 / 观测 / 评测 / 成本**（对应 awesome-agent-tutorial 的主线）。

### 3.3 评估先行（Eval 是工程的起点）

- 没有 Eval 就没有"可靠"，只有"看起来对"。
- 三件套：**黄金数据集**（golden set）→ **回归测试** → **轨迹审计**。
- 工具：promptfoo（评测）、LangSmith（可观测/追踪）、DeepEval、OpenAI Evals。

### 3.4 额外高价值资源（核验说明）

- ✅ **Anthropic《Effective context engineering for AI agents》**（2025-09-29）：上下文工程最重要的一手文章。https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
- ✅ Anthropic《Building effective agents》：workflows vs agents（[[AI学习总览]] 已收录）。
- ✅ DeepLearning.AI《Advanced Retrieval for AI with Chroma》（约 1h2m）确认存在。
- ⚠️ 原文所述"9 小时 Context Engineering 新课"**未查到对应课程，以官网为准**，不要花时间找。
- 概念延伸（进阶）：MemGPT（记忆管理）、GraphRAG（关系检索）、Prompt Caching（成本优化）。

### 3.5 跟你的场景结合（教育者视角）

- 你的**讲义流水线**就是天然的 Agentic 工作流：需求 → 检索讲义库（RAG）→ 生成 → 校验（Eval）→ 入库 → 复用。
- **Obsidian 就是你的"上下文仓库"**：把讲义/错题库做成检索源，是最贴近你的 Context Engineering 实验场。
- 抖音"独立老师 + AI 工具"IP：把最小 Agent 用 Streamlit 部署成演示，就是现成的内容素材。
- 节奏建议：每个 mini 项目完成 → **笔记进 Obsidian + 代码进 GitHub**（就是今天这套动作的延续）。

### 3.6 原文两处模糊引用的处理

- "12 节课从零搭 Harness"、"三层工程体系、六层架构"：原文无具体链接，疑似 AI 生成内容的模糊引用。**建议用 Anthropic 官方文章 + LangGraph/Temporal 文档补位，不必花时间考证出处**。

---

## 四、实践路径（4 周）

> 光看不动手，认知会停留在表面。用一个具体、有边界的小项目串联学习。

1. **第 1 周：用模板跑通上下文工程** — Clone `Context-Engineering-Intro-ZH`，为手头真实小功能（如"自动整理会议纪要并提取待办"）生成 PRP 并执行。
2. **第 2-3 周：手写一个最小 Agent Loop** — 不用框架，写 ≤50 行循环：`LLM → 判断是否调用工具 → 执行工具 → 结果喂回 LLM → 循环到完成`。核心公式：**Agent = LLM + Loop + Tools**。
3. **第 4 周起：引入 Harness 与评测思维** — 问生产级问题：调错工具怎么办？死循环怎么办？怎么衡量完成质量？读 `agent-loop-learning` 或 awesome-agent-tutorial 的"生产四件套"。

> 三步逻辑：**先用模板感受上下文的力量 → 再用最小循环理解 Agent 机制 → 最后用工程约束让它可靠**。

---

## 五、核验记录（2026-10-22，GitHub API）

| 仓库 | 星标 | 最后更新 | 状态 |
|---|---|---|---|
| datawhalechina/hello-agents | 84.1k | 2026-10 | ✅ |
| microsoft/ai-agents-for-beginners | 77.7k | 2026-10 | ✅ |
| rohitg00/ai-engineering-from-scratch | 72.2k | 2026-10-22 | ✅ |
| Corneldj/context-engineering | 88 | 2026-08 | ✅ |
| sabernagato/Context-Engineering-Intro-ZH | 56 | 2025-07 | ✅ |
| cdavid817/awesome-agent-tutorial | 30 | 2026-10 | ✅ |
| sarkarsaurabh27/agent-loop-learning | 3 | 2026-05 | ✅ |
| arthaks/anthropic-engineering-guide | 0（新） | 2026-07 | ✅ |
| nie2764/Context-Engineering | 0（新） | 2025-08 | ✅ |

---

## 六、关联笔记

[[AI学习总览]] · [[学习地图]] · [[Vibe Coding 学习]] · [[学习资源库]] · [[Git同步实操例程]]
