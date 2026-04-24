---
title: Ingest 工作流
aliases: ["Ingest 工作流"]
type: concept
tags: [workflow, llm-wiki]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# Ingest 工作流

[[llm-wiki-pattern|LLM Wiki 模式]]的核心操作之一。将新的原始素材整合进 wiki。

## 流程

1. 用户将素材放入 `raw/` 对应目录
2. 告诉 LLM：`ingest raw/articles/xxx.md`
3. LLM 阅读素材，与用户讨论关键要点
4. 在 `wiki/sources/` 创建摘要页
5. 创建或更新相关实体页和概念页
6. 添加 `[[wikilinks]]` 互相链接
7. 更新 `wiki/index.md`
8. 追加 `wiki/log.md`

## 要点

- 单次 ingest 可能触及 10-15 个 wiki 页面
- 优先更新已有页面，而非创建重复页面
- 可以逐个 ingest（精细控制）或批量 ingest（效率优先）

## 相关

- [[query-workflow|Query 工作流]] — ingest 充实知识库，query 消费知识库
- [[lint-workflow|Lint 工作流]] — ingest 后可运行 lint 检查新增内容的健康度
- [[knowledge-management|知识管理]] — ingest 是知识管理的输入环节
