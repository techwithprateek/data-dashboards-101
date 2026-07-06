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

**Reference build:** [dashboard.html](dashboard.html) — built with Claude + HTML (see below).

## Build with Claude + HTML

No BI tool installed? You can build this entire dashboard with Claude, using plain HTML — no server, no account, just a file you open in your browser.

1. Ask Claude to download the dataset (Kaggle CLI, or the direct link above) and load it with pandas.
2. Ask Claude to parse the money/percent fields (they come as strings like `"41.05B"` or `"24.6%"`) and compute the KPIs above.
3. Ask Claude to build a single self-contained `dashboard.html`: KPI cards up top, then 3-4 charts (Chart.js via CDN is enough — no build tools needed).
4. Open the HTML file directly in your browser to view it.

Example prompt:
> "Download the Financial Performance of Companies from S&P500 dataset from Kaggle, parse the revenue/income/margin fields, and compute combined revenue, combined net income, avg net margin, avg revenue growth, plus top 10 companies by revenue/margin/growth and a net margin distribution. Build a single self-contained HTML dashboard with KPI cards and Chart.js bar charts — one accent color, sorted bars, hover tooltips."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own before peeking.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
