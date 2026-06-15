---
name: office-health-check
description: Use when the user says "health check", "how is the office doing", "check team capacity", "office status", "what's overloaded", asks for an office overview, or wants risks across Agent Office. Reviews utilization, projects, incidents, escalations, and coordination gaps.
---

# Office Health Check

## Step 1 — Read current state

Read these files in order:

1. `OFFICE_OPS/employees/ROSTER.md` — utilization and capacity
2. `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` — active flows and handoffs
3. Any Markdown files in `OFFICE_OPS/projects/` — optional active project evidence
4. Any Markdown files in `OFFICE_OPS/incidents/` — optional open incident evidence

If optional folders contain only README files or no project/incident files, say there is no active evidence in that folder.

## Step 2 — Evaluate against thresholds

| Signal | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Agent utilization | < 80% | 80–90% | > 90% |
| Open escalations | 0 | 1–2 | 3+ |
| Stalled projects | 0 | 1 | 2+ |
| Coordination gaps | None | Minor | Blocking |

Treat roles at exactly 90% as at capacity, and roles above 90% as overloaded. If no roles are above 90%, do not invent overload.

## Step 3 — Produce health summary

```markdown
# Office Health Check — [DATE]

## Overall Status: [Green / Yellow / Red]

## Agent Utilization
- Overloaded (>90%): [list or "none"]
- At capacity (80–90%): [list or "none"]
- Available (<80%): [list]

## Active Projects
| Project | Owner | Status | Blockers |
|---------|-------|--------|---------|
| ...     | ...   | ...    | ...     |

## Open Escalations
- [List or "none"]

## Coordination Gaps
- [Any handoffs that are unclear or breaking down]

## Recommended Actions
1. [Action item]
2. [Action item]
```

## Step 4 — Save report

Save output to `OFFICE_OPS/reporting/daily/YYYY-MM-DD-health-check.md` unless the user asks for chat-only output.
