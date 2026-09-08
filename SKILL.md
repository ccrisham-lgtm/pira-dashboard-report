---
name: pira-marketing-digest
description: Create PIRA Marketing Report Desk digests from NVIDIA Slack report posts. Use when asked to run, summarize, compare, brief, or analyze PIRA Marketing Desk weekly reports from #pira-dashboard-report, including default executive digests, concise Slack/email summaries, leadership updates, anomaly reviews, data-quality reviews, quarter-to-date context, and week-over-week comparisons using marker-bounded Slack batches.
---

# PIRA Marketing Digest

## Operating Rules

- Use Slack channel `#pira-dashboard-report` as the sole runtime data source.
- Detect refresh markers matching `PIRA WEEKLY REFRESH — YYYY-MM-DD`.
- Treat the newest marker-bounded message group as the latest weekly batch.
- Treat the immediately prior marker-bounded message group as the previous weekly batch.
- Do not pull live Salesforce, SharePoint, files, email, or other sources for production digest data unless the user explicitly provides additional data in the request.
- Cite underlying Slack report posts directly for every material metric, comparison, anomaly, or conclusion.
- If a requested metric is not present in Slack, say it is unavailable from the current weekly batch rather than inferring it.

## Slack Collection Workflow

1. Find the channel ID with Slack channel search for `pira-dashboard-report`.
2. Read recent channel history newest first.
3. Locate the newest two marker messages matching `PIRA WEEKLY REFRESH — YYYY-MM-DD`.
4. Build the latest batch from messages at or after the newest marker and before any newer marker.
5. Build the previous batch from messages at or after the prior marker and before the newest marker.
6. If fewer than two markers are returned, page older channel history until two markers are found or Slack history is exhausted.
7. Read thread replies for marker messages and report posts when replies may contain metrics, attachments, clarifications, or corrections.
8. Preserve Slack permalinks, message timestamps, authors, and thread context for citations.

## Batch Parsing

Extract only what is present in the Slack posts:

- Reporting period and refresh date.
- Total cases or requests.
- Opened, closed, active, new, in-progress, on-hold, declined, or backlog counts.
- Closure rate, median or average close time, 90th percentile or long-tail indicators.
- Priority mix, especially High priority volume and share.
- Sub-type/request mix, especially Content Review/Creation, PR and/or Blogs, MDF requests, events/speaker requests, branding questions, CIB questions, and Other.
- Partner/account concentration, top accounts, top owners, owner workload concentration, and partner type segmentation.
- Month, week, quarter-to-date, or fiscal-period context.
- Missing-field counts/rates and other data-quality notes.
- Any explicit explanations, caveats, partial-period warnings, corrections, or source-system notes.

Normalize labels conservatively. Keep original labels in citations or tables when label changes could alter meaning.

## Analysis

- Compare latest vs previous batch for every repeated metric that appears in both batches.
- Show absolute change and percent change when both values are available and mathematically valid.
- Call out directional movement when exact calculations are not possible.
- Add quarter-to-date context when the batch includes QTD, month-by-month, or fiscal-period values.
- Distinguish volume change from mix change. Example: fewer total cases can still hide a higher share of High priority work.
- Watch for concentration risk: top owners/accounts/sub-types carrying an outsized share of work.
- Watch for service-health risk: active backlog growth, slower close times, high-priority spikes, and long-tail closure increases.
- Watch for reporting limits: partial months, missing fields, blank sub-types/accounts/partner types, duplicate records, stale dates, or inconsistent status totals.
- Adapt the depth of analysis to the data available. Prefer a tight, accurate digest over filler.

## Output Modes

Use the mode the user requests. If no mode is specified, use `default`.

- `default`: Executive summary, week-over-week metric changes, quarter-to-date context where available, anomalies/data-quality flags, and 3-5 what-matters-most takeaways.
- `executive`: Short leadership-ready narrative with the story in brief, strategic implications, and only the most important metrics.
- `slack`: Concise Slack-ready update with bullets, no long tables, and links/citations inline.
- `email`: Polished email draft with subject, summary, key changes, flags, and recommended follow-ups.
- `metrics`: Metric-first table of latest, previous, delta, percent delta, and citation.
- `anomalies`: Exceptions, data quality, possible root causes, and recommended checks.
- `qtd`: Quarter-to-date view with run-rate, partial-period caveats, and comparison to prior available period.
- `raw-summary`: Structured inventory of what the Slack batch contains, with minimal interpretation.

## Default Format

Use this structure unless the user asks for another format:

1. **Executive Summary** - 3-5 sentences that explain the story, not just the numbers.
2. **Week-over-Week Changes** - compact table with metric, latest, previous, change, interpretation, and Slack citation.
3. **Quarter-to-Date Context** - include only if available; otherwise state that QTD context was not present in the latest Slack batch.
4. **Anomalies & Data Quality** - missing fields, partial-period caveats, status mismatches, spikes, dips, long-tail closure issues, or concentration concerns.
5. **What Matters Most** - 3-5 numbered takeaways, each action-oriented and grounded in cited evidence.
6. **Source Notes** - refresh dates used, batch boundary assumptions, and any unavailable data.

## Style Guidance

Read [references/insight-style.md](references/insight-style.md) when producing a polished digest, leadership update, or any output where tone/depth matters.

## Citation Standard

- Use direct Slack citations for facts, metrics, and claims.
- Prefer message permalinks when the Slack tool returns them.
- If a permalink is unavailable, cite channel name plus message timestamp and author.
- For tables, put citations in a dedicated column or immediately after the interpreted claim.
- Never cite the SharePoint examples as data sources for a live digest; they are style references only.

## Failure Handling

- If the channel is not visible, tell the user Slack cannot access `#pira-dashboard-report` and ask them to confirm connector access.
- If no marker is found, ask for the latest marker text or request that the weekly refresh post include `PIRA WEEKLY REFRESH — YYYY-MM-DD`.
- If only one marker is found, produce a latest-batch summary and clearly state that week-over-week comparison is unavailable.
- If messages appear incomplete, cite what was available and list the missing pieces needed for a complete digest.
