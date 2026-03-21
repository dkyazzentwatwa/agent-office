---
name: standup
description: Use when the user says "standup", "what's on today", "quick status", "what are we working on", or asks for a snapshot of current work. Generates a fast status report across active tasks, blockers, and agent capacity.
---

# Standup Report

Generate a fast status snapshot across all active work. Designed to take under 2 minutes to read.

## Step 1 — Read current state

1. Most recent file in `OFFICE_OPS/reporting/daily/` — yesterday's triage log
2. Any files in `OFFICE_OPS/projects/` — active projects
3. `OFFICE_OPS/employees/ROSTER.md` — agent utilization

## Step 2 — Produce the standup

```markdown
# Standup — [DATE]

## 🟢 In Progress
- [Active task or project] — [owner agent] — [expected completion]
- [Active task or project] — [owner agent] — [expected completion]

## 🔴 Blocked / Needs Decision
- [Blocked item] — blocked by: [reason] — owner: [agent or human]

## 📋 On Deck Today
- [Task to be started today] — [assigned agent]
- [Task to be started today] — [assigned agent]

## ⚠️ Watch Items
- [Anything at risk or worth monitoring — no action needed yet]

## Agent Capacity Flags
- Overloaded (>90%): [list or "none"]
- At capacity (80–90%): [list or "none"]
```

Keep it short. If there's nothing in a section, omit it entirely.
