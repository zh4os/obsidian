---
title: "Claude Code 不是只有输入框，这 8 个命令我几乎天天在用"
aliases: ["Claude Code 8 个命令", "破晓AI编程 slash commands"]
type: source
tags: [claude-code, slash-command, workflow, context-governance]
created: 2026-04-26
updated: 2026-04-26
sources: ["https://mp.weixin.qq.com/s/WqfpZOeg-UEzUinz8n3T3w"]
---

# Claude Code 不是只有输入框，这 8 个命令我几乎天天在用

来源：[[poxiao-ai|破晓AI编程]] 微信公众号，[原文链接](https://mp.weixin.qq.com/s/WqfpZOeg-UEzUinz8n3T3w)

## 核心立场

文章承接作者前几篇 Claude Code 工作流系列，把方法论落到具体的 [[claude-code|Claude Code]] 内置 slash command 上。讲的不是命令清单，而是**新手就能上手的最小命令工作流**——9 个命令配 [[context-governance|上下文治理]] 与 [[multi-agent-verification|改完先验证]] 的实操心法。

## 9 个高频命令

| 命令 | 用途 | 解决什么 |
|---|---|---|
| `/clear` | 换题先清场 | 旧上下文污染新任务 |
| `/resume` | 旧活直接续 | 任务现场（试过什么、卡在哪）保留 |
| `/rename` | 给 session 命名 | 让 `/resume` 以后搜得到 |
| `/compact` | 把长任务拽回主线 | 现场太乱、方向没错 |
| `/context` | 别靠体感猜上下文 | 把"感觉不对"变成可判断信息 |
| `/statusline` | 状态栏长期可见 | context 用量被动可见，不用主动查 |
| `/btw` | 支线别硬塞主线 | 多线程聊崩，主线被冲乱 |
| `/diff` | 改完不等于改对 | 验证 Claude 真改了什么 |
| `/init` | 新项目搭骨架 | 第一版 [[knowledge-management\|CLAUDE.md]] 起手难 |

## 最小工作流（作者自述）

1. 新任务、不是同一个问题 → `/clear`
2. 旧任务回来续 → `/resume`
3. 任务边界明确 → 顺手 `/rename`
4. 感觉发散 → 先看 `/context`
5. 上下文重了 → `/compact`
6. 支线小问题 → `/btw`
7. 平时把 `/statusline` 配好，context 用量常驻可见
8. Claude 改完 → 先 `/diff`
9. 接新项目 → 尽早 `/init`

## 与 Harness 哲学的呼应

文章观点和 [[harness-engineering|Harness Engineering]] 内核一致：

- `/clear`、`/compact`、`/context`、`/statusline` → [[context-governance|上下文治理]]：上下文是工作内存，需要预算管理而非无限累积
- `/resume`、`/rename` → 会话即工作单元，可恢复性靠认真命名维护
- `/btw` → 单线程纪律，反对把多任务硬塞同一会话
- `/diff` → [[multi-agent-verification|验证先于信任]]，"看起来像做对了"是最大的坑
- `/init` → 用 [[knowledge-management|CLAUDE.md]] 把项目级约束沉淀成可加载指令

## 关键引用

> 很多 session 不是做复杂了，是聊串了。

> `/resume` 好不好用，很大程度取决于你前面有没有认真命名。

> 这个命令最大的价值就是把"感觉不太对劲"变成可判断的信息。

> 很多返工，都是从没看 `/diff` 这一步开始的。

## 相关

- [[claude-code|Claude Code]] — 命令所属工具
- [[claude-code-command-workflow|Claude Code 命令工作流]] — 本文方法论的概念整理
- [[context-governance|上下文治理]] — 命令背后的核心理念
- [[harness-engineering-claude-code|Harness Engineering: Claude Code 设计指南]] — 同主题的工程深度版
