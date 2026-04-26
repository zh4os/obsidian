---
title: 错误与恢复
aliases: ["错误与恢复"]
type: concept
tags: [harness-engineering, claude-code, 可靠性]
created: 2026-04-24
updated: 2026-04-26
sources: [raw/papers/book1-claude-code.pdf]
---

# 错误与恢复

> 错误路径就是主路径。

## 核心洞察：执行叙事的一致性

错误恢复真正保护的，不只是错误本身，还有系统对自己行为的解释能力：
- 我刚才试图做什么
- 为什么没做成
- 我用了什么恢复路径
- 现在是继续、停止，还是换轨

> 解释能力一断，系统就会从工程对象退化成玄学对象。

## 恢复策略分层

| 场景 | 恢复路径 |
|---|---|
| **prompt too long** | 先 collapse drain → 再 reactive compact |
| **max output tokens** | 先提 cap → 再要求模型续写（不是 recap） |
| **自动 compact 失败** | 计数 + 熔断（circuit breaker） |
| **compact 自身爆了** | compact 也有降级修复路径 |
| **中断** | 补齐 synthetic tool_result，语义收尾 |

## 可迁移原则

- 错误恢复要分层，不要所有问题都打一把重锤
- 恢复逻辑必须防止自我回环
- 自动恢复需要计数和熔断
- 截断后的最佳恢复通常是续写，不是总结
- 一个不会收手的恢复系统，和一个不会恢复的系统一样危险

## 相关

- [[harness-engineering|Harness Engineering]]
- [[query-loop|Query Loop]]
- [[context-governance|上下文治理]]
- [[exception-handling-pattern|异常处理与恢复]] — 同主题的设计模式视角（Gulli 第 12 章）
- [[multi-agent-verification|多代理与验证]] — 错误与不确定性同源，验证常作为恢复入口
