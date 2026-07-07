---
name: company-llm-wiki-equity
description: Maintain a local Obsidian Company-LLM-Wiki vault for public-equity value-investing research. Use for creating/updating company research pages, ingesting filings/reports/transcripts/news, maintaining raw/wiki/data/thesis/logs, tracking valuation/risk/thesis assumptions, and repairing Obsidian wikilinks/graph visibility with Chinese index pages and Markdown source-note nodes.
---

# Company LLM Wiki Equity

## Purpose

Maintain a source-backed Obsidian vault for public-company value investing. Convert raw filings, reports, transcripts, and news into durable company research pages, data tables, thesis snapshots, valuation variables, risk registers, update logs, and a browsable Obsidian graph.

## First Reads

Before editing a vault, read:

1. `AGENTS.md`
2. `Home.md`
3. `50-logs/source-index.md`
4. `50-logs/ingest-log.md`
5. The target company home page, if it exists

If the vault uses numbered folders, map them as:

- `10-raw/`: original files and source artifacts
- `20-wiki/`: company research pages
- `30-data/`: financial and KPI tables
- `40-thesis/`: investment thesis, valuation, scenarios, decision logs
- `50-logs/`: source index, ingest log, health check

## Operating Standard

Always separate:

- **Facts**: supported by filings, releases, transcripts, regulatory documents, official pages, or clearly cited industry data.
- **Inferences**: causal interpretation of facts.
- **To verify**: unconfirmed claims, uncertain calculations, unavailable sources, media summaries, paid research, market expectations.

Never treat broker opinions, management narratives, market rumors, or news interpretation as facts. Preserve old judgments unless the user explicitly asks to rewrite history; record changed judgments in a decision log.

## Workflow

1. **Scope the task**: identify target company, ticker, requested source types, time range, pages to update, and whether the user wants download, summary, valuation, or health check.
2. **Gather sources**: prefer official IR, SEC/regulatory filings, company releases, official transcripts, then industry organizations and reputable research. Use broker reports only within redistribution limits.
3. **Store raw artifacts**: put PDFs/HTML/text extracts under the appropriate `10-raw/<Company>/` subfolder.
4. **Create graph nodes for sources**: create or update Chinese Markdown raw index pages and one lightweight Markdown source note for every material source, because Obsidian Graph View does not reliably surface raw attachments.
5. **Register sources**: update `50-logs/source-index.md` before or alongside page updates. Record source type, title, institution, date, link/path, credibility, use, ingestion status, and verification gaps. Link to the Markdown source note, not directly to raw attachments.
6. **Extract evidence**: pull only source-backed facts and clearly label management claims or external estimates.
7. **Update wiki pages**: write durable analysis into `20-wiki/<Company>/`.
8. **Update data tables**: update `30-data/<Company>/` with source marks for every value. Mark missing or unavailable values as `待补充`.
9. **Update thesis pages**: update `40-thesis/<Company>/` with falsifiable assumptions, bull/base/bear scenarios, valuation variables, external viewpoints, and decision-log rows.
10. **Check link graph health**: scan wikilinks, repair target-company unresolved links, add hub links for important company, industry, risk, hypothesis, valuation, and source clusters, and record the result in `50-logs/health-check.md`.
11. **Update logs**: update `50-logs/ingest-log.md` for every material source batch, important graph repair, index rename, or thesis update.
12. **Report back**: summarize ingested sources, updated files, key facts, inferences, weakened/strengthened assumptions, graph-health result, missing materials, and next research steps.

## Reference Files

Read the relevant reference before substantial edits:

- `references/source-ingest-workflow.md`: source search, download, registration, and evidence hierarchy.
- `references/page-structure.md`: expected Obsidian pages and table structures.
- `references/obsidian-graph-maintenance.md`: Chinese index pages, source-note nodes, wikilink repair, and graph-health scan.
- `references/thesis-update-rules.md`: investment assumption, risk, valuation, and decision-log rules.

## Source Credibility Labels

Use labels consistently:

- `监管`: SEC, exchange, regulator filings.
- `官方`: company IR, official releases, official presentations.
- `官方分发 / 三方转录`: transcript distributed from company CDN but transcribed by a provider.
- `行业机构`: SIA, Deloitte, SEMI, McKinsey, Epoch AI, company supply-chain reports, etc.
- `券商`: accessible broker report.
- `券商摘要 / 新闻媒体`: media article summarizing a broker report; cannot support strong conclusions alone.
- `新闻媒体`: news or market reporting; use as a lead requiring cross-check.
- `待验证`: title-only, inaccessible, rumor, or incomplete source.

## Obsidian Linking

Use double links for durable navigation:

- Company home: `[[20-wiki/<Company>/company-home|<Company> 公司首页]]`
- Company hub: `[[公司：<Company>]]`
- Source index anchors: `[[50-logs/source-index#...|Sxx]]`
- Source note node: `[[10-raw/<Company>/资料节点/Sxx-...|Sxx 资料节点]]`
- Raw source directory: `[[10-raw/<Company>/原始资料目录|原始资料目录]]`
- Raw source node index: `[[10-raw/<Company>/资料节点索引|资料节点索引]]`
- Thesis: `[[40-thesis/<Company>/thesis-snapshot|投资假设快照]]`
- Risks: `[[20-wiki/<Company>/risks|风险]]`
- Key drivers: `[[30-data/<Company>/key-driver-tracker|关键变量跟踪表]]`

Prefer Chinese names for Obsidian-facing company, source, index, risk, thesis, valuation, and concept pages when the user's vault is Chinese. Keep stable English raw attachment folders such as `annual-reports/` and `earnings-calls/` if they already exist.

Do not wikilink raw `.pdf`, `.html`, `.txt`, or `.xlsx` attachments from `source-index.md`. Use a wikilink to the Markdown source note, and put the attachment path inside that source note as a normal Markdown link.

## Completion Checklist

Before final response:

- Confirm new files exist.
- Confirm every material source is in `source-index.md`.
- Confirm every material source has a Markdown source-note node and the source index links to it.
- Confirm Obsidian-facing raw index pages use readable Chinese names when the vault is Chinese.
- Confirm every material page update is in `ingest-log.md`.
- Confirm facts/data have source IDs.
- Confirm uncertain values are `待补充` or `待验证`.
- Confirm broker/news summaries are not used as strong facts.
- Confirm the link graph has no target-company unresolved wikilinks or orphan company pages, except intentional template placeholders.
- Confirm the final answer states what could not be accessed.
