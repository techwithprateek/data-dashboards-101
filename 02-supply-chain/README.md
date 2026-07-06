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

**Reference build:** [dashboard.html](dashboard.html) — built with Claude + HTML (see below).

## Build with Claude + HTML

No BI tool installed? You can build this entire dashboard with Claude, using plain HTML — no server, no account, just a file you open in your browser.

1. Ask Claude to download the dataset (Kaggle CLI, or the direct link above) and load it with pandas.
2. Ask Claude to compute the KPIs above — on-time/late delivery rate, and late rate broken out by region, shipping mode, and market.
3. Ask Claude to build a single self-contained `dashboard.html`: KPI cards up top, then 3-4 charts (Chart.js via CDN is enough — no build tools needed).
4. Open the HTML file directly in your browser to view it.

Example prompt:
> "Download the DataCo Smart Supply Chain dataset from Kaggle, compute on-time vs late delivery rate overall, and late delivery rate by order region, shipping mode, and market. Build a single self-contained HTML dashboard with KPI cards and Chart.js bar charts — one accent color, sorted bars, hover tooltips."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own before peeking.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
