---
title: Query 工作流 vs Query Loop
type: analysis
tags: [comparison, workflow, harness-engineering, llm-wiki]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md, raw/papers/book1-claude-code.pdf]
---

# Query 工作流 vs Query Loop

本 wiki 中有两个带 "Query" 的概念：[[query-workflow|Query 工作流]]和 [[query-loop|Query Loop]]。它们同名但不同层——一个是**认知工作流**，一个是**执行基础设施**。

## 区别

| 维度 | [[query-workflow\|Query 工作流]] | [[query-loop\|Query Loop]] |
|------|----------------|------------|
| 来源 | [[llm-wiki-pattern\|LLM Wiki 模式]]（Karpathy） | [[harness-engineering\|Harness Engineering]]（Claude Code） |
| 层次 | 知识库消费流程（应用层） | 代理系统的执行心跳（运行时层） |
| 关注 | 读 index → 读页面 → 综合答案 → 存 analyses | 输入治理、流式消费、中断补齐、终止语义 |
| 产物 | Markdown 页面 / wikilink 引用 | 跨轮 State、tool_result 闭环 |
| 本质 | 一种 [[rag\|RAG]] 实践 | 一个可恢复的控制循环 |

## 关联

### 纵向依赖：应用运行在基础设施之上

LLM Wiki 的 Query 工作流**运行在** Query Loop 之上。当用户问一个问题时：

- **Query 工作流**定义"做什么"：读 `index.md`、读相关页面、综合答案、可能存入 `analyses/`。
- **Query Loop** 决定"怎么把这些动作稳定跑完"：每一次 `Read` 工具调用都发生在 Query Loop 的一个迭代里，Loop 负责把工具调用、权限检查、结果注入、跨轮 State 管理编排成可中断、可恢复的执行过程。

换句话说，Query 工作流是用户能感知到的工作模式，Query Loop 是用户看不到的运行时结构。

### 抽象对照：不同切面的 RAG

- **Query 工作流**：人机协作式的**显式 RAG**——人类提问，LLM 根据 wiki 索引做检索-综合-回答，产物是可复用的 Markdown 分析页。
- **Query Loop**：agent 自主调用工具时的**隐式 RAG 骨架**——模型一边推理一边决定要检索什么、调什么工具，Loop 保证这个"推理-检索-行动"的循环不会因为中断或失败而崩溃。

两者都是 [[rag-pattern|RAG]] 家族的实例，只是一个强调知识库结构，一个强调运行时结构。

### 共同设计哲学：结构化才能累积

两者都体现了"结构化流程 > 自由即兴"的思路：

- Query 工作流要求每个回答都可追溯到 wiki 页面、可选择性沉淀为 analyses，让**知识**复利累积。
- Query Loop 要求每一轮执行都有明确的 State、终止语义和账本，让**执行能力**可审计、可恢复。

## 一句话总结

> **Query 工作流是知识库层的"读者行为"，Query Loop 是 agent harness 层的"运行时心跳"；前者是后者承载的众多任务之一。**

## 相关

- [[query-workflow|Query 工作流]]
- [[query-loop|Query Loop]]
- [[llm-wiki-pattern|LLM Wiki 模式]]
- [[harness-engineering|Harness Engineering]]
- [[rag|RAG]]
- [[rag-pattern|知识检索（RAG）]]
