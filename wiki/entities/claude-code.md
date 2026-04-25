---
title: Claude Code
aliases: ["Claude Code"]
type: entity
tags: [tool, agent, claude, anthropic]
created: 2026-04-24
updated: 2026-04-26
sources: [raw/papers/book1-claude-code.pdf, raw/papers/book2-comparing.pdf, wiki/sources/claude-code-slash-commands.md]
---

# Claude Code

Anthropic 出品的 AI 编程代理（CLI 工具），可在终端中读仓库、调工具、写代码、修改文件。

## 作为 Harness Engineering 样本

Claude Code 值得研究，因为它在实现上保持了工程克制：
- 没有假定模型会持续正确 → 用 [[query-loop|Query Loop]] 管理状态
- 没有假定工具调用天然安全 → 用 [[tool-permission-interruption|权限和调度]] 约束工具
- 没有假定上下文越多越好 → 引入 [[context-governance|memory、CLAUDE.md、compact]]
- 没有把错误视为偶发事件 → 为各种失败场景设计 [[error-and-recovery|恢复路径]]
- 没有把多代理等同于更强能力 → 把 [[multi-agent-verification|synthesis 和 verification 单独拆开]]

## 核心架构组件

| 组件 | 源码 | 职责 |
|---|---|---|
| Query Loop | `query.ts` | 执行循环与状态管理 |
| QueryEngine | `QueryEngine.ts` | 会话生命周期 |
| Tool Orchestration | `toolOrchestration.ts` | 工具调度与权限 |
| Compact | `compact.ts`, `autoCompact.ts` | 上下文压缩与恢复 |
| CLAUDE.md | `claudemd.ts` | 分层指令加载 |
| Forked Agent | `forkedAgent.ts` | 多代理与状态隔离 |

## 在本 wiki 中的角色

本 wiki 运行在 Claude Code 之上——Claude Code 既是研究对象，也是 [[llm-wiki-pattern|LLM Wiki 模式]] 的执行者。

## 日常使用

- [[claude-code-command-workflow|命令工作流]] — 9 个高频 slash command 串成的最小工作流

## 相关

- [[harness-engineering|Harness Engineering]]
- [[comparing-claude-code-codex|与 Codex 的比较]] — 两种 Harness 哲学
- [[codex|Codex]] — OpenAI 的 AI 编程代理
- [[obsidian|Obsidian]] — 本 wiki 的浏览端
- [[claude-code-slash-commands|破晓AI编程：8 个命令实操]]
