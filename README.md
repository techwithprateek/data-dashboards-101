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

## How to Build

**Option A — BI tool (recommended for learning Tableau/Power BI):**
1. Pick a project, download the dataset.
2. Read the business questions and suggested KPIs in that project's README.
3. Read [best-practices.md](best-practices.md) before designing — chart choice, layout, color, grouping.
4. Build in **Tableau Public** (free, local build, public share link) or **Power BI Desktop**.
5. Publish and share your dashboard link — add it as a PR to the project's README, or drop it wherever you found this repo.

**Option B — Claude + HTML (no BI tool needed):**
Each project README has a "Build with Claude + HTML" section with an example prompt — ask Claude to fetch the dataset, compute the KPIs, and generate a self-contained `dashboard.html` you open straight in your browser.
