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

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own first.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
