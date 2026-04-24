---
title: 多智能体协作
aliases: ["多智能体协作", "Multi-Agent Collaboration Pattern"]
type: concept
tags: [agent, 设计模式, 多智能体]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 多智能体协作

多个专用 agent 分工协作完成复杂任务。每个 agent 拥有特定的角色、专业知识和工具集，通过协调器或通信协议组织协作。这模拟了人类团队的分工模式——不同专家各司其职，协同解决单个个体难以独立完成的问题。

## 协作结构

- **层级式（Hierarchical）**：协调器 agent 分配任务给专用子 agent，汇总结果
- **顺序式（Sequential）**：agent 之间按顺序传递工作，如流水线
- **并行式（Parallel）**：多个 agent 同时处理不同方面，最后汇合
- **对等式（Peer-to-Peer）**：agent 之间直接通信协商

## 应用场景

- **软件开发团队**：架构师 + 开发者 + 测试员 + 审查者 agent 协作
- **研究分析**：搜索 agent + 分析 agent + 写作 agent 协作
- **内容创作**：策划 + 写手 + 编辑 + 事实核查 agent 协作
- **客户服务**：前台路由 + 各专业领域 agent 协作

## 实践建议

> 当单个 agent 无法有效处理任务的所有方面、任务可以自然地分解为不同专业领域、或需要多视角评估时，使用多智能体协作模式。

## 代码框架

书中示例使用 **CrewAI** 和 **Google ADK**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 7 章
- [[routing-pattern|路由]] — 路由是多智能体系统中的调度机制
- [[parallelization-pattern|并行化]] — 多 agent 并行是协作的一种形式
- [[a2a-pattern|智能体间通信（A2A）]] — agent 间标准通信协议
- [[multi-agent-verification|多代理与验证]] — Harness Engineering 视角的多 agent 验证
