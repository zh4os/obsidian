---
title: LLM Wiki 模式
aliases: ["LLM Wiki 模式"]
type: concept
tags: [llm, knowledge-management, pattern]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# LLM Wiki 模式

一种个人知识管理模式：LLM 从原始素材中增量构建并维护一个结构化、互相链接的 Markdown wiki，替代传统的每次查询时从零检索的 RAG 方式。

## 核心原则

1. **知识编译而非检索** — 素材被 ingest 时就完成了综合、交叉引用、矛盾标记，而非每次 query 时重新推导
2. **持久化复利** — wiki 是一个持续增值的资产，每新增一份素材都让整体更丰富
3. **人机分工** — 人类负责策展、提问、思考；LLM 负责摘要、归档、交叉引用、维护

## 与 RAG 的区别

| | RAG | LLM Wiki |
|---|---|---|
| 知识何时综合 | 查询时 | Ingest 时 |
| 交叉引用 | 无 | 持久维护 |
| 矛盾检测 | 无 | 内建 |
| 知识积累 | 不积累 | 持续复利 |

## 灵感来源

呼应 Vannevar Bush 1945 年的 Memex 构想 — 带关联路径的个人知识库。

## 相关

- [[karpathy-llm-wiki|原文摘要]]
- [[knowledge-management|知识管理]]
- [[rag|RAG]]
