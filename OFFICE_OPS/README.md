# Agent Office Ops Hub

Managed by: **Operations Manager**

`OFFICE_OPS/` is the control plane for the AI employee office. It does not try to be a full company intranet. It keeps the few shared references that help the 44 role files in `employee/` route work, coordinate handoffs, and leave a local operating trail.

## Active Sources

| Path | Use it for |
|------|------------|
| `employees/ROSTER.md` | Role inventory, domains, capacity, and routing shortcuts |
| `coordination/COORDINATION_MATRIX.md` | Cross-role handoffs, escalation paths, and coordination patterns |
| `processes/DAILY_ROUTINE_SOP.md` | The daily route -> delegate -> log -> review operating loop |
| `reporting/daily/` | Local daily logs and triage notes; private by default |
| `projects/` | Optional evidence for active work that spans more than one task |
| `incidents/` | Optional evidence for blockers, failures, or repeat issues |
| `training/FIRST_USER_GUIDE.md` | How a person should work with the office |
| `dashboard.html` | Single-file visual snapshot; open directly in a browser |

## Daily Loop

1. **Route** incoming work with `ROSTER.md` and `COORDINATION_MATRIX.md`.
2. **Delegate** to one employee or a small coordinated group.
3. **Log** important triage, escalations, and decisions in `reporting/daily/`.
4. **Review** open projects, incidents, and capacity before the next routing pass.

## Optional Folders

`projects/` and `incidents/` are intentionally lightweight. Add Markdown files there only when there is real evidence to preserve. Do not create extra department folders or planning docs unless the office is actually using them.

## Dashboard

Open the dashboard directly:

```bash
open OFFICE_OPS/dashboard.html
```

No server, build step, or package install is required.
