---
title: 推理技术
aliases: ["推理技术", "Reasoning Techniques Pattern"]
type: concept
tags: [agent, 设计模式, 推理, 思维链]
created: 2026-04-24
updated: 2026-04-26
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 推理技术

增强 LLM 推理能力的方法集合。包括 Chain-of-Thought（思维链）、Tree of Thoughts（思维树）、Self-Consistency（自洽性）等技术，让模型在回答前进行更深入的思考，显著提高复杂任务的准确性。

## 核心技术

- **Chain-of-Thought (CoT)**：要求模型展示推理步骤，"让我一步步思考"
- **Self-Consistency**：多次采样推理路径，选择最一致的答案
- **Tree of Thoughts (ToT)**：探索多条推理分支，评估选择最佳路径
- **Scaling Inference Law（推理扩展定律）**：增加推理时的计算量可以提升性能

## 应用场景

- **数学与逻辑**：复杂数学证明、逻辑推理
- **代码推理**：理解复杂代码逻辑、调试分析
- **策略规划**：需要多步前瞻的决策场景
- **科学分析**：需要严谨推导的科学问题

## 智能体的思考过程

不同 LLM 有不同的内置推理机制——有的通过显式思维链（如 Claude 的 extended thinking），有的通过隐式优化。理解这些差异有助于选择合适的推理策略。

## 实践建议

> 对于需要多步推理的复杂任务，始终使用推理增强技术。CoT 是最基础也最有效的方法。

## 代码框架

书中提供了实践代码示例。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 17 章
- [[planning-pattern|规划]] — 推理是规划的基础
- [[reflection-pattern|反思]] — 反思本身是一种推理过程
- [[prompt-chaining|提示词链]] — CoT 可融入链的每个步骤
- [[exploration-discovery-pattern|探索与发现]] — ToT 等推理本质上是带评估的探索
