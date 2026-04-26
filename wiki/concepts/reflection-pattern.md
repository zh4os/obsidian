---
title: 反思
aliases: ["反思", "Reflection Pattern"]
type: concept
tags: [agent, 设计模式, 自我改进]
created: 2026-04-24
updated: 2026-04-26
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 反思

让 LLM 审视和改进自己的输出。模型生成初始响应后，通过一个或多个后续提示词对其进行批判性评估，识别错误、改进质量。这种自我评估循环可以显著提高输出的准确性和可靠性。

## 核心机制

- **自我评估**：生成输出后，要求 LLM 对自己的输出进行评判——检查事实准确性、逻辑一致性、格式完整性
- **迭代改进**：基于自我评估的反馈修改输出，可多轮迭代直到满足质量标准
- **双角色模式**：一个 LLM 实例作为"生成者"，另一个（或同一个以不同提示词）作为"评审者"

## 应用场景

- **代码生成与审查**：生成代码后让 LLM 检查 bug、安全漏洞、性能问题，再输出改进版
- **文本写作**：起草 → 检查逻辑/语法/风格 → 修改 → 最终版
- **数学与推理**：解题后验证每一步推导，减少计算错误
- **数据提取验证**：提取结构化数据后检查完整性和一致性

## 实践建议

> 当需要高质量输出、初始生成可能包含错误、或者任务有明确的质量标准可以评判时，使用反思模式。它特别适合有客观正确性标准的任务。

## 代码框架

书中示例使用 **LangChain** 和 **Google ADK**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 4 章
- [[prompt-chaining|提示词链]] — 反思是链的一种特殊形式（生成→评估→改进）
- [[multi-agent-collaboration-pattern|多智能体协作]] — 可以用不同 agent 分别充当生成者和评审者
- [[evaluation-monitoring-pattern|评估与监控]] — 反思是内部评估，监控是外部评估
- [[learning-adaptation-pattern|学习与适应]] — 反思是单次改进，学习是跨任务持续改进
- [[goal-monitoring-pattern|目标设定与监控]] — 反思查输出质量，监控查执行进度
- [[prompt-chaining-in-long-context-era|长上下文时代下的提示词链]] — 延伸分析：自评必须独立 prompt
