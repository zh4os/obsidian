---
title: Harness Engineering 十条原则
aliases: ["Harness Engineering 十条原则"]
type: concept
tags: [harness-engineering, 原则, 核心]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book1-claude-code.pdf]
---

# Harness Engineering 十条原则

全书压缩。来自 [[harness-engineering-claude-code|原书]] 第 9 章。

1. **把模型当不稳定部件，不要当同事**
2. **[[prompt-as-control-plane|Prompt 是控制面的一部分]]**
3. **[[query-loop|Query Loop]] 才是代理系统的心跳**
4. **工具是受管执行接口**
5. **上下文是工作内存**
6. **错误路径就是主路径**
7. **恢复的目标是继续工作**
8. **多代理的意义，是把不确定性分区**
9. **验证必须独立，不能让系统自己给自己打分**
10. **团队制度比个人技巧重要**

## 全书最后一句话

> Harness Engineering 关心的是：在模型并不可靠的前提下，系统仍然能表现出工程系统应有的行为。

> 难的从来不在把原则说出来，而在愿不愿意承认：Harness 比激情重要，制度比聪明重要，验证比自信重要。

## 相关

- [[harness-engineering|Harness Engineering]] — 详细展开
- [[claude-code|Claude Code]] — 实践样本
