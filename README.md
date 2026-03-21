# AI Agent Office

A documentation-driven AI agent orchestration system — a full virtual office of role-defined AI agents with a coordination framework, operations hub, and live dashboard.

Fork this template to spin up your own AI-powered team for any company, product, or workflow.

---

## What This Is

This project defines a **hub-and-spoke AI agent office**: a set of role-specific system prompts (the "employees") coordinated through a central operations framework. Each agent has defined capabilities, tone, output formats, coordination partners, and escalation triggers. The Operations Manager agent routes work between all other agents and escalates decisions to the human owner.

There is no build system, no package manager, and no external API required. The system runs in any AI chat interface (Claude, ChatGPT, etc.) using the markdown files as system prompts.

---

## Repository Structure

```
agent-office/
├── employee/                    # Role-definition files (system prompts)
│   ├── operations_manager.md
│   ├── executive_assistant.md
│   ├── account_executive.md
│   └── ... (16 more roles)
├── OFFICE_OPS/                  # Central operations hub
│   ├── dashboard.html           # Operations dashboard (open in browser, no server needed)
│   ├── OPERATIONS_GUIDE.md      # Operations Manager quick-start guide
│   ├── DASHBOARD_README.md      # Dashboard setup guide
│   ├── employees/
│   │   └── ROSTER.md            # All agents, capacity, routing rules
│   ├── coordination/
│   │   └── COORDINATION_MATRIX.md  # Cross-agent handoffs and dependencies
│   ├── processes/
│   │   └── DAILY_ROUTINE_SOP.md    # Daily workflow SOP
│   ├── reporting/daily/         # Your operational logs (gitignored locally)
│   ├── projects/                # Active project tracking
│   ├── quality/                 # Quality standards and metrics
│   ├── resources/               # Capacity planning
│   ├── training/                # Onboarding and playbooks
│   └── incidents/               # Incident log
├── AGENTS.md                    # Repo guidelines for AI agents
├── GAP_ANALYSIS.md              # Role gap analysis and expansion roadmap
└── README.md
```

---

## Included Roles (19 Agents)

| Domain | Roles |
|--------|-------|
| Leadership Support | Executive Assistant, Briefing Officer |
| Sales | SDR, Account Executive, Account Manager |
| Marketing | Marketing Coordinator, Content Writer, Social Media Crawler |
| Product | Product Manager |
| Operations | Operations Manager, Project Manager |
| Support | Support Specialist, Customer Success Manager |
| People | HR Coordinator, Recruiter |
| Analytics | Data Analyst |
| Legal / Risk | Legal Counsel, Security Analyst |
| IT | IT Support |

---

## Quick Start

### 1. Use a role as a system prompt

Open any file in `employee/` and paste its contents as the system prompt in your AI interface. Each file is self-contained — the agent will behave according to its role definition.

### 2. Open the operations dashboard

Double-click `OFFICE_OPS/dashboard.html` or run:

```bash
open OFFICE_OPS/dashboard.html
```

### 3. Customize for your company

- Replace `[Your Company]` and `[Your Name]` placeholders in `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md`
- Edit `OFFICE_OPS/employees/ROSTER.md` to reflect your team's capacity
- Update `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` for your handoff logic

---

## Daily Workflow

`OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md` defines a repeatable daily routine:

1. **Morning (8:00–8:30 AM):** Dashboard check, email triage, calendar review
2. **Active Work (8:30 AM–12:00 PM):** Delegate via coordination matrix, process backlog
3. **Follow-Up (1:00–4:00 PM):** Monitor delegated work, ad-hoc requests, cross-role coordination
4. **Daily Close (4:00–5:00 PM):** Task close-out, update daily log, prep for tomorrow

Log your daily work to `OFFICE_OPS/reporting/daily/YYYY-MM-DD-email-triage.md` — this directory is gitignored so your operational data stays local.

---

## Adding New Agents

1. Create `employee/[role_name].md` using lowercase underscores
2. Follow the existing structure: Role & Purpose → Tone & Style → Core Capabilities → Response Guidelines → Output Formats → Coordination → Escalation Triggers
3. Add the role to `OFFICE_OPS/employees/ROSTER.md`
4. Update `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` with any new handoffs

See `GAP_ANALYSIS.md` for a prioritized list of roles to add.

---

## Architecture

```
Human Owner
    │
    ▼
Operations Manager ◀──────────── all escalations route here
    │
    ├──▶ Executive Assistant ◀──▶ Briefing Officer
    ├──▶ Sales (SDR → AE → Account Manager → CSM)
    ├──▶ Marketing (Coordinator → Content Writer → Social Media)
    ├──▶ Product Manager
    ├──▶ Project Manager
    ├──▶ Legal Counsel ◀──▶ Security Analyst
    ├──▶ HR Coordinator ◀──▶ Recruiter
    ├──▶ Data Analyst
    └──▶ IT Support
```

Full handoff logic: `OFFICE_OPS/coordination/COORDINATION_MATRIX.md`

---

## Using with Claude Desktop (Cowork)

This project is designed to work natively with [Claude Desktop](https://claude.com/download) via the **Cowork** tab, which lets you open a local folder as a persistent project so Claude reads your agent files automatically in every conversation.

### Setup

1. Open Claude Desktop and click the **Cowork** tab
2. Click **Projects** in the left panel → **+** to create a new project
3. Select **"Use an existing folder"** and pick your local `agent-office` directory
4. Name the project (e.g. "Agent Office") and click **Create**

Claude will now automatically read `CLAUDE.md` at the start of every session, giving it full context about the project structure, roles, and conventions — no need to re-explain anything.

### Recommended workflow

- Open a conversation, activate the **Operations Manager** agent (paste `employee/operations_manager.md` as your system prompt or attach the file), and start delegating tasks
- Claude can read any file in the project directly — reference `OFFICE_OPS/employees/ROSTER.md`, `COORDINATION_MATRIX.md`, or any role file by name
- Write daily triage logs to `OFFICE_OPS/reporting/daily/` locally — they're gitignored so they never get committed

### Connecting external tools via MCP

Claude Desktop supports MCP (Model Context Protocol) servers that give agents real-time access to external tools. Useful integrations for this setup:

| Tool | What it enables |
|------|----------------|
| Gmail | Executive Assistant can read/draft emails |
| Google Calendar | Scheduling, availability checks |
| Notion | Project tracking, knowledge base |
| GitHub | Code review, issue management |
| Slack | Team communication routing |

To add MCP servers: **Settings → Developer → Edit Config** in Claude Desktop. See the [official MCP docs](https://modelcontextprotocol.io) for server setup instructions.

---

## License

MIT — fork, customize, and use freely.
