---
title: Wiki Overview
aliases: ["Wiki Overview"]
type: analysis
tags: [meta]
created: 2026-04-24
updated: 2026-04-24
sources: []
---

# Wiki Overview

这是一个基于 [[llm-wiki-pattern|LLM Wiki 模式]] 构建的个人多用途知识 wiki。[[claude-code|Claude Code]] 负责维护所有页面，用户在 [[obsidian|Obsidian]] 中浏览和策展。

## 当前规模

- **Sources**: 4 篇
- **Entities**: 6 个
- **Concepts**: 15 个
- **Analyses**: 0 篇

## 主题脉络

### 1. [[llm-wiki-pattern|LLM Wiki 模式]]
用 LLM 增量构建持久化知识库，替代传统 [[rag|RAG]]。本 wiki 自身就是这一模式的实践。

### 2. [[harness-engineering|Harness Engineering]]
围绕不稳定模型设计控制结构的工程方法。从 [[claude-code|Claude Code]] 源码提炼，涵盖 [[query-loop|Query Loop]]、[[tool-permission-interruption|工具权限]]、[[context-governance|上下文治理]]、[[error-and-recovery|错误恢复]]、[[multi-agent-verification|多代理验证]]、[[team-adoption|团队落地]]。

### 3. Harness 哲学比较
[[comparing-claude-code-codex|Claude Code vs Codex]]：运行时纪律 vs 显式控制层，殊途同归。

### 4. [[agentic-design-patterns|智能体设计模式]]
21 种 Agent 设计模式百科：提示词链、路由、并行化、反思、工具使用、规划、多智能体协作、记忆管理、MCP、RAG、A2A 等。

## 使用方式

| 操作 | 触发方式 | 说明 |
|---|---|---|
| **Ingest** | `ingest raw/articles/xxx.md` | 将素材整合进 wiki |
| **Query** | 直接提问 | 基于 wiki 知识回答 |
| **Lint** | `lint` | wiki 健康检查 |
