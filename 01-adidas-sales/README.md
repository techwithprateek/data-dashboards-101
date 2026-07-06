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

**Reference build:** [dashboard.html](dashboard.html) — built with Claude + HTML (see below).

## Build with Claude + HTML

No BI tool installed? You can build this entire dashboard with Claude, using plain HTML — no server, no account, just a file you open in your browser.

1. Ask Claude to download the dataset (Kaggle CLI, or the direct link above) and load it with pandas.
2. Ask Claude to compute the KPIs above — total revenue, units sold, margin by region/category/retailer — and aggregate the results.
3. Ask Claude to build a single self-contained `dashboard.html`: KPI cards up top, then 3-4 charts (Chart.js via CDN is enough — no build tools needed).
4. Open the HTML file directly in your browser to view it.

Example prompt:
> "Download the Adidas US Sales dataset from Kaggle, compute total revenue, units sold, operating margin, revenue by region, by product category, and by retailer. Build a single self-contained HTML dashboard with KPI cards and Chart.js bar/line charts — one accent color, sorted bars, hover tooltips."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own before peeking.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
