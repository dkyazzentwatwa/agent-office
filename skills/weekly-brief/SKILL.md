---
name: weekly-brief
description: Use when the user says "weekly brief", "weekly summary", "wrap up the week", "how did this week go", or asks for a weekly status report. Synthesizes daily logs and project files into an executive summary.
---

# Weekly Brief

Generate an executive summary of the week's activity across all agents, projects, and escalations.

## Step 1 — Gather source data

Read in this order:
1. All files in `OFFICE_OPS/reporting/daily/` — this week's triage logs
2. Any files in `OFFICE_OPS/projects/` — active project status
3. Any files in `OFFICE_OPS/incidents/` — open or resolved incidents
4. `OFFICE_OPS/employees/ROSTER.md` — current utilization

If no daily logs exist for this week, note that and produce a summary from available data only.

## Step 2 — Synthesize across the week

Identify:
- **Volume:** How many items were triaged, delegated, resolved
- **Agent activity:** Which agents were most active, any overloaded
- **Projects:** What progressed, what stalled, what completed
- **Escalations:** Any issues that required owner input
- **Wins:** Notable completions or outcomes
- **Carry-forward:** What's rolling into next week

## Step 3 — Produce the brief

```markdown
# Weekly Brief — Week of [DATE]

## Summary
[2–3 sentence plain-English overview of the week]

## Activity by Domain
| Domain | Items Handled | Key Outcomes |
|--------|--------------|--------------|
| Sales | ... | ... |
| Marketing | ... | ... |
| Operations | ... | ... |
| [etc.] | ... | ... |

## Project Status
| Project | Status | Progress This Week | Next Step |
|---------|--------|--------------------|-----------|
| ... | 🟢/🟡/🔴 | ... | ... |

## Escalations & Decisions
- [Any items that required owner input or are still pending]

## Wins This Week
- [Notable completions, closed deals, shipped work]

## Carry-Forward
- [Open items rolling into next week with owner and deadline]

## Recommended Focus for Next Week
1. [Priority 1]
2. [Priority 2]
3. [Priority 3]
```

## Step 4 — Save report

Save to `OFFICE_OPS/reporting/YYYY-MM-DD-weekly-brief.md` using the week-ending date.
