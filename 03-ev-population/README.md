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

**Reference build:** [dashboard.html](dashboard.html) — built with Claude + HTML (see below).

## Build with Claude + HTML

No BI tool installed? You can build this entire dashboard with Claude, using plain HTML — no server, no account, just a file you open in your browser.

1. Ask Claude to pull the dataset — this one is large (1.7M+ rows), so ask Claude to query the Socrata API (`data.wa.gov/resource/rpr4-cgyd.json`) with aggregated SoQL queries (`$group`, `$select count(*)`) instead of downloading the full file.
2. With 1.7M+ rows, raw-row filtering in the browser isn't an option — ask Claude to precompute a lookup table ("cube") of KPIs + chart data for every Year × Vehicle Type combination using aggregated SoQL queries, instead of shipping raw rows.
3. Ask Claude to build a single self-contained `dashboard.html`: filter dropdowns for Year and Vehicle Type up top, KPI cards below, then 3-4 Chart.js charts that look up the matching precomputed slice and re-render when a filter changes.
4. Open the HTML file directly in your browser to view it.

Example prompt:
> "Query the WA Electric Vehicle Population dataset (Socrata API at data.wa.gov, resource rpr4-cgyd) with aggregated SoQL queries grouped by year, vehicle type, and manufacturer (and separately by county). Precompute a lookup table of KPIs and chart breakdowns for every Year × Vehicle Type filter combination, including 'All'. Build a single self-contained HTML dashboard with filter dropdowns for Year and Vehicle Type, KPI cards, and Chart.js bar/line charts that look up the matching slice on filter change — PowerBI style, one accent color, sorted bars, hover tooltips, no dark mode."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own before peeking.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
