---
title: "智能体设计模式（双语版）"
aliases: ["智能体设计模式（双语版）"]
type: source
tags: [agent, 设计模式, llm, 双语]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 智能体设计模式（双语版）

作者：Antonio Gulli。570 页，21 章，中英双语。系统性地介绍了 LLM 智能体的 21 种设计模式，每种模式包含概述、应用场景、代码示例（LangChain / Google ADK / CrewAI）、关键要点。

## 21 种设计模式

| # | 模式 | 说明 |
|---|---|---|
| 1 | [[prompt-chaining|提示词链]] | 将复杂任务分解为顺序步骤，每步的输出作为下步的输入 |
| 2 | [[routing-pattern|路由]] | 根据输入类型将请求分发到不同的专用处理路径 |
| 3 | [[parallelization-pattern|并行化]] | 同时执行多个独立子任务，再聚合结果 |
| 4 | [[reflection-pattern|反思]] | 让模型审视和改进自己的输出 |
| 5 | [[tool-use-pattern|工具使用]] | 通过函数调用扩展模型能力（API、数据库、搜索） |
| 6 | [[planning-pattern|规划]] | 制定多步计划再逐步执行 |
| 7 | [[multi-agent-collaboration-pattern|多智能体协作]] | 多个专用 agent 分工协作 |
| 8 | [[memory-management-pattern|记忆管理]] | 短期/长期记忆的存储与检索 |
| 9 | [[learning-adaptation-pattern|学习与适应]] | 从经验中改进行为（如 SICA、AlphaEvolve） |
| 10 | [[mcp-pattern|MCP 协议]] | 标准化的模型-工具通信协议 |
| 11 | [[goal-monitoring-pattern|目标设定与监控]] | 设定目标并跟踪进展 |
| 12 | [[exception-handling-pattern|异常处理与恢复]] | 错误检测、降级和恢复策略 |
| 13 | [[human-in-the-loop-pattern|人机协同]] | 在关键决策点引入人类判断 |
| 14 | [[rag-pattern|知识检索（RAG）]] | 检索外部知识增强生成 |
| 15 | [[a2a-pattern|智能体间通信（A2A）]] | Agent-to-Agent 标准通信协议 |
| 16 | [[resource-optimization-pattern|资源感知优化]] | 根据资源约束调整策略 |
| 17 | [[reasoning-pattern|推理技术]] | Chain-of-Thought 等增强推理方法 |
| 18 | [[guardrails-pattern|安全护栏]] | 输入/输出过滤、内容安全 |
| 19 | [[evaluation-monitoring-pattern|评估与监控]] | 系统性能评估和运行时监控 |
| 20 | [[prioritization-pattern|优先级排序]] | 任务优先级和资源分配 |
| 21 | [[exploration-discovery-pattern|探索与发现]] | 自主探索未知领域 |

## 代码框架覆盖

书中示例覆盖多个主流 Agent 框架：
- **LangChain / LangGraph**
- **Google ADK (Agent Developer Kit)**
- **CrewAI**
- **OpenAI API**

## 与本 wiki 其他内容的关系

- [[harness-engineering|Harness Engineering]] 关注的是"如何约束 agent"，本书关注的是"agent 能做什么"——两者互补
- 第 5 章工具使用、第 12 章异常处理与 [[tool-permission-interruption|工具权限与中断]]、[[error-and-recovery|错误与恢复]] 直接对应
- 第 8 章记忆管理与 [[context-governance|上下文治理]] 相关
- 第 14 章 RAG 与 [[rag|RAG]]、[[llm-wiki-pattern|LLM Wiki 模式]] 形成对比

## 相关

- [[antonio-gulli|Antonio Gulli]]
- [[harness-engineering|Harness Engineering]] — 互补视角
