# Project 2: DataCo Smart Supply Chain

**Dataset:** https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

End-to-end supply chain data: order fulfillment, shipping mode, delivery risk, and late deliveries.

## Business Questions

- What % of orders are delivered late, and which region/carrier accounts for most late deliveries?
- Which shipping mode has the highest delivery risk?
- How does delivery risk vary by product category or region?

## Suggested KPIs / Fields

- On-Time Delivery %
- Late Delivery Count / Rate
- Delivery Risk by Region
- Delivery Risk by Shipping Mode

## What to Build

An on-time delivery performance dashboard, or a late-shipment root-cause analysis by region/carrier.

## Tool

Tableau Public (free, local build, public share link) or Power BI Desktop.

Follow the [best practices](../best-practices.md) before you start designing.

**Reference build:** [dashboard.html](dashboard.html) — built with the SQL-first workflow below.

## Build This Dashboard with Claude (SQL-First)

Do the [one-time setup](../README.md#setup-one-time) first (installs Claude Code). Then, in your terminal where you ran `claude`, work through these prompts one at a time.

**1. Get the data**
Go to the [dataset link](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis) above, click **Download**, and unzip the file into your project folder. You'll see a file named `DataCoSupplyChainDataset.csv` (~180K rows — SQLite handles this easily).

**Choose your path:**
- **New to SQL** → follow **Path A** below — one query at a time, explained as you go.
- **Already know SQL** → skip to **Path B** — batch the queries, spend your time on the dashboard instead.

### Path A: New to SQL

**2. Load it into a local SQLite database**
> "Load `DataCoSupplyChainDataset.csv` into a new SQLite database called `supply_chain.db`, in a table called `orders`. The file uses Latin-1 encoding, not UTF-8 — handle that when reading it."

**3. Explore the table**
> "Show me the schema of the `orders` table and the first 5 rows. What does the `Late_delivery_risk` column mean — is it a flag?"

**4. Ask one SQL question at a time:**
> "Write and run a SQL query: total order count, and the percentage of orders where Late_delivery_risk = 1 (late) vs 0 (on-time)."

> "Write and run a SQL query: late delivery rate by Order Region, sorted highest to lowest."

> "Write and run a SQL query: late delivery rate by Shipping Mode, sorted highest to lowest."

> "Write and run a SQL query: order count by Category Name, top 10, sorted highest to lowest."

> "Write and run a SQL query: late delivery rate by Market, sorted highest to lowest."

> "Write and run a SQL query: average shipping days (real) by Shipping Mode, sorted highest to lowest."

Ask **"explain this query"** any time a result surprises you.

**5. Save your results**
> "Save each of those query results as its own CSV file in a `results/` folder."

**6. Build the dashboard** — pick one:
- **Power BI**: Get Data → Text/CSV → import each file from `results/`, then drag fields into visuals. No DAX needed.
- **Claude + HTML**: > "Using the CSV files in `results/`, build a single self-contained `dashboard.html`: filter dropdowns for Order Region and Shipping Mode; KPI cards for total orders, on-time %, late %, and avg shipping days; and charts for late rate by region, by shipping mode, order volume by category, and late rate by market — recomputing when a filter changes, PowerBI style, one accent color, sorted bars, hover tooltips, no dark mode."

### Path B: Already Know SQL

**2. Load and analyze in one pass**
> "Load `DataCoSupplyChainDataset.csv` (Latin-1 encoded) into a SQLite database called `supply_chain.db`, table `orders`. Then write, run, and save each of these as its own CSV in a `results/` folder: (1) total orders and on-time/late % overall, (2) late rate by Order Region, (3) late rate by Shipping Mode, (4) order count by Category Name top 10, (5) late rate by Market, (6) avg shipping days by Shipping Mode, (7) late rate grouped by BOTH Order Region and Shipping Mode together — one row per region/mode combination."

**3. Build the dashboard — this is the real exercise**
This project's reference dashboard replaces the usual pair of "late rate by region" and "late rate by mode" bar charts with **one heatmap matrix**: Order Region as rows, Shipping Mode as columns, cells shaded by late rate — that's what query (7) above is for. Read [best-practices.md](../best-practices.md), then ask Claude to build that structure (a color-shaded HTML table, not a chart) from your `results/` CSVs in your own words — don't reuse the Path A prompt. Compare against [dashboard.html](dashboard.html) once you're happy with yours.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
