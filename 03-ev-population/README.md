# Project 3: Electric Vehicle Population 2024

**Dataset:** https://data.wa.gov/Transportation/Electric-Vehicle-Population-Data/rpr4-cgyd

EV registrations by make, model, range, and state.

## Business Questions

- Which manufacturer has the largest share of EV registrations?
- How has EV adoption trended year over year by state?
- What's the average electric range by make/model?

## Suggested KPIs / Fields

- Total Registrations
- Market Share by Manufacturer
- YoY Growth %
- Avg Electric Range by Model
- Registrations by State

## What to Build

A manufacturer market share dashboard, or an EV adoption trend tracker by state and year.

## Tool

Tableau Public (free, local build, public share link) or Power BI Desktop.

Follow the [best practices](../best-practices.md) before you start designing.

**Reference build:** [dashboard.html](dashboard.html) — built with the SQL-first workflow below.

## Build This Dashboard with Claude (SQL-First)

Do the [one-time setup](../README.md#setup-one-time) first (installs Claude Code). Then, in your terminal where you ran `claude`, work through these prompts one at a time.

**1. Get the data**
This dataset lives on a government open-data portal, not Kaggle, and has 1.7M+ rows — too big to fetch through Claude. Get the full file yourself:
1. Open the [dataset link](https://data.wa.gov/Transportation/Electric-Vehicle-Population-Data/rpr4-cgyd) above.
2. Click **Export** (top right) → **CSV**.
3. Save it into your project folder. It may take a minute to download — it's a large file, but SQLite handles millions of rows without trouble.

**2. Load it into a local SQLite database**
> "Load the Electric Vehicle Population CSV into a new SQLite database called `ev.db`, in a table called `registrations`. This file has 1.7M+ rows so it may take a minute — that's expected."

**3. Explore the table**
> "Show me the schema of the `registrations` table and the first 5 rows."

**4. Ask one SQL question at a time:**
> "Write and run a SQL query: total registration count, and count by Make, top 12, sorted highest to lowest."

> "Write and run a SQL query: registration count by Model Year, sorted chronologically, for 2018 through 2024."

> "Write and run a SQL query: registration count by County, top 10, sorted highest to lowest."

> "Write and run a SQL query: registration count by Electric Vehicle Type (BEV vs PHEV vs Hydrogen)."

> "Write and run a SQL query: average Electric Range by Make, for makes with at least 200 registrations, top 10, sorted highest to lowest."

> "Write and run a SQL query: registration count by New or Used Vehicle."

Ask **"explain this query"** any time a result surprises you.

**5. Save your results**
> "Save each of those query results as its own CSV file in a `results/` folder."

**6. Build the dashboard** — pick one:
- **Power BI**: Get Data → Text/CSV → import each file from `results/`, then drag fields into visuals. No DAX needed.
- **Claude + HTML**: > "Using the CSV files in `results/`, build a single self-contained `dashboard.html`: filter dropdowns for Model Year and Vehicle Type; KPI cards for total registrations, top manufacturer, top manufacturer share, and YoY growth; and charts for the registration trend by year, registrations by manufacturer, vehicle type mix, registrations by county, and avg electric range by manufacturer — recomputing when a filter changes, PowerBI style, one accent color, sorted bars, hover tooltips, no dark mode."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own first.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
