---
title: 评估与监控
aliases: ["评估与监控", "Evaluation and Monitoring Pattern"]
type: concept
tags: [agent, 设计模式, 可观测性]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 评估与监控

系统性地评估智能体性能和运行时监控。包括离线评估（基准测试、评分）和在线监控（延迟、成功率、用户满意度），确保 agent 在生产环境中持续稳定运行。

## 评估维度

- **准确性**：输出是否正确
- **延迟**：响应时间是否满足要求
- **成本**：API 调用和计算开销
- **用户满意度**：最终用户体验

## 监控手段

- **Agent Trajectories（智能体轨迹）**：记录 agent 的完整执行路径，包括每一步的决策、工具调用和结果
- **从 Agent 到高级承包商**：将 agent 的质量管控提升到类似软件工程承包商的水平
- **Google ADK 集成**：Google ADK 提供内置的评估和监控工具

## 应用场景

- **模型选择**：对比不同模型在特定任务上的表现
- **回归检测**：prompt 修改后检测性能变化
- **生产监控**：实时监控 agent 的成功率、延迟、错误率
- **持续改进**：基于监控数据驱动优化决策

## 实践建议

> 没有评估的优化是盲目的。建立评估基线，持续监控，数据驱动改进。

## 代码框架

书中示例使用 **Google ADK** 的评估工具。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 19 章
- [[reflection-pattern|反思]] — 内部评估 vs 外部评估
- [[learning-adaptation-pattern|学习与适应]] — 评估提供学习的反馈信号
- [[goal-monitoring-pattern|目标设定与监控]] — 目标监控是评估的一部分
