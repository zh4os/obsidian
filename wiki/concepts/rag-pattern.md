---
title: 知识检索（RAG）
aliases: ["知识检索（RAG）", "Knowledge Retrieval Pattern", "RAG Pattern"]
type: concept
tags: [agent, 设计模式, 知识检索]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/papers/agentic-design-patterns-bilingual.pdf]
---

# 知识检索（RAG）

检索增强生成（Retrieval-Augmented Generation）的设计模式视角。从外部知识源检索相关信息，作为上下文提供给 LLM 生成回答。这让 agent 能够访问超出训练数据的专有知识、最新信息和领域文档。

## RAG 工作流程

1. **文档预处理**：将文档分块（chunking）、生成向量嵌入、存入向量数据库
2. **查询处理**：将用户查询转为向量，从数据库中检索最相关的文档块
3. **上下文注入**：将检索结果作为上下文注入到提示词中
4. **生成回答**：LLM 基于检索到的上下文生成有据可查的回答

## 高级 RAG 技术

- **查询改写**：优化用户查询以提高检索效果
- **混合检索**：结合向量搜索和关键词搜索
- **重排序**：对检索结果重新排序，提高相关性
- **多步检索**：迭代检索，逐步深入

## 应用场景

- **企业知识库问答**：基于内部文档回答员工问题
- **客户支持**：从帮助文档中检索解决方案
- **法律合规**：从法规文档中检索相关条款
- **技术文档**：从 API 文档中检索用法示例

## 与 LLM Wiki 的对比

参见 [[rag|RAG]] 和 [[llm-wiki-pattern|LLM Wiki 模式]] — LLM Wiki 在 ingest 时就完成综合和交叉引用，而 RAG 在每次查询时从零检索。两者互补。

## 代码框架

书中示例使用 **Google ADK** 和 **LangChain**。

## 相关

- [[agentic-design-patterns|智能体设计模式（双语版）]] — 第 14 章
- [[rag|RAG]] — 本 wiki 中的 RAG 概念页
- [[llm-wiki-pattern|LLM Wiki 模式]] — Wiki 模式是 RAG 的替代/互补方案
- [[memory-management-pattern|记忆管理]] — 长期记忆检索与 RAG 相关
