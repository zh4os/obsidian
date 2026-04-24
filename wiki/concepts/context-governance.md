---
title: 上下文治理
aliases: ["上下文治理"]
type: concept
tags: [harness-engineering, claude-code, context]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# 上下文治理

> 上下文一多，系统就容易产生一种低级幻觉。

上下文是工作内存，需要预算管理，不是越多越好。

## 四层分离

1. **CLAUDE.md** — 长期指令，分层发现和加载
2. **MEMORY.md** — 索引，不是日记本（入口文件 vs 正文文件）
3. **Session Memory** — 短期连续性，结构化而非靠聊天记录硬扛
4. **临时对话** — 当前 turn 的信息

## Compact 机制

- **自动 compact** — 上下文治理首先是预算治理，有阈值、buffer 和 circuit breaker
- **Compact 后重建** — 恢复工作语义（计划、技能、关键文件、工具状态），而非只留摘要
- **Compact 自身也会失败** — 连"修复动作"都需要修复策略

## 工程启示

> 上下文治理做得好的系统，往往看起来有点吝啬。那种吝啬通常是优点，不是缺点。

## 相关

- [[harness-engineering|Harness Engineering]]
- [[prompt-as-control-plane|Prompt 作为控制面]]
- [[error-and-recovery|错误与恢复]]
