---
title: 智能体间通信（A2A）
aliases: ["智能体间通信（A2A）", "Inter-Agent Communication", "A2A Pattern"]
type: concept
tags: [agent, 设计模式, 协议, 通信]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 智能体间通信（A2A）

Agent-to-Agent 标准通信协议，让不同框架、不同组织构建的智能体能够互相发现、协商和协作。A2A 解决的是异构 agent 系统之间的互操作性问题。

## A2A 核心概念

- **Agent Card**：agent 的能力描述卡片，用于服务发现
- **Task**：agent 间协作的基本单元
- **Message**：agent 间通信的消息格式
- **Artifact**：任务执行产生的输出物

## A2A vs MCP

| | A2A | MCP |
|---|---|---|
| 通信对象 | Agent ↔ Agent | Agent ↔ Tool |
| 目的 | 智能体间协作 | 智能体使用工具 |
| 抽象层级 | 任务级别 | 函数调用级别 |
| 互补性 | 两者互补，可同时使用 | |

## 应用场景

- **跨组织协作**：不同公司的 agent 通过 A2A 协议协作
- **异构系统集成**：不同框架构建的 agent 互操作
- **agent 市场**：agent 能力的标准化发布和发现
- **分布式智能体系统**：大规模 agent 网络的通信基础设施

## 实践建议

> 当需要不同来源、不同框架的智能体进行互操作时，使用 A2A 协议。

## 代码框架

书中提供了实践代码示例。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 15 章
- [[mcp-pattern|MCP 协议]] — MCP 管 agent-tool 通信，A2A 管 agent-agent 通信
- [[multi-agent-collaboration-pattern|多智能体协作]] — 协作需要通信协议支持
