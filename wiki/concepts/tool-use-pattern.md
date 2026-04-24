---
title: 工具使用
aliases: ["工具使用", "Tool Use Pattern", "Function Calling"]
type: concept
tags: [agent, 设计模式, 函数调用]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 工具使用

通过函数调用（Function Calling）机制，使智能体能够与外部 API、数据库、服务交互，甚至执行代码。LLM 的知识是静态的，仅限于训练数据；工具使用模式打破了这一限制，让 LLM 能够访问实时信息、执行精确计算、与用户特定数据交互或触发现实世界的行动。

## 工作流程

1. **工具定义**：向 LLM 描述可用的外部函数，包括名称、参数和用途
2. **LLM 决策**：基于用户请求，LLM 判断是否需要调用工具
3. **函数调用生成**：LLM 生成结构化输出（JSON 对象），指定工具名和参数
4. **工具执行**：编排层拦截并执行实际的外部函数
5. **结果反馈**：执行结果返回给 LLM，整合到最终响应中

## 应用场景

- **实时数据查询**：天气、股价、新闻等实时信息获取
- **数据库访问**：查询公司内部数据库、私有知识库
- **精确计算**：数学运算、统计分析等 LLM 不擅长的计算
- **代码执行**：运行代码片段、自动化脚本
- **外部操作**：发送邮件、创建日历事件、控制智能设备

## 实践建议

> 当智能体需要突破 LLM 的内部知识并与外部世界交互时，使用工具使用模式。

## 代码框架

书中示例使用 **LangChain**、**CrewAI** 和 **Google ADK**（含 Vertex AI Search 等预构建工具）。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 5 章
- [[mcp-pattern|MCP 协议]] — MCP 是工具使用的标准化通信协议
- [[tool-permission-interruption|工具权限与中断]] — Harness Engineering 视角的工具管控
- [[routing-pattern|路由]] — 路由决定调用哪个工具
