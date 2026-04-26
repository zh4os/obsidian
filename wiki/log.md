# Wiki Log

<!-- Append-only. Newest entries at top. -->
<!-- Format: ## [YYYY-MM-DD] operation | subject -->

## [2026-04-26] query | 长上下文时代下的提示词链是否还有意义
- Created: wiki/analyses/prompt-chaining-in-long-context-era.md
- Updated: wiki/index.md, wiki/concepts/prompt-chaining.md（补 analysis 反链）

## [2026-04-26] lint | 修复表格 wikilink 别名语法 + 补 14 对对等概念互链
- Fixed: 5 个 source/concept 页的表格内 wikilink 用 `\|` 转义（解决列分隔符冲突）
- Updated: wiki/concepts/error-and-recovery.md, multi-agent-verification.md, context-governance.md, reflection-pattern.md, goal-monitoring-pattern.md, tool-permission-interruption.md, team-adoption.md, learning-adaptation-pattern.md, planning-pattern.md, reasoning-pattern.md, prompt-chaining.md — 补对等概念反向 wikilink，updated 同步到 2026-04-26

## [2026-04-26] ingest | Claude Code 8 个高频 slash command（破晓AI编程）
- Source: https://mp.weixin.qq.com/s/WqfpZOeg-UEzUinz8n3T3w
- Created: wiki/sources/claude-code-slash-commands.md
- Created: wiki/concepts/claude-code-command-workflow.md
- Created: wiki/entities/poxiao-ai.md
- Updated: wiki/entities/claude-code.md, wiki/index.md, wiki/overview.md

## [2026-04-24] query | Agent Harness 术语页
- Created: wiki/concepts/agent-harness.md
- Updated: wiki/index.md

## [2026-04-24] query | Query 工作流 vs Query Loop
- Created: wiki/analyses/query-workflow-vs-query-loop.md
- Updated: wiki/index.md

## [2026-04-24] re-ingest | 智能体设计模式 — 补全 21 个设计模式概念页
- Source: raw/papers/agentic-design-patterns-bilingual.pdf
- Created: wiki/concepts/prompt-chaining.md, wiki/concepts/routing-pattern.md, wiki/concepts/parallelization-pattern.md, wiki/concepts/reflection-pattern.md, wiki/concepts/tool-use-pattern.md, wiki/concepts/planning-pattern.md, wiki/concepts/multi-agent-collaboration-pattern.md, wiki/concepts/memory-management-pattern.md, wiki/concepts/learning-adaptation-pattern.md, wiki/concepts/mcp-pattern.md, wiki/concepts/goal-monitoring-pattern.md, wiki/concepts/exception-handling-pattern.md, wiki/concepts/human-in-the-loop-pattern.md, wiki/concepts/rag-pattern.md, wiki/concepts/a2a-pattern.md, wiki/concepts/resource-optimization-pattern.md, wiki/concepts/reasoning-pattern.md, wiki/concepts/guardrails-pattern.md, wiki/concepts/evaluation-monitoring-pattern.md, wiki/concepts/prioritization-pattern.md, wiki/concepts/exploration-discovery-pattern.md
- Updated: wiki/index.md, wiki/overview.md

## [2026-04-24] ingest | 智能体设计模式（双语版）
- Source: raw/papers/agentic-design-patterns-bilingual.pdf
- Created: wiki/sources/agentic-design-patterns.md
- Created: wiki/entities/antonio-gulli.md
- Updated: wiki/index.md, wiki/overview.md

## [2026-04-24] ingest | Claude Code 和 Codex 的 Harness 设计哲学
- Source: raw/papers/book2-comparing.pdf
- Created: wiki/sources/comparing-claude-code-codex.md
- Created: wiki/entities/codex.md
- Updated: wiki/entities/claude-code.md, wiki/index.md, wiki/overview.md

## [2026-04-24] ingest | Harness Engineering: Claude Code 设计指南
- Source: raw/papers/book1-claude-code.pdf
- Created: wiki/sources/harness-engineering-claude-code.md
- Created: wiki/entities/claude-code.md, wiki/entities/agentway.md
- Created: wiki/concepts/harness-engineering.md, wiki/concepts/query-loop.md, wiki/concepts/prompt-as-control-plane.md, wiki/concepts/tool-permission-interruption.md, wiki/concepts/context-governance.md, wiki/concepts/error-and-recovery.md, wiki/concepts/multi-agent-verification.md, wiki/concepts/team-adoption.md, wiki/concepts/harness-ten-principles.md
- Updated: wiki/index.md, wiki/overview.md

## [2026-04-24] ingest | LLM Wiki — Andrej Karpathy
- Source: raw/articles/karpathy-llm-wiki.md
- Created: wiki/sources/karpathy-llm-wiki.md
- Created: wiki/entities/andrej-karpathy.md, wiki/entities/obsidian.md
- Created: wiki/concepts/llm-wiki-pattern.md, wiki/concepts/ingest-workflow.md, wiki/concepts/query-workflow.md, wiki/concepts/lint-workflow.md, wiki/concepts/knowledge-management.md, wiki/concepts/rag.md
- Updated: wiki/index.md, wiki/overview.md

## [2026-04-24] init | Wiki initialized
- Created directory structure: raw/{articles,papers,notes,assets}, wiki/{sources,entities,concepts,analyses}
- Created CLAUDE.md (schema), index.md, log.md, overview.md
