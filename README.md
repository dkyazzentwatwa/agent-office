# 🏢 AI Agent Office

> A complete virtual office of role-defined AI agents — with a coordination framework, operations hub, and live dashboard. Fork it, customize it, run your own AI-powered team.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Agents](https://img.shields.io/badge/agents-43_roles-indigo.svg)
![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen.svg)

---

## What This Is

A **hub-and-spoke AI agent office**: role-specific system prompts ("employees") coordinated through a central operations framework. Each agent has defined capabilities, tone, output formats, coordination partners, and escalation triggers. The Operations Manager routes work between all agents and escalates decisions to you.

No build system. No package manager. No external API required. Runs in any AI chat interface using markdown files as system prompts.

---

## 👥 The Team (43 Agents)

| Domain | Roles |
|--------|-------|
| 🧭 Leadership | CEO / Strategy, Executive Assistant, Briefing Officer, Internal Communications |
| 💼 Sales | SDR, Account Executive, Account Manager, Sales Manager, Business Development Manager |
| 📣 Marketing | Marketing Coordinator, Content Writer, Brand Manager, Social Media Manager, SEO Specialist, Community Manager, Social Media Crawler |
| 🛠 Product | Product Manager, UX/UI Designer, Technical Writer |
| 💻 Technology | CTO, DevOps Engineer, Solutions Architect, Release Manager |
| ⚙️ Operations | Operations Manager, Project Manager, Quality Assurance Manager, Procurement Specialist, Facilities Manager |
| 🎧 Support | Support Specialist, Customer Success Manager |
| 🧑‍💼 People | HR Coordinator, Recruiter, Training Specialist, Payroll Specialist |
| 📊 Analytics | Data Analyst, Data Scientist |
| 💰 Finance | CFO, Financial Analyst, Investor Relations |
| ⚖️ Legal / Risk | Legal Counsel, Compliance Officer, Security Analyst |
| 💻 IT | IT Support |

---

## 🚀 Quick Start

**1. Activate an agent**

Open any file in `employee/` and paste it as your system prompt. Each file is fully self-contained.

**2. Open the dashboard**

```bash
open OFFICE_OPS/dashboard.html
```

Double-click `OFFICE_OPS/dashboard.html` — no server needed, works in any browser.

**3. Customize for your company**

- Replace `[Your Company]` and `[Your Name]` in `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md`
- Update `OFFICE_OPS/employees/ROSTER.md` with your team's capacity
- Edit `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` for your handoff logic

---

## 🖥 Using with Claude Desktop (Cowork)

This project is built to work natively with [Claude Desktop](https://claude.com/download) via the **Cowork** tab — open your local folder as a persistent project and Claude reads your agent files automatically every session.

### Setup

1. Open Claude Desktop → **Cowork** tab
2. Click **Projects** → **+** → **"Use an existing folder"**
3. Select your local `agent-office` directory → **Create**

Claude automatically reads `CLAUDE.md` at session start, giving it full project context — no re-explaining needed.

### Recommended workflow

- Activate the **Operations Manager** (`employee/operations_manager.md`) as your system prompt and start delegating
- Reference any file by name — Claude can read `ROSTER.md`, `COORDINATION_MATRIX.md`, or any role file directly
- Write daily logs to `OFFICE_OPS/reporting/daily/` — gitignored, stays local

### Connect external tools via MCP

| Tool | What it unlocks |
|------|----------------|
| 📧 Gmail | Executive Assistant reads and drafts emails |
| 📅 Google Calendar | Scheduling and availability checks |
| 📝 Notion | Project tracking and knowledge base |
| 🐙 GitHub | Code review and issue management |
| 💬 Slack | Team communication routing |

To add MCP servers: **Settings → Developer → Edit Config** in Claude Desktop.
See the [MCP documentation](https://modelcontextprotocol.io) for setup instructions.

---

## 📅 Daily Workflow

Defined in `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md`:

| Time | Activity |
|------|----------|
| 8:00–8:30 AM | Dashboard check, email triage, calendar review |
| 8:30 AM–12:00 PM | Delegate via coordination matrix, process backlog |
| 1:00–4:00 PM | Monitor delegated work, ad-hoc requests, cross-role coordination |
| 4:00–5:00 PM | Task close-out, daily log, prep for tomorrow |

Log daily work to `OFFICE_OPS/reporting/daily/YYYY-MM-DD-email-triage.md` — gitignored so operational data stays local.

---

## 🏗 Architecture

```
You (Human Owner)
       │
       ▼
Operations Manager ◀──────────── all escalations route here
       │
       ├──▶ CEO / Strategy ◀──▶ CFO ◀──▶ CTO
       │         └──▶ Briefing Officer ◀──▶ Executive Assistant
       │         └──▶ Investor Relations, Internal Communications
       │
       ├──▶ Sales:  SDR → AE → Account Manager → CSM → Support
       │         └──▶ Sales Manager, Business Development Manager
       │
       ├──▶ Marketing: Brand Manager → Social Media Manager → Community Manager
       │         └──▶ SEO Specialist → Content Writer → Marketing Coordinator
       │
       ├──▶ Technology: CTO → DevOps Engineer, Solutions Architect
       │         └──▶ Release Manager → QA Manager, Technical Writer
       │
       ├──▶ Finance: CFO → Financial Analyst → Payroll Specialist, Procurement
       │
       ├──▶ Product: Product Manager → UX/UI Designer
       ├──▶ Project Manager
       ├──▶ Legal Counsel ◀──▶ Compliance Officer ◀──▶ Security Analyst
       ├──▶ HR Coordinator ◀──▶ Recruiter, Training Specialist
       ├──▶ Data Analyst, Data Scientist
       └──▶ IT Support, Facilities Manager
```

Full handoff logic → `OFFICE_OPS/coordination/COORDINATION_MATRIX.md`

---

## ➕ Adding New Agents

1. Create `employee/[role_name].md` (lowercase underscores)
2. Follow the structure: **Role & Purpose → Tone & Style → Core Capabilities → Response Guidelines → Output Formats → Coordination → Escalation Triggers**
3. Add to `OFFICE_OPS/employees/ROSTER.md`
4. Update `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` with new handoffs

See `GAP_ANALYSIS.md` for a prioritized list of roles to add next.

---

## 📁 Project Structure

```
agent-office/
├── employee/                       # Role-definition files (system prompts)
│   ├── operations_manager.md
│   ├── executive_assistant.md
│   └── ... (41 more roles)
├── OFFICE_OPS/                     # Central operations hub
│   ├── dashboard.html              # Live dashboard (open in browser)
│   ├── OPERATIONS_GUIDE.md         # Operations Manager quick-start
│   ├── employees/ROSTER.md         # All agents, capacity, routing rules
│   ├── coordination/               # Cross-agent handoffs & dependencies
│   ├── processes/                  # Daily workflow SOPs
│   ├── reporting/daily/            # Operational logs (gitignored)
│   ├── projects/                   # Active project tracking
│   ├── quality/                    # Quality standards & metrics
│   ├── resources/                  # Capacity planning
│   ├── training/                   # Onboarding & playbooks
│   └── incidents/                  # Incident log
├── skills/                         # Workflow skills
│   ├── onboard-agent/              # Create new agent roles
│   ├── daily-triage/               # Daily triage workflow
│   └── office-health-check/        # Weekly health review
├── AGENTS.md                       # Repo guidelines
└── GAP_ANALYSIS.md                 # Expansion roadmap
```

---

## 📄 License

MIT — fork, customize, and use freely.
