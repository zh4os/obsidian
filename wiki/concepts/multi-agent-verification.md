---
title: 多代理与验证
aliases: ["多代理与验证"]
type: concept
tags: [harness-engineering, claude-code, multi-agent]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# 多代理与验证

> 多代理真正解决的是不确定性的分区。

## 核心原则

### 1. Fork 要 cache-safe
子代理创建时考虑 prompt cache 共享和参数一致性，减少重复计算。

### 2. 状态隔离
子代理默认隔离 mutable state，首先要减少污染。

### 3. 角色分离
区分四种角色：
- **Research** — 信息收集
- **Implementation** — 执行实现
- **Synthesis** — 综合理解（稀缺能力，coordinator 承担）
- **Verification** — 独立验证

### 4. 验证必须独立

> "实现完成"很快就会冒充"问题解决"。

验证不能让实现者自己做，必须独立成阶段。验证不仅针对代码，也针对记忆和建议。

### 5. 生命周期可观测
agent 生命周期可观测、可中止、可清理。父 abort 能传播到子代理，防止孤儿任务残留。

## 反模式

> 如果一个系统号称 multi-agent，但所有 agent 都在做差不多的事，而且没人真正负责 synthesis 和 verification，那它通常只是在把混乱扩成并行。

## 相关

- [[harness-engineering|Harness Engineering]]
- [[error-and-recovery|错误与恢复]]
- [[team-adoption|团队落地]]
