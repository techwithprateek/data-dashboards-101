# Project 4: Financial Performance Dataset

**Dataset:** https://www.kaggle.com/datasets/ilyaryabov/financial-performance-of-companies-from-sp500

> Note: the originally linked Kaggle dataset (`sazidthe1/financial-performance-data-set`) has been taken down. This is a substitute with the same shape — revenue, income, margins, and growth by company — across S&P 500 companies instead of business units.

Company-level data including revenue, net income, profit margins, and quarterly growth metrics.

## Business Questions

- Which companies generate the highest revenue and net income?
- Which companies have the strongest net margin?
- How does quarterly revenue growth compare across companies?

## Suggested KPIs / Fields

- Combined Revenue
- Combined Net Income
- Avg Net Margin %
- Avg Revenue Growth (YoY) %
- Top Companies by Revenue / Margin / Growth
- Net Margin Distribution

## What to Build

An executive financial dashboard with top-company rankings by revenue, margin, and growth, plus a net margin distribution across all companies.

## Tool

Tableau Public (free, local build, public share link) or Power BI Desktop.

Follow the [best practices](../best-practices.md) before you start designing.

**Reference build:** [dashboard.html](dashboard.html) — built with the SQL-first workflow below.

## Build This Dashboard with Claude (SQL-First)

Do the [one-time setup](../README.md#setup-one-time) first (installs Claude Code). Then, in your terminal where you ran `claude`, work through these prompts one at a time.

**1. Get the data**
Go to the [dataset link](https://www.kaggle.com/datasets/ilyaryabov/financial-performance-of-companies-from-sp500) above, click **Download**, and unzip the file into your project folder. You should end up with `snp500_companies_description.csv`.

**2. Load it into a local SQLite database**
> "Load `snp500_companies_description.csv` into a new SQLite database called `financial.db`, in a table called `companies`. Some numeric columns are stored as text with suffixes like `41.05B` or `24.6%` — load them as text for now, we'll clean them with SQL next."

**3. Explore and clean the data**
> "Show me the schema and 5 sample rows of the `companies` table."

> "Add new numeric columns to the table: `revenue_num` and `income_num`, parsed from the 'Revenue (ttm)' and 'Income (ttm)' text columns (convert B/M/K suffixes to actual numbers), and `margin_num` and `growth_num` parsed from the percent columns (strip the % sign)."

**4. Ask one SQL question at a time:**
> "Write and run a SQL query: combined revenue, combined income, average net margin, and average revenue growth across all companies with valid numbers."

> "Write and run a SQL query: top 10 companies by revenue_num, sorted highest to lowest."

> "Write and run a SQL query: top 10 companies by market capitalization, sorted highest to lowest."

> "Write and run a SQL query: top 10 companies by margin_num, sorted highest to lowest."

> "Write and run a SQL query: top 10 companies by growth_num, sorted highest to lowest."

> "Write and run a SQL query: count of companies bucketed into net margin tiers (<0%, 0-10%, 10-20%, 20-30%, 30%+)."

Ask **"explain this query"** any time a result surprises you.

**5. Save your results**
> "Save each of those query results as its own CSV file in a `results/` folder."

**6. Build the dashboard** — pick one:
- **Power BI**: Get Data → Text/CSV → import each file from `results/`, then drag fields into visuals. No DAX needed.
- **Claude + HTML**: > "Using the CSV files in `results/`, build a single self-contained `dashboard.html`: filter dropdowns for Net Margin Tier and Revenue Tier; KPI cards for combined revenue, combined income, avg net margin, and avg revenue growth; and charts (or ranked leaderboards) for top 10 companies by revenue, market cap, net margin, and growth, plus a net margin distribution — recomputing when a filter changes, PowerBI style, one accent color, hover tooltips, no dark mode."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own first.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
