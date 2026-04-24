---
title: 规划
aliases: ["规划", "Planning Pattern"]
type: concept
tags: [agent, 设计模式, 推理]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 规划

让智能体在执行前制定多步计划，而非直接行动。面对复杂任务时，智能体先分析目标、分解子任务、确定执行顺序和依赖关系，然后逐步执行计划。这使得 agent 能够处理需要深度推理和长期策略的任务。

## 核心能力

- **目标分解**：将高层目标拆分为可执行的子任务序列
- **依赖分析**：识别子任务之间的先后依赖关系
- **动态调整**：执行过程中根据反馈调整计划
- **深度研究**：与 Google DeepResearch、OpenAI Deep Research API 等深度研究工具结合

## 应用场景

- **复杂研究任务**：制定研究计划 → 分步检索 → 综合分析
- **项目管理**：拆解项目为里程碑和可执行步骤
- **旅行规划**：综合考虑预算、偏好、时间等多维约束
- **代码工程**：架构设计 → 模块划分 → 逐步实现

## 实践建议

> 当任务需要多步推理、涉及多个相互依赖的子任务、或需要长期策略时，使用规划模式。

## 代码框架

书中示例使用 **CrewAI**、**Google DeepResearch** 和 **OpenAI Deep Research API**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 6 章
- [[prompt-chaining|提示词链]] — 计划确定后通过链执行
- [[reasoning-pattern|推理技术]] — 推理是规划的基础能力
- [[goal-monitoring-pattern|目标设定与监控]] — 监控计划的执行进度
