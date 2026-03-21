---
name: office-health-check
description: Use when the user says "health check", "how is the office doing", "check team capacity", "office status", "what's overloaded", or asks for a team overview. Reviews utilization, projects, escalations, and coordination gaps.
---

# Office Health Check

## Step 1 — Read current state

Read these files in order:
1. `OFFICE_OPS/employees/ROSTER.md` — utilization and capacity
2. `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` — active flows and handoffs
3. Any files in `OFFICE_OPS/projects/` — active project status
4. Any files in `OFFICE_OPS/incidents/` — open incidents

## Step 2 — Evaluate against thresholds

| Signal | Healthy | Warning | Critical |
|--------|---------|---------|----------|
| Agent utilization | < 80% | 80–90% | > 90% |
| Open escalations | 0 | 1–2 | 3+ |
| Stalled projects | 0 | 1 | 2+ |
| Coordination gaps | None | Minor | Blocking |

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

Save output to `OFFICE_OPS/reporting/YYYY-MM-DD-health-check.md`.
