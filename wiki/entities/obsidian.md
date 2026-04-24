---
title: Obsidian
aliases: ["Obsidian"]
type: entity
tags: [tool, knowledge-management, markdown]
created: 2026-04-24
updated: 2026-04-24
sources: [raw/articles/karpathy-llm-wiki.md]
---

# Obsidian

基于本地 Markdown 文件的[[knowledge-management|知识管理]]工具。支持 `[[wikilinks]]`、graph view、插件生态。

## 在本 wiki 中的角色

本 wiki 的"IDE"。[[claude-code|Claude Code]] 在后台编辑 Markdown 文件，用户在 Obsidian 中实时浏览结果 — 跟踪链接、查看图谱视图、阅读更新的页面。这是 [[llm-wiki-pattern|LLM Wiki 模式]] 的人机协作界面：LLM 负责写入，用户在 Obsidian 中策展和探索。

## 推荐配置

- **附件目录**：Settings → Files and links → Attachment folder path → `raw/assets/`
- **Web Clipper**：浏览器扩展，将网页文章转为 Markdown 存入 `raw/articles/`
- **Dataview 插件**：可对 frontmatter 做查询，生成动态表格
- **Graph View**：可视化页面之间的链接关系，发现孤立页和知识枢纽

## 相关

- [[andrej-karpathy|Andrej Karpathy]] — LLM Wiki 模式的提出者，推荐 Obsidian 作为前端
- [[ingest-workflow|Ingest 工作流]] — 在 Obsidian 中浏览 ingest 结果
- [[lint-workflow|Lint 工作流]] — Graph View 可辅助发现孤立页等问题
