---
title: Harness Engineering
aliases: ["Harness Engineering"]
type: concept
tags: [harness-engineering, agent, 系统设计, 核心概念]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# Harness Engineering

一组持续生效的控制结构，用来约束不稳定模型在工程环境中的行为边界。由 [[harness-engineering-claude-code|agentway.dev]] 提出。

## 核心前提

> 模型本身并不稳定。这个判断未必讨喜，但工程系统不能依赖乐观叙事维持。

一个只会输出文本的模型，出错时主要带来理解成本。一个能运行命令、写文件、修改仓库的模型，出错后留下的是**执行结果**——文件被删、进程中断、Git 历史难以追踪。能力增强伴随后果增强，因此需要 Harness。

## 与"模型能力"的关系

Harness 不是对模型能力的情绪化防御，而是模型进入工程环境的前提。没有约束的能力只会扩大事故半径。

比喻：Harness 之于 Agent，如同操作系统之于应用程序——提供进程隔离、权限管理、资源调度。

## [[harness-ten-principles|十条原则]]

1. 把模型当不稳定部件，不要当同事
2. [[prompt-as-control-plane|Prompt 是控制面的一部分]]
3. [[query-loop|Query Loop]] 才是代理系统的心跳
4. 工具是受管执行接口
5. 上下文是工作内存
6. 错误路径就是主路径
7. 恢复的目标是继续工作
8. 多代理的意义是把不确定性分区
9. 验证必须独立
10. 团队制度比个人技巧重要

## 最后六条底线

> 先设计权限，再设计能力；先设计回滚，再设计自治；先设计验证，再设计交付；先设计上下文预算，再设计长期对话；先设计生命周期，再设计多代理；先设计制度，再指望团队熟练。

## 相关

- [[agent-harness|Agent Harness]] — 术语入口页：harness 的定义、组成部件、两种流派
- [[claude-code|Claude Code]] — Harness Engineering 的实践样本
- [[query-loop|Query Loop]]、[[tool-permission-interruption|工具权限与中断]]、[[context-governance|上下文治理]]、[[error-and-recovery|错误与恢复]]、[[multi-agent-verification|多代理与验证]]
