---
title: MCP 协议
aliases: ["MCP 协议", "Model Context Protocol"]
type: concept
tags: [agent, 设计模式, 协议, 标准化]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# MCP 协议

模型上下文协议（Model Context Protocol），一种标准化的模型与工具之间的通信协议。MCP 将工具使用从特定框架的实现中解耦出来，提供统一的接口标准，使任何支持 MCP 的客户端都可以连接任何 MCP 服务器提供的工具。

## MCP vs 工具函数调用

| | 工具函数调用 | MCP |
|---|---|---|
| 标准化 | 各框架各自实现 | 统一协议标准 |
| 可移植性 | 工具绑定特定框架 | 工具可跨框架复用 |
| 服务发现 | 手动配置 | 动态发现 |
| 生态系统 | 封闭 | 开放 |

## 核心组件

- **MCP Server**：暴露工具的服务端（如 FastMCP）
- **MCP Client**：连接服务端的客户端（如 ADK、Claude Code）
- **MCPToolset**：框架集成层，将 MCP 工具暴露给智能体

## 应用场景

- **工具生态共享**：构建一次 MCP 服务器，多个 agent 框架都可使用
- **企业工具集成**：统一暴露企业内部 API 为 MCP 工具
- **跨框架互操作**：不同智能体框架通过 MCP 共享工具能力

## 实践建议

> 当需要构建可复用、可移植的工具集，或需要不同框架的 agent 共享相同工具时，使用 MCP 协议。

## 代码框架

书中示例使用 **Google ADK**（MCPToolset + ADK Web）和 **FastMCP**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 10 章
- [[tool-use-pattern|工具使用]] — MCP 是工具使用的标准化协议层
- [[a2a-pattern|智能体间通信（A2A）]] — A2A 是 agent 间通信，MCP 是 agent 与工具间通信
- [[claude-code|Claude Code]] — Claude Code 原生支持 MCP
