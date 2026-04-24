---
title: 安全护栏
aliases: ["安全护栏", "Guardrails Pattern", "Safety Patterns"]
type: concept
tags: [agent, 设计模式, 安全, 合规]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 安全护栏

输入/输出过滤和内容安全机制。确保智能体的输入不包含恶意内容（提示注入、有害请求），输出不包含不当内容（偏见、有害信息、隐私泄露）。是构建可靠智能体的必要防线。

## 护栏类型

- **输入护栏**：过滤恶意输入、检测提示注入、验证输入格式
- **输出护栏**：检查生成内容的安全性、准确性、合规性
- **行为护栏**：限制 agent 可执行的操作范围和权限
- **过程护栏**：监控执行过程中的异常行为

## 工程化可靠智能体

- 输入验证和清洗
- 输出过滤和审查
- 操作权限白名单
- 异常行为检测
- 审计日志

## 应用场景

- **内容安全**：防止生成有害、偏见、不当内容
- **数据保护**：防止 PII 泄露、保护用户隐私
- **权限管控**：限制 agent 可访问的资源和可执行的操作
- **合规审计**：记录 agent 的所有决策和操作，满足审计要求

## 实践建议

> 在任何面向用户的智能体系统中，安全护栏都是必须的。分层防御——输入过滤 + 输出检查 + 行为监控。

## 代码框架

书中示例使用 **CrewAI** 和 **Vertex AI**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 18 章
- [[tool-permission-interruption|工具权限与中断]] — Harness Engineering 中的权限模型
- [[exception-handling-pattern|异常处理与恢复]] — 护栏预防错误，异常处理应对错误
- [[human-in-the-loop-pattern|人机协同]] — 人机协同是最终的安全网
