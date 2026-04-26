---
title: Claude Code 命令工作流
aliases: ["Claude Code 命令工作流", "slash command 最小工作流"]
type: concept
tags: [claude-code, slash-command, workflow, context-governance]
created: 2026-04-26
updated: 2026-04-26
sources: [wiki/sources/claude-code-slash-commands.md]
---

# Claude Code 命令工作流

把 [[claude-code|Claude Code]] 的内置 slash command 串成一套日常工作流，目标是**主动管理上下文、明确任务边界、强制验证产出**——而不是靠"和 Claude 多聊几句"硬怼。

## 命令分类

按职责切分，9 个命令落到 4 类：

### 1. 任务边界（开局）

| 命令 | 何时用 |
|---|---|
| `/clear` | 不是同一个问题就清场，避免旧上下文污染 |
| `/resume` | 昨天的任务现场（已试过、卡点、下一步）整体续回 |
| `/rename` | 任务边界一清楚就命名，让 `/resume` 以后搜得到 |

要点：会话即工作单元，**命名是未来检索的代价**。"继续优化""改一下"等于自我埋雷。

### 2. 上下文管理（中盘）

| 命令 | 何时用 |
|---|---|
| `/context` | 主动查当前上下文有多重，把体感变可判断信息 |
| `/compact` | 现场乱了但方向对，把主线拽回 |
| `/statusline` | 把 context 用量做成状态栏常驻信息 |

要点：呼应 [[context-governance|上下文治理]]——别等聊崩了才后知后觉。`/compact` 救场不救方向，方向错就 `/clear` 重来。

### 3. 多线纪律

| 命令 | 何时用 |
|---|---|
| `/btw` | 主任务推进时冒出的支线问题，单独处理 |

要点：聊崩的会话往往不是任务难，是一边修登录一边聊埋点一边想 CSS 命名，最后变成多线程事故现场。

### 4. 验证与起手

| 命令 | 何时用 |
|---|---|
| `/diff` | Claude 改完先看真改了什么，再决定下一步 |
| `/init` | 新项目尽早跑一次，生成项目级 CLAUDE.md 骨架 |

要点：`/diff` 是 [[multi-agent-verification|验证先于信任]] 的具体动作——查 4 件事：

1. 改的是不是该改的地方
2. 有没有顺手动别的文件
3. 改法是不是符合预期
4. 有没有夹带"我顺便优化了一下"的私货

`/init` 不是自动驾驶，但能解决"第一版 [[knowledge-management|CLAUDE.md]] 怎么起手"的问题，后续边用边补。

## 最小工作流

```
新任务   → /clear
续旧任务 → /resume
边界明确 → /rename
感觉发散 → /context
上下文重 → /compact
支线问题 → /btw
长期可见 → /statusline（配一次）
改完代码 → /diff
新项目   → /init（一次性）
```

## 与其它概念的对应

| 命令 | 对应 wiki 概念 |
|---|---|
| `/clear`、`/compact`、`/context`、`/statusline` | [[context-governance\|上下文治理]] |
| `/resume`、`/rename` | [[memory-management-pattern\|记忆管理]] 的会话维度 |
| `/btw` | 反 multi-tasking 纪律（与 [[parallelization-pattern\|并行化]] 区别：一个是主动开支线，一个是失控混线） |
| `/diff` | [[multi-agent-verification\|多代理与验证]]、["看起来像做对了"反模式](../sources/harness-engineering-claude-code.md) |
| `/init` | [[knowledge-management\|知识管理]]、CLAUDE.md 分层指令 |

## 相关

- [[claude-code|Claude Code]] — 命令所属工具
- [[claude-code-slash-commands|来源文章]]
- [[context-governance|上下文治理]] — 命令背后的工程理念
- [[multi-agent-verification|多代理与验证]] — `/diff` 的方法论根
- [[harness-ten-principles|Harness Engineering 十条原则]] — 文章观点的深度版本
