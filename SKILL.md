---
name: pira-dashboard-report
description: Create data-driven PIRA Marketing Desk insights deliverables from metrics posted in the Slack channel #pira-dashboard-report. Use when the user asks for a PIRA dashboard report, Marketing Desk report, partner marketing case insights, weekly/monthly/quarterly case summary, stakeholder update, Word document report, Excel workbook, Outlook email draft, or executive summary based on case totals, owner/account/subtype/status/origin/priority/MDF data in #pira-dashboard-report.
---

# PIRA Dashboard Report

## Overview

Create three deliverables from `#pira-dashboard-report`: a full Word document insights report, an Excel insights workbook, and a shortened Outlook email draft. Use the Slack connector to gather posted Marketing Desk/PIRA metrics, synthesize business insights from the data, use the document workflow available in the current environment to produce the `.docx` file, use the spreadsheet workflow to produce the `.xlsx` file, then use the Outlook Email connector to create the draft email.

## Non Optional Output Contract

Always create all three deliverables for every run unless the user explicitly asks for only one specific output. Do not stop after producing a written summary in chat. The task is incomplete until all three of these are created and verified as applicable:

1. A full Word report saved as a `.docx` file.
2. An Excel insights workbook saved as a `.xlsx` file.
3. A saved Outlook email draft.

If one deliverable cannot be created because a required connector, permission, or runtime is unavailable, create the other two deliverables, state exactly which deliverable is blocked, and explain the missing dependency in the final response. Do not silently omit any deliverable.

## Workflow

1. Resolve the Slack channel by searching for `pira-dashboard-report`; prefer the channel named `#pira-dashboard-report`.
2. Determine the reporting window from the user request. If no date range is provided, use the last 7 days.
3. Read recent channel messages for that window. Include bot messages when the channel contains automated dashboard reports or scheduled data posts.
4. Search within the channel for useful metric terms when direct reading is not enough: `cases`, `opened`, `closed`, `owner`, `account`, `subtype`, `status`, `origin`, `priority`, `MDF`, `Marketing Desk`, `NPN`, `current quarter`, `last quarter`, `all time`, `total`.
5. Open relevant threads when a message has replies or looks like a correction, data caveat, revised total, or explanation of report scope.
6. Extract metrics and dimensions from the data posts. Prioritize counts, percentages, quarter-over-quarter movement, closure rate, top owners, top accounts, high-priority share, MDF volume, case origin, subtype, status, and workload concentration.
7. Convert the extracted metrics into stakeholder insights. Explain what the data suggests about partner engagement, workload, support demand, process efficiency, urgent request volume, and areas needing follow-up.
8. Draft the full report, Excel workbook, and shortened email using `references/report-format.md`.
9. Create a professional Word document (`.docx`) for the full report. Include a clear title, date range, insight-led section headings, concise bullets, and tables only where they help readers compare metrics. Render and visually verify the document when the document workflow requires it.
10. Create an Excel insights workbook (`.xlsx`) using the spreadsheet workflow. Follow `references/workbook-format.md` for the first-tab layout and visual structure. Verify key values, formulas, and visible dashboard layout before finalizing.
11. Create the shortened email as an Outlook draft using the Outlook Email connector. Leave the To, CC, and BCC lines empty unless the user provides recipients. Attach files only when the user asks for attachments. Do not send the email.
12. Before final response, confirm that the `.docx`, `.xlsx`, and Outlook draft all exist. If any are missing, continue working or report the explicit blocker.
13. Briefly summarize the created Word report, Excel workbook, and Outlook draft in the final response, including links or citations to the local files and the Outlook draft link when available.

## Source Handling

- Treat Slack messages as source data, not polished report copy.
- Prefer paraphrase and synthesis over long quotation.
- Mention uncertainty when a message is ambiguous, stale, or contradicted by a later message.
- Do not invent owners, statuses, metrics, or dates. Use `Owner not specified` or `Status unclear` where needed.
- Do not make the report about the Slack channel, posting workflow, Salesforce report IDs, or automation process unless those details affect data reliability.
- Use workflow or source notes only to explain data caveats, corrections, missing reports, proxy-derived figures, or scope assumptions.
- If no relevant Slack content is found, say that clearly and ask whether to broaden the date range.

## Monthly Reporting Window

Default to a monthly report. Use these rules:

- If the user names a month, use that full calendar month.
- If the user gives a date range, use the provided range and label it clearly.
- If the user does not specify a month or range, use the previous completed calendar month.
- Use exact dates in filenames, document subtitles, workbook subtitles, and the Outlook subject/body.
- Search Slack for posts within the monthly window and include the latest corrected metric posts for that month.
- When multiple posts report the same metric in the same month, use the latest correction or latest duplicate unless the source says otherwise.
 
## Deliverables

Always produce all three deliverables unless the user explicitly asks for only one. Treat this as a completion requirement, not a preference:

- Full Word report: save as a `.docx` file with a descriptive filename such as `PIRA Marketing Desk Insights Report - YYYY-MM-DD to YYYY-MM-DD.docx`.
- Excel insights workbook: save as a `.xlsx` file with a descriptive filename such as `PIRA Marketing Desk Case Insights - YYYY-MM-DD to YYYY-MM-DD.xlsx`.
- Outlook email draft: create a saved draft with no recipients by default. The body should emphasize key takeaways and omit separate `Data caveats` and `Follow-ups` sections unless the user explicitly asks for them.

Completion checklist before answering the user:

- Confirm the Word `.docx` exists at the saved output path.
- Confirm the Excel `.xlsx` exists at the saved output path.
- Confirm the Outlook draft was created and capture its draft link or ID when the connector returns one.
- If a deliverable is blocked, name the blocker and do not imply that all deliverables were completed.

For the required structure and tone, read `references/report-format.md`.
For the Excel output, also read `references/workbook-format.md`.
