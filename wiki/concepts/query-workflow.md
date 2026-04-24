---
title: Query 工作流
aliases: ["Query 工作流"]
type: concept
tags: [workflow, llm-wiki]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# Query 工作流

[[llm-wiki-pattern|LLM Wiki 模式]]的核心操作之一。基于 wiki 已有知识回答问题。

## 流程

1. 用户提出问题
2. LLM 读取 `wiki/index.md` 定位相关页面
3. 读取相关页面，综合信息
4. 生成带 `[[wikilink]]` 引用的回答
5. 如果回答有复用价值，存入 `wiki/analyses/`
6. 更新 index.md 和 log.md

## 要点

- 回答的形式可以多样：文本、表格、对比分析
- **好的回答应该被存入 wiki**，让探索也能产生复利

## 相关

- [[ingest-workflow|Ingest 工作流]] — ingest 充实知识库，query 消费知识库
- [[lint-workflow|Lint 工作流]] — lint 检查 query 生成的 analyses 页面健康度
- [[rag|RAG]] — query 工作流本质上是一种 RAG 实践
- [[query-loop|Query Loop]] — Harness Engineering 中的底层执行循环机制
