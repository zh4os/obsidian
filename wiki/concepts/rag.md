---
title: RAG (Retrieval-Augmented Generation)
aliases: ["RAG (Retrieval-Augmented Generation)"]
type: concept
tags: [llm, rag, knowledge-management]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# RAG (Retrieval-Augmented Generation)

检索增强生成。在查询时从文档集合中检索相关片段，交给 LLM 生成回答。NotebookLM、ChatGPT file uploads 等产品采用此模式。

## 局限性

- 每次查询从零检索，知识不积累
- 无交叉引用
- 无矛盾检测
- 需要综合多文档的复杂问题表现不佳

## 与 LLM Wiki 的对比

参见 [[LLM Wiki 模式#与 RAG 的区别]]
