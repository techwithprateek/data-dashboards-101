# data-dashboards-101

5 beginner-friendly data visualization / dashboard projects. Each project has a dataset, business questions to answer, and suggested KPIs — no finished dashboard given, so you build it yourself.

## Projects

| # | Project | Focus | Reference Dashboard |
|---|---------|-------|----------------------|
| 1 | [Adidas US Sales](01-adidas-sales/README.md) | regional sales performance, retailer profitability | [dashboard.html](01-adidas-sales/dashboard.html) |
| 2 | [DataCo Smart Supply Chain](02-supply-chain/README.md) | on-time delivery, late-shipment root cause | [dashboard.html](02-supply-chain/dashboard.html) |
| 3 | [Electric Vehicle Population](03-ev-population/README.md) | manufacturer market share, EV adoption trends | [dashboard.html](03-ev-population/dashboard.html) |
| 4 | [Financial Performance (S&P 500)](04-financial-performance/README.md) | company revenue, margin, growth rankings | [dashboard.html](04-financial-performance/dashboard.html) |
| 5 | [IBM HR Attrition](05-hr-attrition/README.md) | attrition risk, driver analysis | [dashboard.html](05-hr-attrition/dashboard.html) |

Each reference dashboard is a self-contained HTML file (open directly in a browser, no server needed) — built with Claude, real data, PowerBI-style filter dropdowns that actually cross-filter the KPIs and charts, a light flat theme (no dark mode), and a distinct accent color per project. They're the "answer key" — try building your own first.

## Setup (one-time)

You need a tool that lets Claude create files and run commands on your computer — the regular claude.ai chat in a browser can't do this. Use **Claude Code**:

1. **Install Node.js** — go to [nodejs.org](https://nodejs.org), download the "LTS" version, run the installer, click through with defaults. (This is just a requirement to install Claude Code — you won't write any Node.js code.)
2. **Open a terminal.**
   - Mac: press `Cmd + Space`, type "Terminal", hit Enter.
   - Windows: press the Start key, type "Command Prompt" (or install "Windows Terminal" from the Microsoft Store for a nicer experience), hit Enter.
3. **Install Claude Code** — in the terminal, type this and press Enter:
   ```
   npm install -g @anthropic-ai/claude-code
   ```
4. **Create a project folder and enter it:**
   ```
   mkdir dashboard-practice
   cd dashboard-practice
   ```
5. **Start Claude Code:**
   ```
   claude
   ```
   Log in when it asks (same account as claude.ai). You're now chatting with Claude *inside your terminal* — it can read/write files and run code in this folder. Everything from here on is just prompts you type at this chat.

You do **not** need to separately install SQLite — Claude will create and query your database using Python's built-in `sqlite3` module, which needs no setup.

## How to Build

**Option A — BI tool (recommended for learning Tableau/Power BI):**
1. Pick a project, download the dataset.
2. Read the business questions and suggested KPIs in that project's README.
3. Read [best-practices.md](best-practices.md) before designing — chart choice, layout, color, grouping.
4. Build in **Tableau Public** (free, local build, public share link) or **Power BI Desktop**.
5. Publish and share your dashboard link — add it as a PR to the project's README, or drop it wherever you found this repo.

**Option B — SQL + Claude (recommended — teaches the actual Data Analyst skill stack):**

This path teaches you SQL — the single most-requested skill in Data Analyst job postings — while Claude handles all the setup and query-writing friction. The shape of the workflow is always the same:

```
raw file  →  local SQLite database  →  SQL queries (one per business question)  →  saved CSV results  →  Power BI or Claude-built dashboard
```

Each project's README has the exact copy-paste prompts for that dataset, following this pattern:
1. Load the raw file into a local SQLite database.
2. Ask Claude to show you the table schema, so you know what you're working with.
3. Ask Claude to write and run one SQL query per business question — ask "explain this query" any time you don't understand it. This is where the actual SQL learning happens.
4. Save each query's results as a CSV file.
5. Either import those CSVs into Power BI and build visuals with drag-and-drop (no DAX needed — the SQL already did the aggregation), or ask Claude to turn them into a self-contained HTML dashboard directly.

**Already know SQL?** Each project README forks into two paths: **Path A (New to SQL)** is the query-by-query walkthrough above; **Path B (Already Know SQL)** batches all the queries into one prompt and points you straight at the reference dashboard's specific layout (a heatmap, a leaderboard, a hero trend chart) as the thing worth practicing — since SQL isn't the skill gap for that path, dashboard design is.
