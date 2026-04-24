---
title: "LLM Wiki — Andrej Karpathy"
aliases: ["LLM Wiki — Andrej Karpathy"]
type: source
tags: [llm, knowledge-management, obsidian, rag, wiki]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# LLM Wiki — Andrej Karpathy

Source: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f

## 核心观点

传统 RAG 每次查询都从零检索、拼凑答案，知识不会积累。LLM Wiki 模式的核心区别在于：**LLM 增量构建并维护一个持久化的 wiki**，知识被编译一次、持续更新，而不是每次重新推导。

关键比喻：**Obsidian 是 IDE，LLM 是程序员，wiki 是代码库。**

## 三层架构

| 层 | 内容 | 所有权 |
|---|---|---|
| **Raw Sources** | 原始文档（文章、论文、笔记） | 不可变，LLM 只读 |
| **Wiki** | Markdown 页面（摘要、实体、概念、分析） | LLM 拥有、创建、维护 |
| **Schema** | CLAUDE.md / AGENTS.md | 人与 LLM 共同演化 |

## 三个核心操作

- **[[ingest-workflow|Ingest 工作流]]**：投入新素材 → LLM 阅读 → 创建摘要 → 更新关联页面 → 更新索引和日志。单个素材可能触及 10-15 个 wiki 页面。
- **[[query-workflow|Query 工作流]]**：提问 → LLM 从 index 定位相关页 → 综合回答 → 有价值的回答存入 wiki。
- **[[lint-workflow|Lint 工作流]]**：健康检查 → 查找矛盾、孤立页、缺失链接、过时内容、知识缺口。

## 为什么有效

人类放弃 wiki 是因为**维护成本增长快于价值**。LLM 不会厌倦，不会忘记更新交叉引用，一次能触及 15 个文件。维护成本趋近于零，wiki 因此能持续存活。

这个理念呼应了 Vannevar Bush 1945 年的 Memex 构想 — 一个带有关联路径的个人知识库。Bush 无法解决的维护问题，LLM 解决了。

## 相关概念

- [[rag|RAG]]
- [[knowledge-management|知识管理]]
- [[obsidian|Obsidian]]
- [[andrej-karpathy|Andrej Karpathy]]
