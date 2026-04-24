---
title: "Claude Code 和 Codex 的 Harness 设计哲学"
aliases: ["Claude Code 和 Codex 的 Harness 设计哲学"]
type: source
tags: [harness-engineering, claude-code, codex, 比较, 系统设计]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/book2-comparing.pdf]
---

# Claude Code 和 Codex 的 Harness 设计哲学

来源：[[agentway|agentway.dev]]，2026-04-01，rev 37dfc2，54 页（8 章 + 2 附录）
Harness Engineering 系列第二本，比较 [[claude-code|Claude Code]] 与 [[codex|Codex]] 的 Harness 设计哲学。

## 核心立场

> Claude Code 与 Codex 的共同点，不在于它们都很会调用工具，而在于它们都不肯把模型当作一个可以放任自流的部件。

两者都承认模型不可靠，但把"不信任"安放在不同地方。

## 五条比较轴

### 1. 控制面

| Claude Code | Codex |
|---|---|
| 动态 prompt 装配线 | 带编号的公文系统（结构化 fragment） |
| 现场编导 | 制度秘书 |
| 经验型控制力 | 制度型控制力 |

- Claude Code：`prompts.ts` + `systemPrompt.ts` + `claudemd.ts` 层层拼装
- Codex：`fragment.rs` + `user_instructions.rs` 带 marker 的结构化片段

### 2. 连续性（心跳放在哪）

| Claude Code | Codex |
|---|---|
| [[query-loop|Query Loop]] 压进主循环 | Thread + Rollout + State Bridge |
| 现场救火队 | 带档案系统的调度中心 |

### 3. 工具与权限

| Claude Code | Codex |
|---|---|
| 运行时编排 + 危险动作约束 | 工具 schema + 审批参数 + 策略引擎 |
| allow/deny/ask 运行时判定 | exec policy 可解析策略语言 |

### 4. 本地治理（CLAUDE.md vs AGENTS.md）

| Claude Code | Codex |
|---|---|
| 让现场规则进入会话 | 让现场规则进入制度 |
| 偏经验收编 | 偏制度挂载 |

### 5. 多代理与验证

| Claude Code | Codex |
|---|---|
| 运行时职责分区 | 显式工具化协作 |
| verification 独立于 implementation | 持久状态让验证不只是礼仪 |

## 殊途同归

> 同归：都知道模型不可信，真正可信的只能是约束结构。
> 各表一枝：一个从运行时事故经验里塑出来，另一个从显式结构设计里塑出来。

## 给后来者的建议

- 如果问题是长会话失控、恢复脆弱、验证被跳过 → 先学 Claude Code 的运行时纪律
- 如果问题是规则来源太散、权限边界不清、工具契约不稳定 → 先学 Codex 的显式控制层
- 最怕混着用，既没有运行时纪律，也没有清楚的控制层

## 相关页面

- [[harness-engineering-claude-code|第一本书：Claude Code 设计指南]]
- [[harness-engineering|Harness Engineering]]
- [[claude-code|Claude Code]]
- [[codex|Codex]]
