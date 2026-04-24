---
title: 学习与适应
aliases: ["学习与适应", "Learning and Adaptation Pattern"]
type: concept
tags: [agent, 设计模式, 自我改进]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 学习与适应

智能体从经验中改进自身行为的能力。不同于反思模式的单次输出改进，学习与适应关注的是跨任务、跨时间的持续改进——让 agent 变得越来越好。

## 关键方法

- **SICA（Self-Improving Coding Agent）**：自我改进编码智能体，通过代码执行反馈自动调优
- **AlphaEvolve / OpenEvolve**：通过进化算法不断优化提示词、代码或策略
- **经验积累**：将成功和失败的经验持久化，指导未来决策

## 应用场景

- **代码优化**：agent 通过反复运行和测试代码，逐步改进性能
- **提示词进化**：通过评估和变异不断优化提示词效果
- **策略调优**：基于过去的成功/失败案例调整行为策略
- **个性化学习**：根据用户反馈调整交互方式和输出风格

## 实践建议

> 当需要智能体持续改进性能、适应变化的环境或用户需求时，使用学习与适应模式。它超越了单次执行的优化。

## 代码框架

书中案例研究包括 **SICA**、**AlphaEvolve** 和 **OpenEvolve**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 9 章
- [[reflection-pattern|反思]] — 反思是单次改进，学习是持续改进
- [[evaluation-monitoring-pattern|评估与监控]] — 评估提供学习所需的反馈信号
- [[memory-management-pattern|记忆管理]] — 经验积累需要记忆支持
