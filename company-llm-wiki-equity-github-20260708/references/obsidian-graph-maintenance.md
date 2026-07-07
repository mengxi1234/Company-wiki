# Obsidian Graph Maintenance

## Goal

Keep the vault searchable by both text and Obsidian graph. A source is not fully ingested until it has a traceable source-index row, a raw artifact or URL, and a Markdown node that links it into the company research graph.

## Chinese Index Rule

When the vault is Chinese, use Chinese names for Obsidian-facing index and hub pages:

- `原始资料目录`
- `资料节点索引`
- `年报与10-K索引`
- `财报与电话会索引`
- `券商研报索引`
- `行业报告索引`
- `新闻与事件索引`
- `公司：<Company>`
- `风险：<Company>`
- `假设：<Company>-YYYY-MM-DD`
- `估值：<Company>-YYYY-MM-DD`

Keep attachment folders stable if they already exist. For example, `10-raw/<Company>/annual-reports/` can remain English while `10-raw/<Company>/年报与10-K索引.md` is the human-facing graph page.

## Source Notes

Create one Markdown source note per material source:

- Path: `10-raw/<Company>/资料节点/Sxx-<short-source-name>.md`
- Link to the company hub: `[[公司：<Company>]]`
- Link to the source index: `[[50-logs/source-index|资料索引总表]]`
- Link to the relevant category index: `[[10-raw/<Company>/年报与10-K索引|年报与10-K索引]]`
- Link to impacted analysis pages such as `[[20-wiki/<Company>/moat|护城河]]`
- Link to attachments with normal Markdown links, not wikilinks.

Keep source notes short: metadata, source-backed facts, inferences, verification gaps, and links. They exist to connect evidence to analysis, not to duplicate the entire report.

## Link Repair Rules

1. Resolve exact path links first, then basename links.
2. Prefer creating a missing hub page when many pages intentionally point to the same concept.
3. Prefer updating links when the old target was an English index page that has been renamed to Chinese.
4. Treat template placeholders such as `{{公司名称}}`, `{{YYYY-MM-DD}}`, and AGENTS examples as intentional unresolved links unless the user asks to materialize templates.
5. Do not create placeholder pages for every incidental word. Create hubs only for company, source, industry, concept, risk, hypothesis, and valuation nodes that improve navigation.

## Health Scan

After graph repair or a material source batch, scan all Markdown files for wikilinks and report:

- Markdown file count
- Total wikilinks
- Resolved wikilinks
- Unresolved wikilinks
- Target-company unresolved links
- Orphan Markdown pages
- Intentional unresolved placeholders

Use any local script or a short one-off scanner. The logic should:

- Collect all `.md` files.
- Build resolvable targets by path-without-`.md` and basename.
- Extract wikilinks, strip aliases after `|` and headings after `#`.
- Count links as resolved when the target matches a known path or basename.
- Count orphan pages as Markdown files with no incoming links, excluding top-level templates or intentionally standalone instructions when appropriate.

Record the result in `50-logs/health-check.md` and record the repair action in `50-logs/ingest-log.md`.

## Final Report

When the user asks to optimize links or graph visibility, include:

1. Which index or hub pages were created or renamed.
2. How many source notes exist for the company.
3. Remaining unresolved links and whether they are intentional.
4. Whether any pages remain orphaned.
5. What the user should now see in Obsidian Graph View.
