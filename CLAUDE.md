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

## Tips for the LLM

- When ingesting, a single source may touch 10-15 wiki pages. Be thorough.
- When updating existing pages with new information, note what changed and why.
- The wiki should compound — each ingest should make the whole wiki richer, not just add an isolated page.
- Prefer updating existing pages over creating new ones when the topic overlaps.
- Keep `overview.md` current — it should reflect the wiki's evolving scope and themes.
