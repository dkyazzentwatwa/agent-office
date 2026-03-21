# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Project Is

An AI agent office orchestration system — a collection of role-definition files (system prompts) for 21+ virtual AI employees, plus an operations hub with dashboards, SOPs, and coordination frameworks. There is no build system, no npm, no compiled code.

## Commands

```bash
# Start local server for live dashboard
python3 OFFICE_OPS/server.py
# → http://localhost:8000/dashboard.html

# Open dashboard statically (no live reload needed)
open OFFICE_OPS/dashboard.html
```

## Architecture

**Hub-and-spoke model:**
- `employee/` — Role definition files (system prompts). Each `[role].md` defines capabilities, tone, output templates, coordination partners, and escalation triggers for one AI employee.
- `OFFICE_OPS/` — Central operations hub:
  - `employees/ROSTER.md` — All agents, capacity utilization, routing rules
  - `coordination/COORDINATION_MATRIX.md` — Cross-functional handoffs, dependency map, escalation paths
  - `processes/DAILY_ROUTINE_SOP.md` — Daily workflow SOP (triage → delegation → monitoring → close)
  - `dashboard.html` — Single-file HTML operations dashboard; reads data from the Markdown files above
  - `server.py` — Minimal Python 3 HTTP server; local only, not hardened for production
  - `reporting/`, `projects/`, `quality/`, `resources/`, `incidents/` — Operational tracking directories

**Operations Manager** is the coordination hub that routes work between agents and escalates to the human decision-maker. All cross-agent workflows are defined in `COORDINATION_MATRIX.md`.

## Conventions

- New role files go in `employee/` with lowercase underscore-separated names (e.g., `employee/data_engineer.md`) and must follow the existing structure: Role & Purpose, Tone & Style, Core Capabilities, Response Guidelines, Output Formats, Coordination, Escalation Triggers.
- Operational Markdown: short, scannable, action-oriented with sentence-case prose, clear headings, and bullet lists.
- Python (`server.py`): PEP 8, 4-space indentation, small readable functions.
- Dashboard changes require manual verification — open `dashboard.html` and confirm roster, coordination, and project content renders without console errors.
