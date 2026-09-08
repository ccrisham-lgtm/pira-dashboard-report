PIRA Dashboard Reporting Skill

Codex skill for creating PIRA Marketing Desk reporting updates from metrics posted in Slack.

## What This Skill Does

This skill helps generate leadership-ready PIRA Marketing Desk insights from the `#pira-dashboard-report` Slack channel. It is designed to summarize case volume, week-over-week movement, quarter-to-date context, anomalies, data-quality flags, and practical follow-ups.

Depending on the request, the skill can produce:

- Executive summaries
- Slack-ready updates
- Email drafts
- Metric-first tables
- Quarter-to-date summaries
- Raw summaries of the latest Slack metric batch
- Anomaly and data-quality reviews

## Required Access

Each teammate using this skill needs their own access to:

- Codex
- Slack
- The `#pira-dashboard-report` Slack channel
- Any connected tools they want Codex to use for output, such as Outlook, Word, Excel, or SharePoint

The skill provides workflow instructions only. It does not grant access to Slack, Outlook, Salesforce, SharePoint, or any internal systems.

## Repository Contents

```text
SKILL.md
openai.yaml
references/
  insight-style.md
```

`SKILL.md` contains the main workflow and trigger instructions.

`openai.yaml` contains display metadata for Codex.

`references/insight-style.md` contains tone, structure, and style guidance for polished stakeholder-ready outputs.

## Installation

Copy this repository folder into your local Codex skills directory:

```text
~/.codex/skills/
```

The final path should look similar to:

```text
~/.codex/skills/pira-dashboard-reporting/
```

Then start a new Codex task so the skill can be discovered.

## How To Use

Ask Codex for the report or summary you need. Examples:

```text
Run the PIRA dashboard reporting skill.
```

```text
Create a PIRA Marketing Desk executive summary from the latest Slack metrics.
```

```text
Summarize the latest #pira-dashboard-report batch in email format.
```

```text
Create a QTD PIRA Marketing Desk update with anomalies and data-quality flags.
```

You can request a specific output mode:

- `default`
- `executive`
- `slack`
- `email`
- `metrics`
- `anomalies`
- `qtd`
- `raw-summary`

Example:

```text
Use the PIRA dashboard reporting skill in executive mode.
```

## Notes For Teammates

- Use exact Slack metrics when available.
- Treat Slack messages as source data, not final copy.
- Do not invent missing dimensions such as owner, account, status, subtype, or origin.
- Flag corrected or conflicting posts clearly.
- Include caveats when source data is partial, stale, corrected, or proxy-derived.

## Maintenance

When the reporting workflow changes, update `SKILL.md`.

When the preferred tone, format, or stakeholder style changes, update `references/insight-style.md`.
