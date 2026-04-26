---
title: 工具权限与中断
aliases: ["工具权限与中断"]
type: concept
tags: [harness-engineering, claude-code, 安全]
created: 2026-04-24
updated: 2026-04-26
sources: [raw/papers/book1-claude-code.pdf]
---

# 工具权限与中断

> 一旦模型开始调用工具，问题的性质就变了。工具不是意见，工具是动作。

## 核心原则：权限先于能力

Claude Code 把工具变成**受管执行接口**，避免让模型直接碰世界。

### 权限语义三分叉

| 语义 | 含义 |
|---|---|
| **allow** | 自动允许 |
| **ask** | 需要用户确认 |
| **deny** | 拒绝执行 |

### Bash 的特殊待遇

Bash 永远比别的工具更可疑——因为它能做的事情最多、后果最不可控。Claude Code 对 Bash 实施特殊高压治理。

## 中断是一等语义

中断不只是"用户不想看了"，而是一次需要正确收尾的状态转移：
- `query.ts` 中断时补齐 synthetic tool_result
- `compact.ts` 处理被用户按 Esc 的 compact

## 相关

- [[harness-engineering|Harness Engineering]]
- [[query-loop|Query Loop]]
- [[error-and-recovery|错误与恢复]]
- [[human-in-the-loop-pattern|人机协同]] — `ask` 语义就是人在环里的具体形态
- [[guardrails-pattern|安全护栏]] — 权限是结构化护栏，护栏是策略层延伸
