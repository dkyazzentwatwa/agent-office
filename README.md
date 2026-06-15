# Agent Office

> A complete virtual office of role-defined AI agents — with a coordination framework, operations hub, and live dashboard. Fork it, customize it, run your own AI-powered team.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Agents](https://img.shields.io/badge/agents-44_roles-indigo.svg)
![No dependencies](https://img.shields.io/badge/dependencies-none-brightgreen.svg)

---

## What This Is

A **role-based AI office**: self-contained employee prompts coordinated through a small operations control plane. Each employee has defined capabilities, tone, output formats, coordination partners, and escalation triggers. The Operations Manager routes work between employees and escalates decisions to you.

No build system. No package manager. No external API required. Designed for Codex and Claude Cowork using Markdown files as instructions and operating context.

---

## The Team (44 Agents)

| Domain | Roles |
|--------|-------|
| Leadership | CEO / Strategy, Executive Assistant, Briefing Officer, Internal Communications |
| Sales | SDR, Account Executive, Account Manager, Sales Manager, Business Development Manager |
| Marketing | Marketing Coordinator, Content Writer, Brand Manager, Social Media Manager, SEO Specialist, Community Manager, Social Media Crawler |
| Product | Product Manager, UX/UI Designer, Technical Writer |
| Technology | CTO, DevOps Engineer, Solutions Architect, Release Manager |
| Operations | Operations Manager, Project Manager, Quality Assurance Manager, Procurement Specialist, Facilities Manager |
| Support | Support Specialist, Customer Success Manager, Flow Helper Support Admin |
| People | HR Coordinator, Recruiter, Training Specialist, Payroll Specialist |
| Analytics | Data Analyst, Data Scientist |
| Finance | CFO, Financial Analyst, Investor Relations |
| Legal / Risk | Legal Counsel, Compliance Officer, Security Analyst |
| IT | IT Support |

---

## Quick Start

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

## Beginner Skill Menu

Skills are ready-made office routines. You do not need to know the file names. Ask for the outcome you want, and the office should pick the right routine.

### Start here

| If you want to... | Say something like... | What the office does |
|-------------------|-----------------------|----------------------|
| Sort emails | "Triage these emails." | Finds replies, delegations, calendar actions, and decisions |
| Review the day | "Triage my calendar." | Spots prep, conflicts, reschedules, and focus blocks |
| Look something up safely | "Search the web and verify this." | Uses source-backed web research without exposing private data |
| Find the right employee | "Who should own this?" | Routes the request to the best employee or small team |
| Get a quick snapshot | "Give me a standup." | Summarizes active work, blockers, priorities, and capacity flags |

### When you are ready for bigger routines

| If you want to... | Say something like... | What the office does |
|-------------------|-----------------------|----------------------|
| Start the day with multiple inputs | "Run daily triage." | Combines tasks, routing, decisions, and a daily log |
| Check whether the office is overloaded | "Do an office health check." | Reviews capacity, projects, incidents, and coordination gaps |
| Wrap up the week | "Write a weekly brief." | Turns daily logs and project notes into an executive summary |
| Add a new specialist | "Add a new agent for partnerships." | Creates a role prompt and updates the roster and handoffs |

Good starter prompts:

```text
Who should handle this request?
Triage these emails and draft the replies I should send.
Triage my calendar and tell me what needs prep.
Search the web safely and verify this before I use it.
Give me a standup for today.
```

The detailed skill files live in `skills/`, but most users can stay in plain English.

---

## Ops Control Plane

`OFFICE_OPS/` is intentionally small. It is the shared control plane for routing, delegation, daily logs, and review.

| Path | Purpose |
|------|---------|
| `OFFICE_OPS/employees/ROSTER.md` | Role inventory, domains, capacity, and routing shortcuts |
| `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` | Cross-role handoffs and escalation patterns |
| `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md` | Daily route -> delegate -> log -> review workflow |
| `OFFICE_OPS/training/FIRST_USER_GUIDE.md` | First-time user guide |
| `OFFICE_OPS/reporting/daily/` | Local daily logs; gitignored except `.gitkeep` |
| `OFFICE_OPS/projects/` | Optional active-work evidence |
| `OFFICE_OPS/incidents/` | Optional blocker or failure evidence |
| `OFFICE_OPS/dashboard.html` | Single-file browser dashboard |

---

## Using With Codex

Codex reads repository guidance from `AGENTS.md`. Start Codex in this folder and ask it to route, triage, update docs, or run one of the office skills.

Useful starter prompts:

```text
Read AGENTS.md and give me a standup.
Use skills/email-triage/SKILL.md to triage these emails.
Review the office docs for stale references.
```

See `docs/codex-instructions.md` for a copy-paste friendly Codex operating prompt.

---

## Using With Claude Cowork

This project is built to work with [Claude Desktop](https://claude.com/download) Cowork by selecting this local folder and using the repo files as folder context.

### Setup

1. Open Claude Desktop and go to Cowork.
2. Use an existing local folder and select your `agent-office` directory.
3. Add folder instructions from `docs/claude-cowork-instructions.md` if Cowork asks for project-specific guidance.

Cowork can use folder instructions and local files as context. Keep instructions short, and point Claude to the specific file you want it to use when precision matters.

### Recommended workflow

- Start by asking: "Who should handle this?" or "Triage these emails."
- Reference files by name, such as `ROSTER.md`, `COORDINATION_MATRIX.md`, or a role file in `employee/`
- Write daily logs to `OFFICE_OPS/reporting/daily/` — gitignored, stays local

### Connect external tools

| Tool | What it unlocks |
|------|----------------|
| Gmail | Executive Assistant reads and drafts emails |
| Calendar | Scheduling and availability checks |
| Browser/search | Source-backed research |
| GitHub | Code review and issue management |
| Slack | Team communication routing |

Use Claude's current Cowork connector/plugin flow for external tools. Keep folder access narrow and review actions before allowing file deletion or external changes.

---

## Daily Workflow

Defined in `OFFICE_OPS/processes/DAILY_ROUTINE_SOP.md`:

| Time | Activity |
|------|----------|
| 8:00–8:30 AM | Dashboard check, email triage, calendar review |
| 8:30 AM–12:00 PM | Delegate via coordination matrix, process backlog |
| 1:00–4:00 PM | Monitor delegated work, ad-hoc requests, cross-role coordination |
| 4:00–5:00 PM | Task close-out, daily log, prep for tomorrow |

Log daily work to `OFFICE_OPS/reporting/daily/YYYY-MM-DD-email-triage.md` — gitignored so operational data stays local.

---

## Architecture

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

## Adding New Agents

1. Create `employee/[role_name].md` (lowercase underscores)
2. Follow the structure: **Role & Purpose → Tone & Style → Core Capabilities → Response Guidelines → Output Formats → Coordination → Escalation Triggers**
3. Add to `OFFICE_OPS/employees/ROSTER.md`
4. Update `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` with new handoffs

## Project Structure

```
agent-office/
├── employee/                       # Role-definition files (system prompts)
│   ├── operations_manager.md
│   ├── executive_assistant.md
│   └── ... (42 more roles)
├── OFFICE_OPS/                     # Small operations control plane
│   ├── dashboard.html              # Live dashboard (open in browser)
│   ├── OPERATIONS_GUIDE.md         # Operations Manager guide
│   ├── employees/ROSTER.md         # All agents, capacity, routing rules
│   ├── coordination/COORDINATION_MATRIX.md
│   ├── processes/DAILY_ROUTINE_SOP.md
│   ├── training/FIRST_USER_GUIDE.md
│   ├── reporting/daily/            # Operational logs (gitignored)
│   ├── projects/                   # Optional active-work evidence
│   └── incidents/                  # Optional blocker/failure evidence
├── skills/                         # Plain-English office routines
│   ├── email-triage/               # Sort emails into replies, delegation, and decisions
│   ├── calendar-triage/            # Review meetings, conflicts, prep, and focus time
│   ├── safe-agent-web-search/      # Source-backed web research with safety rules
│   ├── office-manager-router/      # Decide who should handle work
│   ├── daily-triage/               # Sort inbox/tasks into owners and decisions
│   ├── standup/                    # Quick status snapshot
│   ├── office-health-check/        # Capacity and risk review
│   ├── weekly-brief/               # End-of-week summary
│   └── onboard-agent/              # Add a new employee role
├── docs/                           # Codex and Claude Cowork instructions
│   ├── codex-instructions.md
│   └── claude-cowork-instructions.md
└── AGENTS.md                       # Codex/repo guidelines
```

---

## License

MIT — fork, customize, and use freely.
