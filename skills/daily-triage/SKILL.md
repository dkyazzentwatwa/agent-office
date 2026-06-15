---
name: daily-triage
description: Use when the user says "run daily triage", "do daily triage", "start the day", shares a mixed batch of emails/calendar/tasks, or asks to delegate today's work across Agent Office. For email-only use email-triage; for calendar-only use calendar-triage.
---

# Daily Triage

Use this only for a mixed daily pass. For a small email-only or calendar-only request, use the simpler `email-triage` or `calendar-triage` skill.

## Step 1 - Read current state

Read these files before routing:

1. `OFFICE_OPS/employees/ROSTER.md` - role inventory, capacity, and escalation routing
2. `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` - active handoffs and cross-functional flows
3. `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md` - daily operating loop and escalation rules

If the user has not provided actual inbox/task items, ask for the items or produce only a routing plan.

## Step 2 - Triage each item

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

## Step 3 - Route with capacity

Use the best role fit first, then capacity:

- Avoid assigning new work to roles above 90% utilization unless they are the only appropriate owner.
- At 80-90% utilization, route only priority work or pair with a lower-utilization support role.
- If ownership is unclear, route to Operations Manager for decision.
- If private data, credentials, legal risk, security risk, or a business decision is involved, flag for human approval.

## Step 4 - Delegate clearly

When routing to an agent, use this format:

```text
TO: [Employee Name]
FROM: Operations Manager
DATE: [Today]
PRIORITY: [High/Medium/Low]

TASK: [Clear request]
CONTEXT: [Relevant background]
DEPENDENCIES: [Inputs or handoffs needed]
DEADLINE: [Specific date or timing]
SUCCESS CRITERIA: [What done means]
QUESTIONS: [Open issues, if any]
```

## Step 5 - Log output

Create `OFFICE_OPS/reporting/daily/YYYY-MM-DD-email-triage.md` with:

```markdown
# Daily Triage — [DATE]

## Processed
| Item | Routed To | Action | Deadline |
|------|-----------|--------|----------|
| ...  | ...       | ...    | ...      |

## Pending Human Decision
- [Item requiring owner input]

## Delegated Work
- [Owner] - [task] - [deadline] - [success criteria]

## Escalations
- [Any active escalations]

## Carry-Forward
- [Open item] - [next action] - [owner]

## Notes
[Anything unusual or worth flagging]
```

If the user asks for triage in chat only, still include the same sections without saving a file.
