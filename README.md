# 上下文工程与Agent系统学习路线

> 从"提示词"转向"上下文与 Agent 系统"的系统学习路线图。
> 2026-10-22 整理并核验（豆包整理，豪哥学习库同步）。

## 内容

- `上下文工程与Agent系统学习路线.md`：完整学习路线（四层框架 / 资源清单 / 补充 / 4 周实践 / 核验记录）
- 主线：**Prompt（如何说）→ Context（看到什么）→ Harness（系统级约束与验证）→ Agent Loop（自主执行循环）**
- 核心理念：模型是马，Harness 是缰绳、马鞍与路；大多数 Agent 失败不是模型能力的失败，而是上下文的失败。

## 学习资源速览

| 领域 | 推荐起点 |
|---|---|
| 上下文工程 | Corneldj/context-engineering（主干课）· sabernagato/Context-Engineering-Intro-ZH（模板落地） |
| Agent 入门 | microsoft/ai-agents-for-beginners · datawhalechina/hello-agents（中文实战） |
| 生产级 | cdavid817/awesome-agent-tutorial · sarkarsaurabh27/agent-loop-learning |
| 综合参考 | arthaks/anthropic-engineering-guide · rohitg00/ai-engineering-from-scratch |

## 实践路径

1. **第 1 周**：用模板跑通上下文工程（Context-Engineering-Intro-ZH）
2. **第 2-3 周**：手写 ≤50 行 Agent Loop（Agent = LLM + Loop + Tools）
3. **第 4 周起**：引入 Harness 与评测（安全 / 观测 / 评测 / 成本）
