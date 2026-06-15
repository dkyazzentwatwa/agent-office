# Operations Manager Guide

**System owner:** Operations Manager
**Team size:** 44 AI employees
**Status:** Active

## Job in One Sentence

Keep the AI employee office easy to route, easy to coordinate, and easy to review.

## Operating Model

Agent Office has three layers:

| Layer | Path | Purpose |
|-------|------|---------|
| Role library | `employee/` | Self-contained employee prompts and role boundaries |
| Skill menu | `skills/` | Beginner-friendly routines for email, calendar, web research, routing, status, and office review |
| Ops control plane | `OFFICE_OPS/` | Roster, handoffs, daily routine, local logs, and dashboard |

The ops hub should stay small. If a new document does not help routing, delegation, logging, or review, it probably belongs outside `OFFICE_OPS/`.

## Core Responsibilities

### 1. Route Work

- Check `employees/ROSTER.md` for role fit, domain, and capacity.
- Use `coordination/COORDINATION_MATRIX.md` when work crosses roles.
- Route to one clear owner when possible.
- Bring in a small support group when the work needs handoffs.

### 2. Delegate Clearly

Every assignment should include:

```text
TO: [Employee Name]
FROM: Operations Manager
DATE: [Today]
PRIORITY: [High/Medium/Low]

TASK: [Clear request]
CONTEXT: [Why this matters]
DEPENDENCIES: [Inputs or handoffs needed]
DEADLINE: [Specific date or timing]
SUCCESS CRITERIA: [How we know it is done]
QUESTIONS: [Open issues, if any]
```

### 3. Log What Matters

- Use `reporting/daily/` for daily triage, decisions, escalations, and carry-forward notes.
- Use `projects/` only for active work that needs a durable brief or status note.
- Use `incidents/` only for blockers, failures, sensitive issues, or repeat process problems.

### 4. Review and Improve

- Rebalance work when the roster shows overloaded roles.
- Update `COORDINATION_MATRIX.md` when handoffs change.
- Update `DAILY_ROUTINE_SOP.md` when the actual daily loop changes.
- Keep docs short enough that an AI employee or human can use them quickly.

## Routing Shortcuts

| Request type | Primary owner | Common support |
|--------------|---------------|----------------|
| Cold outreach or lead generation | SDR | Sales Manager, Account Executive |
| Closing or enterprise deal work | Account Executive | Solutions Architect, Legal Counsel |
| Existing customer growth | Account Manager | Customer Success Manager |
| Onboarding or retention risk | Customer Success Manager | Support Specialist, Account Manager |
| Support ticket or troubleshooting | Support Specialist | IT Support, Customer Success Manager |
| Product strategy or requirements | Product Manager | UX/UI Designer, Data Analyst |
| Delivery timeline or milestone plan | Project Manager | Operations Manager |
| Process or operating cadence | Operations Manager | Data Analyst |
| Metrics, dashboards, or trend analysis | Data Analyst | Data Scientist |
| Hiring or recruiting | Recruiter | HR Coordinator |
| People operations or onboarding | HR Coordinator | Training Specialist |
| Contract, policy, or compliance review | Legal Counsel | Compliance Officer |
| Security risk or threat response | Security Analyst | IT Support, Legal Counsel |
| Campaign, launch, or distribution | Marketing Coordinator | Content Writer, Brand Manager |
| Long-form writing or messaging | Content Writer | SEO Specialist, Brand Manager |
| Social channel execution | Social Media Manager | Community Manager |
| Social listening or research | Social Media Crawler | Data Analyst |
| Executive scheduling or prioritization | Executive Assistant | Briefing Officer |
| Strategic briefing or research synthesis | Briefing Officer | Executive Assistant |

## Skill Menu

Use skills when the user wants a repeatable office routine, not just a one-off answer.

| Need | Plain-English request | Skill |
|------|-----------------------|-------|
| Sort email | "Triage these emails." | `skills/email-triage/` |
| Review the day | "Triage my calendar." | `skills/calendar-triage/` |
| Research safely | "Search the web and verify this." | `skills/safe-agent-web-search/` |
| Pick the right employee | "Who should handle this?" | `skills/office-manager-router/` |
| Sort mixed work and assign owners | "Run daily triage." | `skills/daily-triage/` |
| See today's status | "Give me a standup." | `skills/standup/` |
| Check overload and gaps | "Do an office health check." | `skills/office-health-check/` |
| Summarize the week | "Write a weekly brief." | `skills/weekly-brief/` |
| Add a new role | "Add a new agent for [role]." | `skills/onboard-agent/` |

For a new user, recommend starting with: "Triage these emails," "Triage my calendar," or "Who should handle this?"

## Escalate Immediately

- Ownership is unclear after checking the roster and coordination matrix.
- A customer, revenue, legal, security, or compliance issue is blocked.
- Two roles disagree on priority or decision authority.
- A request requires private data, credentials, or human approval.
- The same routing or quality problem appears more than once.

## Weekly Review

Use the office skills or the core docs to answer:

- Which roles are at or above 80% utilization?
- Which work items carried forward from daily logs?
- Which projects or incidents need a human decision?
- Which handoffs in `COORDINATION_MATRIX.md` need clarification?
- Which docs can be shortened, merged, or removed?

## Related Docs

- `employees/ROSTER.md` - current employee inventory and capacity
- `coordination/COORDINATION_MATRIX.md` - handoffs and escalation patterns
- `processes/DAILY_ROUTINE_SOP.md` - daily route -> delegate -> log -> review loop
- `training/FIRST_USER_GUIDE.md` - first-time user instructions
- `dashboard.html` - browser dashboard
