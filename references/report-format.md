# PIRA Marketing Desk Insights Report Format

## Full Word Report

Use this structure:

# PIRA Marketing Desk Insights Report
Reporting window: <start date> to <end date>
Source data: Metrics posted in Slack channel `#pira-dashboard-report`

## Strategic Initiatives and Highlights
Write a short opening section in the style of an internal partner marketing update. Focus on what the data shows about partner support demand, Marketing Desk performance, ecosystem engagement, and operational priorities.

## Marketing Desk Key Insights
Write 6-10 insight bullets grounded in the posted metrics. Favor statements such as:
- Total case/request volume for the period.
- Quarter-over-quarter or week-over-week movement when both periods are available.
- Closure rate or open case rate when status data is available.
- Top owner workload concentration when owner data is available.
- Top account or partner concentration when account data is available.
- High-priority share when priority data is available.
- MDF request volume and movement when MDF metrics are available.
- Channel/origin/subtype mix when those dimensions are available.

Use exact counts from Slack. Calculate simple percentages only when numerator and denominator are both available from the source data. Do not estimate.

## Metrics Snapshot
Use a compact table with columns such as Metric, Value, Interpretation, and Caveat. Keep this focused on the business data, not the Slack workflow.

## Observations by Dimension
Add subsections only for dimensions found in the source data:
- Case Volume
- Status and Closure
- Owners and Workload
- Accounts or Partner Segments
- Subtype and Origin
- MDF Requests
- Priority and Urgency

Each subsection should explain what the numbers mean for Marketing Desk planning and partner support.

## Risks and Data Caveats
List only caveats that affect interpretation, such as conflicting totals, retired Salesforce reports, proxy-derived SOQL figures, missing dimensions, or incomplete period comparisons.

## Recommended Follow-Ups
Use action-oriented bullets tied to the data. Include owner and due date when available; otherwise mark them as not specified.

## Source Notes
Keep source notes brief. Include the Slack date range reviewed and important links only when useful. Do not let source notes become a report about the channel or workflow.

## Excel Insights Workbook

Create a workbook in addition to the Word report and Outlook draft. The first tab should be an executive insight dashboard modeled on the reference workbook `Copy of Aug 18 report MD all time .xls.xlsx`, tab `Case Insights`.

Read `workbook-format.md` before creating the workbook.

## Outlook Email Draft

Use this structure:

Subject: PIRA Marketing Desk Insights: <date range or week label>

Hi team,

Here are the key PIRA Marketing Desk insights for <date range>:

- <4-7 highest-signal key takeaways with exact counts and percentages where available>
- <Include meaningful caveats inline only when they materially affect a takeaway, rather than adding a separate caveats section.>

Best,
Claire

Draft behavior:
- Create the email as an Outlook draft by default.
- Leave To, CC, and BCC empty unless recipients are provided.
- Do not include separate `Data caveats` or `Follow-ups` headings unless the user explicitly asks.
- Do not send the email.


## Tone

Use a polished internal partner marketing tone: concise, factual, and insight-led. Avoid overexplaining the collection process. Avoid promotional language. Do not include internal reasoning or tool details in the deliverables.
