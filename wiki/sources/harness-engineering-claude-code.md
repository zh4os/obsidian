---
title: "Harness Engineering: Claude Code 设计指南"
aliases: ["Harness Engineering: Claude Code 设计指南"]
type: source
tags: [harness-engineering, claude-code, agent, 系统设计, 工程原则]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# Harness Engineering: Claude Code 设计指南

来源：agentway.dev，2026-04-01，rev 37dfc2，共 88 页（9 章 + 3 附录）

## 核心立场

> Prompt 决定它怎么说话，Harness 决定它怎么做事。

这本书不讨论"模型会不会写代码"，而讨论"一个会写代码的模型被放进终端、仓库和团队流程以后，怎样才不会把系统带偏"。核心概念是 **[[harness-engineering|Harness Engineering]]**：围绕不稳定模型设计一组持续生效的控制结构，约束其在工程环境中的行为边界。

## 全书结构

| 章 | 主题 | 核心原则 |
|---|---|---|
| 1 | 为什么需要 Harness | 模型是不稳定部件，系统必须围绕这个事实设计 |
| 2 | [[prompt-as-control-plane|Prompt 作为控制面]] | Prompt 是分层的控制面，不是人格包装 |
| 3 | [[query-loop|Query Loop]] | 代理系统的心跳：可恢复的执行循环 |
| 4 | [[tool-permission-interruption|工具权限与中断]] | 工具是受管执行接口，权限先于能力 |
| 5 | [[context-governance|上下文治理]] | 上下文是工作内存，需要预算管理 |
| 6 | [[error-and-recovery|错误与恢复]] | 错误路径就是主路径 |
| 7 | [[multi-agent-verification|多代理与验证]] | 用分工和验证管理不确定性 |
| 8 | [[team-adoption|团队落地]] | 团队制度比个人技巧重要 |
| 9 | [[harness-ten-principles|Harness Engineering 十条原则]] | 全书压缩 |

## 关键洞察

1. **模型是最不稳定的部件** — Claude Code 没有假定模型会持续正确，因此用 query loop 管理状态、用权限约束工具、用 compact 治理上下文
2. **五层 Harness** — 受约束的会话系统 → 代理依赖持续循环 → 工具调用服从调度 → 最危险的工具配最细的规矩 → 错误属于主路径
3. **执行叙事的一致性** — 错误恢复真正保护的，是系统对自己行为的解释能力
4. **验证必须独立** — 不能让系统自己给自己打分
5. **制度化优于个人技巧** — 个人顺手不代表团队能稳定复用

## 相关页面

- [[harness-engineering|Harness Engineering]]
- [[query-loop|Query Loop]]
- [[claude-code|Claude Code]]
- [[andrej-karpathy|Karpathy 的 LLM Wiki]] 模式本身就运行在 Claude Code 上
