# Page Structure

## Obsidian-Facing Raw Source Pages

Raw attachments can stay in stable English folders, but the pages the user sees in Obsidian should be readable and graph-visible. Use or create:

- `10-raw/<Company>/原始资料目录.md`
- `10-raw/<Company>/资料节点索引.md`
- `10-raw/<Company>/年报与10-K索引.md`
- `10-raw/<Company>/财报与电话会索引.md`
- `10-raw/<Company>/券商研报索引.md`
- `10-raw/<Company>/行业报告索引.md`
- `10-raw/<Company>/新闻与事件索引.md`
- `10-raw/<Company>/资料节点/Sxx-<short-source-name>.md`

Each source note should include:

- Source ID, title, publisher, date, type, credibility, ingestion status.
- A normal Markdown link to the raw attachment or source URL.
- Obsidian links to `[[公司：<Company>]]`, `[[50-logs/source-index|资料索引总表]]`, the relevant Chinese raw index page, and impacted research pages.
- Short extracted facts, inferences, and `待验证` questions. Do not turn source notes into long duplicated reports.

Create or repair hub pages when they are referenced:

- `公司：<Company>.md`
- `风险：<Company>.md`
- `假设：<Company>-YYYY-MM-DD.md`
- `估值：<Company>-YYYY-MM-DD.md`
- Industry and concept hubs such as `行业：AI基础设施.md` or `概念：CUDA生态.md` when they materially improve navigation.

## Company Wiki Pages

Use or create:

- `20-wiki/<Company>/company-home.md`
- `20-wiki/<Company>/business-model.md`
- `20-wiki/<Company>/product-and-customers.md`
- `20-wiki/<Company>/industry-and-competition.md`
- `20-wiki/<Company>/moat.md`
- `20-wiki/<Company>/management-and-culture.md`
- `20-wiki/<Company>/capital-allocation.md`
- `20-wiki/<Company>/financial-analysis.md`
- `20-wiki/<Company>/risks.md`
- `20-wiki/<Company>/timeline.md`
- `20-wiki/<Company>/open-questions.md`
- `20-wiki/<Company>/valuation.md` when external views or market-implied assumptions are discussed

## Data Pages

Use or create:

- `30-data/<Company>/financial-summary.md`
- `30-data/<Company>/kpi-table.md`
- `30-data/<Company>/segment-table.md`
- `30-data/<Company>/key-driver-tracker.md`

Data tables should include source IDs in the same cell as every factual number. Derived metrics should explain formula and source row. Missing values must be `待补充`.

## Thesis Pages

Use or create:

- `40-thesis/<Company>/thesis-snapshot.md`
- `40-thesis/<Company>/bull-base-bear.md`
- `40-thesis/<Company>/valuation-assumptions.md`
- `40-thesis/<Company>/external-viewpoints.md`
- `40-thesis/<Company>/decision-log.md`

## Annual Reviews

Use:

- `20-wiki/<Company>/annual-reviews/<year>-annual-review.md`

Always clarify fiscal-year vs calendar-year periods.

## External Viewpoints Table

Use this structure:

| 来源 | 日期 | 观点方向 | 核心逻辑 | 关键假设 | 支持证据 | 可能问题 | 对我们判断的影响 |
|---|---:|---|---|---|---|---|---|

Do not stack target prices. Extract disagreements and identify whether they are backed by company facts, industry evidence, or merely expectations.

## Key Driver Tracker

Use this structure:

| 关键变量 | 当前判断 | 支持证据 | 反向证据 | 观察频率 | 下一次更新来源 |
|---|---|---|---|---|---|

For AI infrastructure companies, common variables include data center revenue, AI server demand, gross margin, HBM/CoWoS supply, self-developed chip substitution, export controls, software ecosystem, networking attach rate, inventory/commitments, and valuation multiple.
