---
title: Query Loop
aliases: ["Query Loop"]
type: concept
tags: [harness-engineering, claude-code, 系统设计]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# Query Loop

代理系统的心跳。不是单次问答，而是一个跨轮的、可恢复的执行循环。

## 核心职责

1. **治理输入** — 在调用模型之前，先对输入做大段治理逻辑
2. **流式消费** — 把模型输出当事件流处理，而非当最终文案
3. **中断补齐** — 中断时为已发出但未完成的工具生成 synthetic tool_result，保持执行账本闭环
4. **区分终止语义** — 完成、失败、恢复、继续是四种不同状态

## 成熟心跳的条件

- 有明确的跨轮状态
- 能治理输入，不只是被动消费
- 能流式承接模型输出
- 能补齐中断后的执行账本
- 能区分完成、失败、恢复和继续

> 缺少这些结构的系统，也许仍然能做出漂亮 demo，但它们更接近一次性表演，而不是运行时。

## Claude Code 实现

- `query.ts` — 用显式 State 管理跨轮执行状态
- `QueryEngine.ts` — 管理 conversation 的 query lifecycle，一个 QueryEngine 对应一个 conversation

## 相关

- [[harness-engineering|Harness Engineering]]
- [[error-and-recovery|错误与恢复]] — Query Loop 的恢复分支
- [[tool-permission-interruption|工具权限与中断]] — Query Loop 碰到外部世界的地方
- [[query-workflow|Query 工作流]] — LLM Wiki 的 Query 工作流是 Query Loop 的上层应用
