---
title: Codex
aliases: ["Codex"]
type: entity
tags: [tool, agent, openai]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book2-comparing.pdf]
---

# Codex

OpenAI 出品的 AI 编程代理。与 [[claude-code|Claude Code]] 同属"把模型放进工程环境"的系统。

## Harness 设计哲学

Codex 代表一种**显式控制面优先**的驯化路线：
- 把 instruction fragment、thread、rollout、state bridge、exec policy 等结构做成显式、可组合、可序列化的模块
- 连续性寄托在 thread 和状态基础设施上，而非主循环
- 权限治理通过策略语言（policy language）实现

核心源码模块：`core/src/lib.rs`、`instructions/src/fragment.rs`、`execpolicy/src/lib.rs`、`sdk/typescript/src/thread.ts`

## 与 Claude Code 的对比

参见 [[comparing-claude-code-codex|Claude Code 和 Codex 的 Harness 设计哲学]]

## 相关

- [[claude-code|Claude Code]]
- [[harness-engineering|Harness Engineering]]
