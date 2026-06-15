---
name: standup
description: Use when the user says "standup", "what's on today", "quick status", "what are we working on", "morning update", or asks for a snapshot of current work. Generates a concise status report across active tasks, blockers, today’s priorities, and agent capacity.
---

# Standup Report

Generate a fast status snapshot across all active work. Designed to take under 2 minutes to read.

## Step 1 — Read current state

1. Most recent Markdown file in `OFFICE_OPS/reporting/daily/` — yesterday's triage log, if one exists
2. Any Markdown files in `OFFICE_OPS/projects/` — optional active project evidence
3. Any Markdown files in `OFFICE_OPS/incidents/` — optional blocker or failure evidence
4. `OFFICE_OPS/employees/ROSTER.md` — agent utilization

Ignore `.gitkeep` and folder README files as operational evidence. If no logs or project evidence exist, say the standup is based on roster capacity only.

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

Keep it short. If there is nothing in a section, omit it entirely. Do not save a standup file unless the user asks.
