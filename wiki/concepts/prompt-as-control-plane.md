---
title: Prompt 作为控制面
aliases: ["Prompt 作为控制面"]
type: concept
tags: [harness-engineering, prompt, claude-code]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# Prompt 作为控制面

> 把 prompt 当成人设，是一种常见误会。

在 [[claude-code|Claude Code]] 中，prompt 不是静态文案，而是分层拼装的控制面组件。它的真正价值不在文字本身，而在优先级。

## 分层结构

Claude Code 的 prompt 从一开始就是分层的：
- 身份描述
- 行为规则
- 工具约束
- 输出纪律

优先级来源：默认 → 项目 → 自定义 → 追加 → agent 专属 prompt

## Prompt 连接的系统

- **CLAUDE.md 体系** — 长期指令不能和临场对话混在一起
- **MEMORY.md** — 索引，不是日记本
- **动态系统提醒** — 运行时注入的上下文

## 判断标准

> 删掉某段 prompt 以后，系统行为会不会出现结构性变化。如果会，说明它真是控制面；如果不会，可能只是装饰。

## 相关

- [[harness-engineering|Harness Engineering]]
- [[context-governance|上下文治理]]
- [[claude-code|Claude Code]]
