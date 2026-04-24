---
title: Lint 工作流
aliases: ["Lint 工作流"]
type: concept
tags: [workflow, llm-wiki]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# Lint 工作流

[[llm-wiki-pattern|LLM Wiki 模式]]的核心操作之一。对 wiki 进行健康检查和维护。

## 检查项

1. **矛盾** — 不同页面之间的冲突声明
2. **孤立页** — 没有入站 `[[wikilinks]]` 的页面
3. **缺失页** — `[[wikilinks]]` 指向不存在的页面
4. **过时内容** — 有更新的素材但页面未更新
5. **缺失交叉引用** — 相关页面之间没有链接
6. **知识缺口** — 被频繁提及但没有独立页面的概念

## 使用

直接告诉 LLM `lint`，即可触发全面检查。

## 相关

- [[ingest-workflow|Ingest 工作流]] — lint 检查 ingest 产生的新页面质量
- [[query-workflow|Query 工作流]] — lint 检查 query 生成的 analyses 页面
- [[knowledge-management|知识管理]] — lint 是知识管理的质量保障环节
