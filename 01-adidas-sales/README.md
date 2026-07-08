# Project 1: Adidas US Sales

**Dataset:** https://www.kaggle.com/datasets/heemalichaudhari/adidas-sales-dataset

Retailer, region, product category, units sold, revenue, and operating profit data.

## Business Questions

- Which region generates the highest revenue and units sold?
- Which product category has the best operating profit margin?
- How does retailer profitability compare across regions?

## Suggested KPIs / Fields

- Total Revenue
- Total Units Sold
- Operating Profit Margin %
- Revenue by Region
- Revenue by Product Category
- Retailer Profitability Comparison

## What to Build

A regional sales performance dashboard with product category drill-down, or a retailer profitability comparison.

## Tool

Tableau Public (free, local build, public share link) or Power BI Desktop.

Follow the [best practices](../best-practices.md) before you start designing.

**Reference build:** [dashboard.html](dashboard.html) — built with the SQL-first workflow below.

## Build This Dashboard with Claude (SQL-First)

Do the [one-time setup](../README.md#setup-one-time) first (installs Claude Code). Then, in your terminal where you ran `claude`, work through these prompts one at a time.

**1. Get the data**
Go to the [dataset link](https://www.kaggle.com/datasets/heemalichaudhari/adidas-sales-dataset) above, click **Download**, and unzip the file into your project folder. You should end up with `Adidas US Sales Datasets.xlsx`.

**Choose your path:**
- **New to SQL** → follow **Path A** below — one query at a time, explained as you go.
- **Already know SQL** → skip to **Path B** — batch the queries, spend your time on the dashboard instead.

### Path A: New to SQL

**2. Load it into a local SQLite database**
> "Load `Adidas US Sales Datasets.xlsx` into a new SQLite database called `adidas.db`, in a table called `sales`. The real column headers start a few rows down in the file (there's a title and some blank rows above them) — inspect the file first and skip past those before loading."

**3. Explore the table**
> "Show me the schema of the `sales` table and the first 5 rows."

**4. Ask one SQL question at a time** — paste each of these, one per message:
> "Write and run a SQL query for total revenue, total units sold, and operating margin (sum of profit ÷ sum of revenue) across the whole table."

> "Write and run a SQL query: total revenue by region, sorted highest to lowest."

> "Write and run a SQL query: total revenue by product category, sorted highest to lowest."

> "Write and run a SQL query: total revenue by month, sorted chronologically. Use the invoice date column."

> "Write and run a SQL query: operating margin (sum of profit ÷ sum of revenue) by retailer, sorted highest to lowest."

> "Write and run a SQL query: total revenue by sales method (in-store, outlet, online)."

If any query result surprises you, ask Claude **"explain this query"** — that's the actual SQL lesson.

**5. Save your results**
> "Save each of those query results as its own CSV file in a `results/` folder."

**6. Build the dashboard** — pick one:
- **Power BI**: Open Power BI Desktop → Get Data → Text/CSV → import each file from `results/`. Drag fields into visuals — the SQL already did the aggregation, so no DAX is required. Follow the [best practices](../best-practices.md) for layout and color.
- **Claude + HTML**: > "Using the CSV files in `results/`, build a single self-contained `dashboard.html`: filter dropdowns for Region, Product Category, and Retailer; KPI cards for total revenue, units sold, operating margin, and total profit; and charts for revenue by region, by category, monthly trend, and margin by retailer. Every chart and KPI should recompute when a filter changes — PowerBI style, one accent color, sorted bars, hover tooltips, no dark mode."

### Path B: Already Know SQL

**2. Load and analyze in one pass**
> "Load `Adidas US Sales Datasets.xlsx` into a SQLite database called `adidas.db`, table `sales` (headers start a few rows down — skip the blank ones above them). Then write, run, and save each of these as its own CSV in a `results/` folder: (1) total revenue, units sold, and operating margin overall, (2) revenue by region, (3) revenue by product category, (4) revenue by month, (5) operating margin by retailer, (6) revenue by sales method."

**3. Build the dashboard — this is the real exercise**
This project's reference dashboard leads with a full-width hero trend chart right under the KPIs, and swaps the usual retailer bar chart for a **ranked leaderboard** — a numbered list with an inline proportional bar per row, sorted by margin, not a Chart.js bar chart. Read [best-practices.md](../best-practices.md), then ask Claude to build that structure from your `results/` CSVs in your own words — don't reuse the Path A prompt. Compare against [dashboard.html](dashboard.html) once you're happy with yours.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
