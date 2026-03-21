---
name: daily-triage
description: Run the daily email and task triage workflow. Processes inbox, delegates to the right agents via the coordination matrix, logs outputs to OFFICE_OPS/reporting/daily/. Use at the start of each workday.
---

# Daily Triage Workflow

Follow `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md` for the full procedure. This skill provides a fast-path checklist.

## Pre-Triage (2 min)

1. Read `OFFICE_OPS/employees/ROSTER.md` — note any agents at >90% utilization (do not route new work to them)
2. Check `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` — confirm active workflows and pending handoffs

## Triage Each Item

For each email or task, apply this decision tree:

```
Is it actionable?
  No → Archive or defer
  Yes ↓
Is it urgent (same-day response required)?
  No → Add to backlog, assign agent
  Yes ↓
Which agent owns this domain?
  → Route via COORDINATION_MATRIX.md
  → If unclear → Operations Manager decides
Is approval required from human owner?
  Yes → Flag and surface immediately
  No → Delegate and log
```

## Delegation Format

When routing to an agent, provide:
- **Task:** [what needs to be done]
- **Context:** [relevant background]
- **Deadline:** [when it's due]
- **Output expected:** [what to deliver back]

## Log Output

Create `OFFICE_OPS/reporting/daily/YYYY-MM-DD-email-triage.md` with:

```markdown
# Daily Triage — [DATE]

## Processed
| Item | Routed To | Action | Deadline |
|------|-----------|--------|----------|
| ...  | ...       | ...    | ...      |

## Pending Human Decision
- [Item requiring owner input]

## Escalations
- [Any active escalations]

## Notes
[Anything unusual or worth flagging]
```
