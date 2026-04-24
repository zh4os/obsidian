---
title: 并行化
aliases: ["并行化", "Parallelization Pattern"]
type: concept
tags: [agent, 设计模式, 性能优化]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 并行化

同时执行多个独立的 LLM 调用或子任务，再聚合结果。与 [[prompt-chaining|提示词链]] 的顺序执行互补——独立子任务并行处理，依赖步骤用链串联。

## 两种核心变体

- **分段处理（Sectioning）**：将任务分解为独立部分，同时交给不同 LLM 实例处理（如同时生成文章的不同章节）
- **投票机制（Voting）**：对同一输入运行多次 LLM 调用，通过多数投票或评分聚合提高结果可靠性

## 应用场景

- **文档分析**：同时对文档的不同部分进行总结、实体提取、情感分析
- **多角度评审**：多个 LLM 实例分别从安全性、性能、可读性角度审查代码
- **多源数据收集**：同时从多个 API 或数据库检索信息
- **内容安全检查**：并行运行多个安全过滤器（有害内容、偏见、合规性）
- **可靠性提升**：多次运行同一查询，投票选出最佳答案

## 实践建议

> 当任务可以分解为独立部分分别处理、需要通过多次评估提高可靠性、或需要从多个来源并行收集数据时，使用此模式。注意权衡延迟改善与 API 调用成本。

## 代码框架

书中示例使用 **LangChain / LangGraph** 和 **Google ADK**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 3 章
- [[prompt-chaining|提示词链]] — 并行处理独立子任务，链处理依赖步骤
- [[multi-agent-collaboration-pattern|多智能体协作]] — 多个 agent 并行工作是协作的一种形式
- [[resource-optimization-pattern|资源感知优化]] — 并行化需要考虑资源成本
