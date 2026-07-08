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

**Reference build:** [dashboard.html](dashboard.html) — built with the SQL-first workflow below.

## Build This Dashboard with Claude (SQL-First)

Do the [one-time setup](../README.md#setup-one-time) first (installs Claude Code). Then, in your terminal where you ran `claude`, work through these prompts one at a time.

**1. Get the data**
Go to the [dataset link](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) above, click **Download**, and unzip the file into your project folder. You should end up with `WA_Fn-UseC_-HR-Employee-Attrition.csv`.

**2. Load it into a local SQLite database**
> "Load `WA_Fn-UseC_-HR-Employee-Attrition.csv` into a new SQLite database called `hr.db`, in a table called `employees`."

**3. Explore the table**
> "Show me the schema of the `employees` table and the first 5 rows. What values does the Attrition column take?"

**4. Ask one SQL question at a time:**
> "Write and run a SQL query: total employee count, and the overall attrition rate (percentage where Attrition = 'Yes')."

> "Write and run a SQL query: average YearsAtCompany for employees who left vs employees who stayed."

> "Write and run a SQL query: attrition rate by Department, sorted highest to lowest."

> "Write and run a SQL query: headcount by Department, sorted highest to lowest."

> "Write and run a SQL query: attrition rate by OverTime status (Yes/No)."

> "Write and run a SQL query: attrition rate by JobRole, sorted highest to lowest."

> "Write and run a SQL query: attrition rate broken out by both Department and JobSatisfaction (1-4) together — one row per department/satisfaction combination."

Ask **"explain this query"** any time a result surprises you — the last one uses `GROUP BY` on two columns at once, worth understanding.

**5. Save your results**
> "Save each of those query results as its own CSV file in a `results/` folder."

**6. Build the dashboard** — pick one:
- **Power BI**: Get Data → Text/CSV → import each file from `results/`, then drag fields into visuals. No DAX needed.
- **Claude + HTML**: > "Using the CSV files in `results/`, build a single self-contained `dashboard.html`: filter dropdowns for Department, Job Role, and Overtime; KPI cards for total employees, attrition rate, and avg tenure of leavers vs stayers; a heatmap of attrition rate by Department × Job Satisfaction; and charts for attrition by job role and by overtime status — recomputing when a filter changes, PowerBI style, one accent color, hover tooltips, no dark mode."

The [dashboard.html](dashboard.html) in this folder was built exactly this way — open it as a reference, but try building your own first.

## Share Your Version

Built it? Add your published dashboard link as a PR to this README, or drop it in the comments on the post.
