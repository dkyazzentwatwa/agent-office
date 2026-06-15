# CLAUDE.md

This file provides guidance to Claude Cowork or Claude Code when working with this folder.

## What This Project Is

An AI agent office orchestration system — a collection of role-definition files (system prompts) for 44 virtual AI employees, plus a small operations control plane for routing, coordination, daily logs, and dashboard review. There is no build system, no npm, no compiled code.

## Commands

```bash
# Open dashboard
open OFFICE_OPS/dashboard.html
```

## Architecture

**Control-plane model:**
- `employee/` — Role definition files (system prompts). Each `[role].md` defines capabilities, tone, output templates, coordination partners, and escalation triggers for one AI employee.
- `skills/` — Plain-language office routines for routing work, sorting tasks, checking status, reviewing capacity, and adding roles.
- `OFFICE_OPS/` — Small operations hub:
  - `employees/ROSTER.md` — All agents, capacity utilization, and routing shortcuts
  - `coordination/COORDINATION_MATRIX.md` — Cross-functional handoffs, dependency map, and escalation patterns
  - `processes/DAILY_ROUTINE_SOP.md` — Daily workflow SOP (route → delegate → log → review)
  - `training/FIRST_USER_GUIDE.md` — How a person should work with the office
  - `reporting/daily/` — Local daily logs
  - `projects/` and `incidents/` — Optional evidence folders for active work and blockers
  - `dashboard.html` — Single-file HTML operations dashboard

**Operations Manager** is the coordination hub that routes work between agents and escalates to the human decision-maker. All cross-agent workflows are defined in `COORDINATION_MATRIX.md`.

## Beginner Skill Menu

The `skills/` directory contains ready-made office routines. Users should not need to know skill file names. When their request matches one of these outcomes, read the relevant `SKILL.md` and execute it.

| User wants to... | Natural prompt | Use |
|------------------|----------------|-----|
| Sort email | "Triage these emails." | `skills/email-triage/` |
| Review the day | "Triage my calendar." | `skills/calendar-triage/` |
| Research safely | "Search the web and verify this." | `skills/safe-agent-web-search/` |
| Find the right employee | "Who should handle this?" | `skills/office-manager-router/` |
| Sort a mixed task batch | "Run daily triage." | `skills/daily-triage/` |
| Get today's quick status | "Give me a standup." | `skills/standup/` |
| Check workload and risks | "Do an office health check." | `skills/office-health-check/` |
| Summarize the week | "Write a weekly brief." | `skills/weekly-brief/` |
| Add a new specialist | "Add a new agent for partnerships." | `skills/onboard-agent/` |

When in doubt, start with `skills/office-manager-router/`; it can route the user to the right employee or workflow.

## Conventions

- New role files go in `employee/` with lowercase underscore-separated names (e.g., `employee/data_engineer.md`) and must follow the existing structure: Role & Purpose, Tone & Style, Core Capabilities, Response Guidelines, Output Formats, Coordination, Escalation Triggers.
- Operational Markdown: short, scannable, action-oriented with sentence-case prose, clear headings, and bullet lists.
- Dashboard changes require manual verification — open `dashboard.html` and confirm roster, coordination, and project content renders without console errors.
