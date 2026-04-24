---
title: 探索与发现
aliases: ["探索与发现", "Exploration and Discovery Pattern"]
type: concept
tags: [agent, 设计模式, 科学研究]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 探索与发现

智能体自主探索未知领域、发现新知识的能力。这是 agent 设计模式中最前沿的方向——让 AI 不仅执行已知任务，还能主动探索、提出假设、设计实验和发现新事物。

## 关键案例

- **Google Co-Scientist**：Google 的 AI 协同科学家，能够自主进行科学研究——提出假设、设计实验、分析结果
- **自主研究 agent**：能够在缺乏明确指令的情况下，自主决定探索方向

## 探索策略

- **好奇心驱动**：探索信息增益最大的方向
- **假设验证**：提出假设 → 设计实验 → 验证结果 → 修正假设
- **随机探索**：引入随机性避免局部最优
- **知识边界探测**：识别已知与未知的边界，重点探索边界区域

## 应用场景

- **科学研究**：药物发现、材料科学、蛋白质结构预测
- **数据探索**：自主发现数据集中的模式和异常
- **创意生成**：探索新的设计空间和创意方向
- **知识发现**：在大规模文献中发现新的关联和洞察

## 实践建议

> 探索与发现是最具挑战性的 agent 能力。适合在有大量未标注数据或未知空间的科研场景中使用。

## 代码框架

书中以 **Google Co-Scientist** 为案例，提供了实践代码示例。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 21 章
- [[planning-pattern|规划]] — 探索需要规划实验路径
- [[reasoning-pattern|推理技术]] — 探索需要深度推理
- [[learning-adaptation-pattern|学习与适应]] — 从探索结果中学习
