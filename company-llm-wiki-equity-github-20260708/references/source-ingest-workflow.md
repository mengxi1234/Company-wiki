# Source Ingest Workflow

## Source Priority

1. Regulatory filings: SEC EDGAR, exchange filings, 10-K, 10-Q, 8-K, proxy.
2. Company official: IR pages, earnings releases, annual reports, presentations, official news.
3. Officially distributed transcripts: company CDN, IR event pages, clearly sourced transcript PDFs.
4. Industry institutions and primary participants: SIA, SEMI, Deloitte, McKinsey, Epoch AI, TSMC, SK hynix, Micron, Samsung, AMD, Broadcom, Google, AWS, Microsoft, Meta, etc.
5. Broker research: use only accessible content or user-provided files; comply with redistribution limits.
6. News and media summaries: use as leads, not as strong evidence.

## Raw File Placement

Use the closest matching subfolder:

- `10-raw/<Company>/annual-reports/`
- `10-raw/<Company>/earnings-calls/`
- `10-raw/<Company>/broker-reports/`
- `10-raw/<Company>/industry-reports/`
- `10-raw/<Company>/news/`

If a PDF is parsed into text, keep both the original PDF and extracted `.txt`.

Raw attachments are evidence files, not reliable graph nodes. For every material source, also create a lightweight Markdown source note under:

- `10-raw/<Company>/资料节点/`

The source note should link outward to the company hub, source index, relevant Chinese raw category index, impacted wiki/data/thesis pages, and the raw attachment or original URL. Use a normal Markdown link for attachments, for example `[official PDF](../annual-reports/file.pdf)`, not a wikilink to the PDF.

Use Chinese names for Obsidian-facing raw index pages:

- `原始资料目录.md`
- `资料节点索引.md`
- `年报与10-K索引.md`
- `财报与电话会索引.md`
- `券商研报索引.md`
- `行业报告索引.md`
- `新闻与事件索引.md`

## Source Index Fields

Each material source row should include:

- Source ID
- Company or theme
- Source type
- Fiscal period or title
- Publisher/institution
- Publish or filing date
- Source link
- Local file path or Markdown source-note wikilink
- Credibility label
- Use cases
- Ingestion status
- Questions requiring verification

In `50-logs/source-index.md`, prefer the source-note wikilink as the local path, such as `[[10-raw/<Company>/资料节点/S12-...|S12 资料节点]]`. Put direct raw attachment paths inside the source note. This keeps the graph connected while preserving file traceability.

For inaccessible broker reports, write:

- `仅获取到标题/摘要`
- `需要用户手动提供原文`
- `不能据此形成强结论`

## Evidence Extraction

For each source batch, extract:

- Business structure and segment changes
- Revenue and profitability drivers
- Customer types and concentration
- Supply chain and manufacturing dependency
- Competitive changes
- Management claims and guidance
- Risks and uncertainty
- Valuation variables

## Logs

Update `50-logs/ingest-log.md` with:

- Ingest date
- Source date
- Company/theme
- Source ID(s)
- Type
- Credibility
- Impacted pages
- Verification gaps
- Status

Update `50-logs/health-check.md` after a major source batch.
