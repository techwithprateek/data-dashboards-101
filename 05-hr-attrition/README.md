# Project 5: IBM HR Analytics Employee Attrition

**Dataset:** https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset

Employee-level data: department, tenure, satisfaction, income, overtime, and whether they left.

## Business Questions

- Which department/manager has the highest attrition rate?
- What factors (overtime, satisfaction, income, tenure) most correlate with attrition?
- Is there a tenure range where attrition risk spikes?

## Suggested KPIs / Fields

- Attrition Rate %
- Attrition by Department
- Avg Tenure of Leavers
- Attrition by Overtime Status
- Satisfaction Score vs Attrition

## What to Build

An attrition risk dashboard by department/manager, or a driver analysis of what predicts employee churn.

## Tool

Tableau Public (free, local build, public share link) or Power BI Desktop.

Follow the [best practices](../best-practices.md) before you start designing.

**Reference build:** [dashboard.html](dashboard.html) — built with Claude + HTML (see below).

## Build with Claude + HTML

No BI tool installed? You can build this entire dashboard with Claude, using plain HTML — no server, no account, just a file you open in your browser.

1. Ask Claude to download the dataset (Kaggle CLI, or the direct link above) and load it with pandas.
2. Ask Claude to compute attrition rate overall, and broken out by department, overtime status, job role, and tenure bucket.
3. Ask Claude to build a single self-contained `dashboard.html`: filter dropdowns for Department, Job Role, and Overtime Status up top, KPI cards below, then 3-4 Chart.js charts that all recompute client-side when a filter changes.
4. Open the HTML file directly in your browser to view it.

Example prompt:
> "Download the IBM HR Analytics Employee Attrition dataset from Kaggle, load it as row-level data, and build a single self-contained HTML dashboard: filter dropdowns for Department, Job Role, and Overtime Status; KPI cards for total employees, attrition rate, and avg tenure of leavers vs stayers; and Chart.js bar charts for attrition rate by department, overtime status, job role, and tenure bucket — all recomputing on filter change, PowerBI style, one accent color, sorted bars, hover tooltips, no dark mode."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own before peeking.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
