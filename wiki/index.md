# Wiki Index

## Sources
- [[karpathy-llm-wiki|LLM Wiki — Andrej Karpathy]] — LLM 增量构建持久化知识 wiki 的模式提案
- [[harness-engineering-claude-code|Harness Engineering: Claude Code 设计指南]] — 从 Claude Code 源码提炼的 AI Agent 工程原则（88 页，9 章）
- [[comparing-claude-code-codex|Claude Code 和 Codex 的 Harness 设计哲学]] — 两种 Harness 路线的比较工程笔记（54 页，8 章）
- [[agentic-design-patterns|智能体设计模式（双语版）]] — 21 种 LLM Agent 设计模式百科（570 页，21 章）
- [[claude-code-slash-commands|Claude Code 8 个高频命令]] — 破晓AI编程的 slash command 实操工作流

## Entities
- [[andrej-karpathy|Andrej Karpathy]] — AI 研究者，LLM Wiki 模式提出者
- [[obsidian|Obsidian]] — 本地 Markdown 知识管理工具
- [[claude-code|Claude Code]] — Anthropic 的 AI 编程代理
- [[codex|Codex]] — OpenAI 的 AI 编程代理
- [[agentway|agentway.dev]] — Harness Engineering 系列书籍出版方
- [[antonio-gulli|Antonio Gulli]] — 《智能体设计模式》作者
- [[poxiao-ai|破晓AI编程]] — Claude Code 工作流向微信公众号作者

## Concepts
- [[llm-wiki-pattern|LLM Wiki 模式]] — 用 LLM 维护持久化知识库的模式
- [[ingest-workflow|Ingest 工作流]] — 将原始素材整合进 wiki 的流程
- [[query-workflow|Query 工作流]] — 基于 wiki 知识回答问题的流程
- [[lint-workflow|Lint 工作流]] — wiki 健康检查和维护流程
- [[knowledge-management|知识管理]] — 组织、存储和检索知识的实践
- [[rag|RAG]] — 检索增强生成
- [[harness-engineering|Harness Engineering]] — 围绕不稳定模型设计控制结构的工程方法
- [[agent-harness|Agent Harness]] — 把 LLM 约束成可用工程部件的"外壳"（术语入口页）
- [[prompt-as-control-plane|Prompt 作为控制面]] — Prompt 是分层控制面，不是人格包装
- [[query-loop|Query Loop]] — 代理系统的心跳：可恢复的执行循环
- [[tool-permission-interruption|工具权限与中断]] — 工具是受管执行接口，权限先于能力
- [[context-governance|上下文治理]] — 上下文是工作内存，需要预算管理
- [[error-and-recovery|错误与恢复]] — 错误路径就是主路径
- [[multi-agent-verification|多代理与验证]] — 用分工和验证管理不确定性
- [[team-adoption|团队落地]] — 团队制度比个人技巧重要
- [[harness-ten-principles|Harness Engineering 十条原则]] — 全书十条原则压缩
- [[prompt-chaining|提示词链]] — 将复杂任务分解为顺序子任务的管道模式（第 1 章）
- [[routing-pattern|路由]] — 动态条件路由，按输入分发到不同处理流程（第 2 章）
- [[parallelization-pattern|并行化]] — 同时执行多个独立子任务并聚合结果（第 3 章）
- [[reflection-pattern|反思]] — 自我评估与迭代改进（第 4 章）
- [[tool-use-pattern|工具使用]] — 通过外部工具扩展 LLM 能力边界（第 5 章）
- [[planning-pattern|规划]] — 将高层目标分解为可执行步骤序列（第 6 章）
- [[multi-agent-collaboration-pattern|多智能体协作]] — 多个专业化 agent 协同工作（第 7 章）
- [[memory-management-pattern|记忆管理]] — 会话、状态与长期记忆管理（第 8 章）
- [[learning-adaptation-pattern|学习与适应]] — SICA、AlphaEvolve 等自我改进机制（第 9 章）
- [[mcp-pattern|MCP 协议]] — 标准化模型-工具通信协议（第 10 章）
- [[goal-monitoring-pattern|目标设定与监控]] — 目标追踪与偏差修正（第 11 章）
- [[exception-handling-pattern|异常处理与恢复]] — 错误检测、降级与恢复策略（第 12 章）
- [[human-in-the-loop-pattern|人机协同]] — 人类监督与关键节点干预（第 13 章）
- [[rag-pattern|知识检索（RAG）]] — 检索增强生成的 Agent 化实践（第 14 章）
- [[a2a-pattern|智能体间通信（A2A）]] — Agent 间标准化通信协议（第 15 章）
- [[resource-optimization-pattern|资源感知优化]] — 计算资源与成本的智能管理（第 16 章）
- [[reasoning-pattern|推理技术]] — CoT、ToT、Self-Consistency 等推理增强（第 17 章）
- [[guardrails-pattern|安全护栏]] — 输入/输出过滤与内容安全机制（第 18 章）
- [[evaluation-monitoring-pattern|评估与监控]] — 系统性评估与运行时监控（第 19 章）
- [[prioritization-pattern|优先级排序]] — 任务优先级判断与资源分配（第 20 章）
- [[exploration-discovery-pattern|探索与发现]] — 自主探索未知领域与发现新知识（第 21 章）
- [[claude-code-command-workflow|Claude Code 命令工作流]] — 9 个 slash command 的最小工作流

## Analyses
- [[query-workflow-vs-query-loop|Query 工作流 vs Query Loop]] — 同名但不同层：认知工作流 vs 执行基础设施
