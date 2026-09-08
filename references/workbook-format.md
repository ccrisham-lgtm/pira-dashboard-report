# PIRA Marketing Desk Insights Workbook Format

Create an Excel workbook with a first tab similar to the reference workbook tab `Case Insights` from `Copy of Aug 18 report MD all time .xls.xlsx`.

## Workbook Structure

Use three tabs when source data allows:

- `Case Insights`: executive dashboard tab.
- `Source Metrics`: normalized extracted metrics from Slack, with date, report name, metric/dimension, value, and source note.
- `Calculations`: helper tables for chart inputs, percentages, rankings, and quality checks.

If only aggregated Slack totals are available, still create `Case Insights` and `Source Metrics`; omit charts or sections that require unavailable detail.

## First Tab Layout

Model the first tab on the reference `Case Insights` sheet:

- Row 1: large title, such as `Partner Marketing Case Insights` or `PIRA Marketing Desk Case Insights`.
- Row 2: subtitle with total cases, reporting window, and snapshot date.
- Rows 4-7: KPI tiles. Use merged or visually grouped cells for:
  - Total cases or total requests.
  - Active cases, such as New + In Progress + On Hold, when status rows are available.
  - Closure rate when closed and total counts are available.
  - Median days to close for closed cases when duration data is available.
- Rows 8-11: `STORY IN BRIEF`, a concise paragraph summarizing the highest-value insights.
- Middle section: charts when the source data supports them.
  - Monthly Case Openings line chart when monthly/time-series openings are available.
  - Case Status Mix doughnut chart when status distribution is available.
  - All Cases by Sub-Type bar chart when subtype distribution is available.
- Lower-right section: `DATA QUALITY WATCHLIST`, with columns `Field`, `Missing`, `Rate`, and `Why it matters` when missing-data counts are available.
- Lower-right or bottom section: `INITIAL TAKEAWAYS`, numbered 1-4, focused on actions or interpretation.

## Formatting

- Use a clean internal-dashboard look: white background, black section headings, light grid structure, and restrained NVIDIA-adjacent green or dark blue accents.
- Keep KPI tiles large and easy to scan.
- Use typed numbers and percentages, not text-formatted numbers, except for labels.
- Use number formats such as `#,##0` and `0.0%`.
- Keep source notes compact and out of the main visual path.
- Freeze panes only if it improves review; the reference first tab does not require frozen panes.

## Insight Rules

- Build the sheet from the posted Slack data, not from the Slack workflow.
- Calculate percentages only from available numerator and denominator values.
- Do not invent owner, account, status, priority, subtype, or month rows when Slack only provides totals.
- If chart-level detail is missing, replace the chart area with a short table or note showing what detail is needed for that visual.
- When conflicting totals exist, surface them in the data quality or notes area rather than hiding the discrepancy.

## Reference Observed

The provided reference workbook first tab is named `Case Insights`. It contains:

- Title: `Partner Marketing Case Insights`.
- Subtitle: `1,451 cases opened July 2024-August 2026 | Snapshot analyzed August 18, 2026`.
- KPI tiles for total cases, active cases, closed rate, and closed-case median resolution time.
- A `STORY IN BRIEF` narrative.
- Charts titled `Monthly Case Openings`, `Case Status Mix`, and `All Cases by Sub-Type`.
- A `DATA QUALITY WATCHLIST` table with `Field`, `Missing`, `Rate`, and `Why it matters`.
- An `INITIAL TAKEAWAYS` numbered list.
