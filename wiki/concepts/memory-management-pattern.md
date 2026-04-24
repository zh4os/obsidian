---
title: 记忆管理
aliases: ["记忆管理", "Memory Management Pattern"]
type: concept
tags: [agent, 设计模式, 状态管理]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 记忆管理

智能体的短期和长期记忆的存储与检索机制。LLM 本身是无状态的，每次调用从零开始。记忆管理让 agent 能够跨对话轮次保持上下文、跨会话积累知识、并随时间学习用户偏好。

## 记忆类型

- **Session（会话记忆）**：跟踪当前对话的历史，维持上下文连贯性
- **State（状态草稿本）**：会话过程中的工作状态、中间结果、待办事项
- **Memory（长期记忆）**：跨会话持久化的用户偏好、事实知识、历史交互摘要

## 实现方式

- **Google ADK**：Session（对话追踪）+ State（草稿本）+ MemoryService（长期知识）
- **LangChain / LangGraph**：多种记忆模块 + Vertex Memory Bank
- **向量数据库**：语义检索长期记忆

## 应用场景

- **个人助手**：记住用户偏好、历史请求、常用设置
- **客户服务**：跨会话追踪用户问题历史和解决方案
- **教育辅导**：记住学生的学习进度和薄弱环节
- **项目管理**：跨多次交互追踪项目状态和决策历史

## 实践建议

> 当智能体需要跨对话轮次或跨会话保持连贯性、积累知识或个性化服务时，使用记忆管理模式。

## 代码框架

书中示例使用 **Google ADK**（Session / State / MemoryService）和 **LangChain / LangGraph**（含 Vertex Memory Bank）。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 8 章
- [[context-governance|上下文治理]] — Harness Engineering 视角的上下文管理
- [[llm-wiki-pattern|LLM Wiki 模式]] — Wiki 本身就是一种长期记忆实现
- [[rag-pattern|知识检索（RAG）]] — RAG 是记忆检索的一种方式
