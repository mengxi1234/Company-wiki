Company LLM Wiki Equity
一个用于维护本地 Obsidian 公司研究知识库的 Codex Skill。
它的目标不是简单总结资料，而是把上市公司的年报、财报、电话会、券商研报、行业报告和重要新闻，沉淀成一套可持续更新、可追踪来源、可验证假设的价值投资研究系统。
适合做什么
创建和维护上市公司研究 Wiki
摄入 10-K、10-Q、年报、季报、电话会纪要、券商研报、行业报告和重要新闻
建立公司首页、业务模式、产品客户、行业竞争、护城河、管理层、资本配置、风险清单等页面
维护财务数据表、KPI 表、分部收入表和关键变量跟踪表
更新投资假设、估值变量、牛市/基准/熊市情景和决策日志
维护 Obsidian 双链结构和图谱关系
为原始资料创建 Markdown 资料节点，让 PDF、HTML、研报和新闻能接入知识图谱
知识库结构
默认适配以下 Obsidian Vault 结构：
10-raw/      原始资料和来源文件
20-wiki/     公司研究页面
30-data/     财务和 KPI 数据表
40-thesis/   投资判断、估值、情景分析、决策日志
50-logs/     资料索引、摄入日志、健康检查
核心原则
这个 Skill 会要求 Codex 始终区分三类内容：
事实：由公告、财报、电话会、监管文件、公司官方页面或明确引用的行业数据支持
推断：基于事实做出的商业解释或投资判断
待验证：未经确认的说法、不确定的计算、无法访问的资料、媒体摘要、付费研报内容或市场预期
它不会把券商观点、管理层叙事、市场传闻或新闻解读直接当作事实。
Obsidian 图谱优化
这个 Skill 特别强化了 Obsidian 双链和图谱维护：
使用中文索引页，例如 原始资料目录、资料节点索引、年报与10-K索引、券商研报索引
为每一份重要资料创建 Markdown 资料节点
source-index.md 链接到资料节点，而不是直接链接 PDF、HTML、TXT 等附件
修复未解析双链、孤立页面和公司研究页面之间的断点
将图谱健康检查结果记录到 50-logs/health-check.md
资料可信度标签
常用标签包括：
监管：SEC、交易所、监管机构文件
官方：公司 IR、官方公告、官方演示材料
官方分发 / 三方转录：公司分发但由第三方转录的电话会纪要
行业机构：SIA、SEMI、Deloitte、McKinsey、Epoch AI、产业链公司报告等
券商：可访问的券商研报
券商摘要 / 新闻媒体：媒体对券商研报的摘要，不能单独支持强结论
新闻媒体：新闻或市场报道，只能作为线索，需要交叉验证
待验证：只有标题、无法访问、传闻或资料不完整的来源
文件说明
SKILL.md
agents/openai.yaml
references/page-structure.md
references/source-ingest-workflow.md
references/thesis-update-rules.md
references/obsidian-graph-maintenance.md
SKILL.md：Skill 的主说明和执行规则
agents/openai.yaml：Codex 中展示用的名称、简介和默认提示
references/page-structure.md：公司研究页面和数据表结构
references/source-ingest-workflow.md：资料搜索、下载、登记和证据提取流程
references/thesis-update-rules.md：投资假设、风险、估值和决策日志规则
references/obsidian-graph-maintenance.md：中文索引页、资料节点、双链修复和图谱健康检查规则
使用方式
把整个文件夹放到 Codex 的 skills 目录中，例如：
~/.codex/skills/company-llm-wiki-equity/
然后在 Codex 中使用：
$company-llm-wiki-equity
示例任务：
请使用 $company-llm-wiki-equity，帮我为 NVIDIA 摄入最近 3 年年报和最近 4 个季度财报，并更新 Company-LLM-Wiki。
当前状态
这个 Skill 已用于构建和维护一个面向价值投资研究的 Company-LLM-Wiki，并针对 NVIDIA 样板公司优化了资料摄入、双链图谱、中文索引页和投资假设更新流程。
