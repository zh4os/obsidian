---
title: Agent Harness
aliases: ["Agent Harness", "harness", "挽具"]
type: concept
tags: [harness-engineering, agent, 系统设计, 术语]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf, raw/papers/book2-comparing.pdf]
---

# Agent Harness

术语入口页。Agent Harness 指把 LLM 约束成可用工程部件的那套"外壳"——一组持续生效的控制结构。"Harness" 本义是**马具/挽具**，拴住马、让它朝规定方向拉车；Agent harness 就是把"聪明但不稳定的 LLM"拴进工程系统的装置。

## 一句话定义

> **Agent Harness 之于 Agent，如同操作系统之于应用程序**——提供进程隔离、权限管理、资源调度、生命周期管理。

LLM 是 "app"，harness 是 "OS"。这个比喻出自 [[harness-engineering|Harness Engineering]]。

## 为什么需要 Harness

核心前提：**模型本身并不稳定**。

- 一个只会输出文本的模型出错，主要带来**理解成本**。
- 一个能运行命令、写文件、修改仓库的模型出错后留下的是**执行结果**——文件被删、进程中断、Git 历史难追。

能力增强伴随后果增强。没有约束的能力只会扩大事故半径，所以需要 harness。

## 组成部件

一个成熟的 agent harness 至少包含以下控制结构，对应 [[harness-ten-principles|十条原则]]：

| 部件 | 负责 |
|------|------|
| [[prompt-as-control-plane\|Prompt 作为控制面]] | 分层拼装 system / user / context，不是人格包装 |
| [[query-loop\|Query Loop]] | 跨轮的可恢复执行心跳 |
| [[tool-permission-interruption\|工具权限与中断]] | 受管执行接口，权限先于能力 |
| [[context-governance\|上下文治理]] | 工作内存预算管理 |
| [[error-and-recovery\|错误与恢复]] | 把错误路径当主路径 |
| [[multi-agent-verification\|多代理与验证]] | 用分工 + 独立验证分区不确定性 |
| [[team-adoption\|团队落地]] | 制度比个人技巧重要 |

## 两种实现流派

[[comparing-claude-code-codex|Claude Code 和 Codex 的 Harness 设计哲学]]对比了两种典型 harness：

| | [[claude-code\|Claude Code]] | [[codex\|Codex]] |
|---|---|---|
| 气质 | 运行时纪律派 | 显式结构派 |
| 控制面 | 动态 prompt 装配线 | 带 marker 的结构化 fragment |
| 心跳 | [[query-loop\|Query Loop]] 压进主循环 | Thread + Rollout + State Bridge |
| 权限 | 运行时 allow/deny/ask | exec policy 可解析策略语言 |
| 比喻 | 现场编导 | 制度秘书 |

两者都承认模型不可信，只是把"不信任"安放在不同层。

## 底线六条

> 先设计权限，再设计能力；
> 先设计回滚，再设计自治；
> 先设计验证，再设计交付；
> 先设计上下文预算，再设计长期对话；
> 先设计生命周期，再设计多代理；
> 先设计制度，再指望团队熟练。

## 常见误解

- ❌ Harness = 对模型能力的情绪化防御
- ✅ Harness = 模型进入工程环境的**前提**
- ❌ Harness = 一堆 prompt 技巧
- ✅ Harness = 覆盖 prompt / loop / tool / context / error / team 的完整控制结构
- ❌ 更强的模型就不需要 harness
- ✅ 能力越强，harness 越必要——因为事故半径更大

## 相关

- [[harness-engineering|Harness Engineering]] — 提出 harness 概念的方法论
- [[harness-ten-principles|Harness Engineering 十条原则]] — harness 的设计准则
- [[harness-engineering-claude-code|第一本书：Claude Code 设计指南]] — harness 的实践样本
- [[comparing-claude-code-codex|第二本书：Claude Code vs Codex]] — 两种 harness 流派对比
- [[claude-code|Claude Code]]、[[codex|Codex]] — 两种 harness 的实例
