---
title: Wiki Overview
aliases: ["Wiki Overview"]
type: analysis
tags: [meta]
created: 2026-04-24
updated: 2026-04-28
sources: []
---

# Wiki Overview

这是一个基于 [[llm-wiki-pattern|LLM Wiki 模式]] 构建的个人多用途知识 wiki。[[claude-code|Claude Code]] 负责维护所有页面，用户在 [[obsidian|Obsidian]] 中浏览和策展。

## 当前规模

- **Sources**: 5 篇
- **Entities**: 7 个
- **Concepts**: 38 个
- **Analyses**: 9 篇

## 主题脉络

### 1. [[llm-wiki-pattern|LLM Wiki 模式]]
用 LLM 增量构建持久化知识库，替代传统 [[rag|RAG]]。本 wiki 自身就是这一模式的实践。

### 2. [[harness-engineering|Harness Engineering]]
围绕不稳定模型设计控制结构的工程方法。从 [[claude-code|Claude Code]] 源码提炼，涵盖 [[query-loop|Query Loop]]、[[tool-permission-interruption|工具权限]]、[[context-governance|上下文治理]]、[[error-and-recovery|错误恢复]]、[[multi-agent-verification|多代理验证]]、[[team-adoption|团队落地]]。

### 3. Harness 哲学比较
[[comparing-claude-code-codex|Claude Code vs Codex]]：运行时纪律 vs 显式控制层，殊途同归。

### 4. [[agentic-design-patterns|智能体设计模式]]
21 种 Agent 设计模式百科，每种模式均有独立概念页：
- **基础模式**：[[prompt-chaining|提示词链]]、[[routing-pattern|路由]]、[[parallelization-pattern|并行化]]、[[reflection-pattern|反思]]
- **能力扩展**：[[tool-use-pattern|工具使用]]、[[planning-pattern|规划]]、[[reasoning-pattern|推理技术]]、[[memory-management-pattern|记忆管理]]
- **协作与通信**：[[multi-agent-collaboration-pattern|多智能体协作]]、[[human-in-the-loop-pattern|人机协同]]、[[mcp-pattern|MCP 协议]]、[[a2a-pattern|A2A 通信]]
- **治理与安全**：[[guardrails-pattern|安全护栏]]、[[exception-handling-pattern|异常处理]]、[[goal-monitoring-pattern|目标监控]]、[[evaluation-monitoring-pattern|评估与监控]]
- **高级主题**：[[learning-adaptation-pattern|学习与适应]]、[[rag-pattern|知识检索]]、[[resource-optimization-pattern|资源优化]]、[[prioritization-pattern|优先级排序]]、[[exploration-discovery-pattern|探索与发现]]

### 5. Claude Code 实操工作流
[[claude-code-command-workflow|9 个 slash command 的最小工作流]]：把 [[harness-engineering|Harness]] 理念落到 `/clear`、`/compact`、`/context`、`/diff` 等具体命令。来源 [[poxiao-ai|破晓AI编程]] 公众号文章。

### 6. 记忆管理深度专题
围绕 [[memory-management-pattern|记忆管理]] 的 7 篇深度分析，覆盖应用实践层面的关键张力：
- **[[memory-write-strategy|写入策略]]**：信号 vs 噪音，隐式/显式分流，"不该被记的清单"
- **[[memory-staleness-and-forgetting|遗忘与陈旧]]**：失效机制对比，记忆 vs git 的边界，陈旧记忆的不对称伤害
- **[[memory-vs-long-context|长上下文 vs 长期记忆]]**：百万 token 没让记忆失效，反而把它推向工程化治理
- **[[memory-as-attack-surface|记忆作为攻击面]]**：长期化 prompt injection、可信源四级分级、冲突解决 fallback
- **[[memory-evaluation|记忆系统的评估]]**：缺乏公开 ablation 的领域，何时反而有害
- **[[memory-vs-workflow-state|记忆 vs 工作流状态]]**：常被混淆的两种持久化，按相似度 vs 按位置访问的判据
- **[[memory-granularity-and-timing|粒度与时机]]**：原子配即时、叙事配延迟，叙事是权威源、原子是投影

## 使用方式

| 操作 | 触发方式 | 说明 |
|---|---|---|
| **Ingest** | `ingest raw/articles/xxx.md` | 将素材整合进 wiki |
| **Query** | 直接提问 | 基于 wiki 知识回答 |
| **Lint** | `lint` | wiki 健康检查 |
