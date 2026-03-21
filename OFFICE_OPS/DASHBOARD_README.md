# AI Agent Office Dashboard

A single-file HTML operations dashboard for managing your AI employee office. No server, no dependencies — just open and use.

---

## Quick Start

Double-click `dashboard.html` or run:

```bash
open OFFICE_OPS/dashboard.html
```

That's it. Works in any modern browser.

---

## Dashboard Sections

### 1. Employee Roster & Capacity
- All employees with utilization percentages
- Visual capacity bars (green = more available)
- Sorted by domain

### 2. Active Projects & Status
- Project status (🟢 Green / 🟡 Yellow / 🔴 Red)
- Timeline and blockers
- Quick view of what's in progress

### 3. Coordination Flows
- The 4 main workflow paths: Sales Pipeline, Marketing & Content, Operations & Leadership, Risk & Compliance
- Visual handoff mapping

### 4. Office Health Summary
- Average team utilization
- Number of active projects
- Key alerts and bottlenecks

---

## Updating the Data

All dashboard data lives in the `<script>` section at the top of `dashboard.html`. Edit the `ROSTER_DATA`, `PROJECTS_DATA`, and `COORDINATION_DATA` arrays directly.

---

## Design

- Anthropic-branded with black gradient background
- Indigo + pink accent colors
- Clean card layout, mobile responsive

---

**Owner:** Operations Manager
