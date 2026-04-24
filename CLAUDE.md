# LLM Wiki Schema

This Obsidian Vault is a personal knowledge base maintained by an LLM following the LLM Wiki pattern. The LLM builds and maintains a persistent, interlinked wiki from raw sources. The human curates sources and asks questions; the LLM does the bookkeeping.

## Directory Structure

```
raw/            # Raw sources (IMMUTABLE — never modify)
  articles/     # Web-clipped articles
  papers/       # PDFs, research papers
  notes/        # Personal notes, journals
  assets/       # Images, attachments
wiki/           # LLM-generated and maintained (human reads, LLM writes)
  index.md      # Content index organized by category
  log.md        # Chronological operation log
  overview.md   # Wiki overview, updated as content grows
  sources/      # Summary page per ingested source
  entities/     # Entity pages (people, tools, companies, books…)
  concepts/     # Concept pages (methodologies, theories, patterns…)
  analyses/     # Query-generated syntheses, comparisons
```

## Conventions

- **Language**: All wiki content pages in Chinese (中文). Structure files (index.md, log.md) use English for headers/format but Chinese for descriptions. Raw sources keep their original language.
- **Wikilinks**: Use `[[wikilinks]]` for all cross-references between wiki pages. This powers Obsidian's graph view.
- **Frontmatter**: Every wiki page must have YAML frontmatter:
  ```yaml
  ---
  title: Page Title
  type: source | entity | concept | analysis
  tags: []
  created: YYYY-MM-DD
  updated: YYYY-MM-DD
  sources: []
  ---
  ```
- **File naming**: Use kebab-case for filenames (e.g., `machine-learning.md`, `andrej-karpathy.md`).
- **raw/ is read-only**: NEVER create, modify, or delete files in `raw/`. It is the source of truth.

## Workflows

### Ingest

Triggered when the user says "ingest" followed by a file path (e.g., `ingest raw/articles/some-article.md`).

1. Read the source file in `raw/`.
2. Discuss key takeaways with the user — ask what to emphasize if unclear.
3. Create a summary page in `wiki/sources/` with frontmatter.
4. For each notable entity mentioned, create or update its page in `wiki/entities/`.
5. For each notable concept mentioned, create or update its page in `wiki/concepts/`.
6. Add `[[wikilinks]]` between all related pages.
7. Update `wiki/index.md` — add entries under the appropriate categories.
8. Append an entry to `wiki/log.md` (newest first) in this format:
   ```markdown
   ## [YYYY-MM-DD] ingest | Source Title
   - Created: wiki/sources/source-slug.md
   - Updated: wiki/entities/xxx.md, wiki/concepts/yyy.md
   ```

### Query

When the user asks a question about the wiki's knowledge:

1. Read `wiki/index.md` to find relevant pages.
2. Read those pages to gather information.
3. Synthesize an answer with `[[wikilink]]` citations.
4. If the answer is substantial and reusable, offer to save it as a page in `wiki/analyses/`.
5. If saved, update `wiki/index.md` and append to `wiki/log.md`.

### Lint

Triggered when the user says "lint". Perform a health check:

1. **Contradictions**: Flag claims that conflict across pages.
2. **Orphan pages**: Find pages with no inbound `[[wikilinks]]`.
3. **Missing pages**: Find `[[wikilinks]]` that point to non-existent pages.
4. **Stale content**: Flag pages not updated since newer sources on the same topic were ingested.
5. **Missing cross-references**: Suggest links between related pages that aren't yet connected.
6. **Gaps**: Suggest concepts or entities mentioned frequently but lacking their own page.

Output a health report and offer to fix issues.

## Quality Rules (from past review lessons)

### Wikilinks 必须使用文件名，不用标题
- 正确：`[[llm-wiki-pattern|LLM Wiki 模式]]`
- 错误：`[[LLM Wiki 模式]]`
- Obsidian 解析 wikilinks 时匹配的是文件名（kebab-case），不是 frontmatter title。用 `|` 分隔显示名。

### 每个新页面必须有"相关"区块
- 所有 concept 和 entity 页面末尾必须有 `## 相关` 区块，包含 2-4 条 wikilinks。
- 双向链接：如果 A 链接了 B，B 也应该链接 A。
- 同源页面互链：来自同一 source 的 concept 页面之间应互相引用。

### Source 页中引用的每个概念/实体必须有对应文件
- 在 source 摘要页中写 `[[xxx-pattern|某模式]]` 之前，确认 `wiki/concepts/xxx-pattern.md` 已经存在或即将创建。
- 批量创建时，先创建所有文件，再更新 source 页面的 wikilinks。

### Ingest 完成前必须更新三个结构文件
- `wiki/index.md` — 添加所有新建页面的条目
- `wiki/overview.md` — 更新计数和主题脉络
- `wiki/log.md` — 追加操作日志

## Tips for the LLM

- When ingesting, a single source may touch 10-15 wiki pages. Be thorough.
- When updating existing pages with new information, note what changed and why.
- The wiki should compound — each ingest should make the whole wiki richer, not just add an isolated page.
- Prefer updating existing pages over creating new ones when the topic overlaps.
- Keep `overview.md` current — it should reflect the wiki's evolving scope and themes.
- After ingest, run a self-check: grep all `[[wikilinks]]` in changed files and verify targets exist.
