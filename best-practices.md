# Dashboard Design Best Practices (5 Must Tips)

1. **Match the chart to the question, not the data type.**
   - Trend over time → line chart
   - Comparing categories → bar chart (horizontal if labels are long)
   - Part-to-whole → stacked bar or treemap (avoid pie/donut past 4-5 slices)
   - Distribution → histogram or box plot
   - Relationship between 2 metrics → scatter plot
   - Single important KPI → big number / KPI card, not a chart

2. **Establish a visual hierarchy — top-left to bottom-right.**
   - Place the most important KPI cards top-left (eyes land there first, Z-pattern reading).
   - Summary/overview visuals up top, drill-down/detail visuals below.
   - Filters and slicers on the left or top, consistently placed across every page.

3. **Limit your color palette to 1 accent color + neutral grays.**
   - Use color only to highlight what matters (e.g., red for below-target, one brand color for the key series).
   - Don't color every category differently — it creates visual noise instead of insight.
   - Keep the same color meaning consistent across all visuals in the dashboard.

4. **Group related visuals together and align them to a grid.**
   - Cluster visuals by theme (e.g., all "sales" charts in one row, all "operations" charts in another).
   - Keep consistent spacing/alignment — misaligned charts read as unpolished even if the data is solid.
   - 4-6 visuals per dashboard page max; split into multiple pages/tabs if there's more.

5. **Remove chart junk — every element should earn its place.**
   - Drop unnecessary gridlines, 3D effects, drop shadows, and redundant legends.
   - Label directly on the chart where possible instead of relying on a legend.
   - Round numbers (e.g., $1.2M not $1,243,921.37) unless precision is the point.
