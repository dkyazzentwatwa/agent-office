# Employee Coordination Matrix

**Purpose:** Map interdependencies and handoffs between employees  
**Owner:** Operations Manager  
**Last Updated:** 2026-03-20

---

## Primary Coordination Flows

### Sales Pipeline
```
SDR (cold outreach) 
  → Account Executive (qualification & closing)
    → Account Manager (ongoing account management)
      → Customer Success Manager (onboarding & expansion)
        → Support Specialist (ongoing support)
```

### Marketing & Content
```
Product Manager (strategy)
  → Content Writer (creation)
    → Marketing Coordinator (distribution & campaigns)
      → Social Media Crawler (monitoring & insights)
        → Data Analyst (performance metrics)
```

### Operations & Leadership
```
Executive Assistant (schedule & priorities)
  ↔ Briefing Officer (intelligence & analysis)
  ↔ Operations Manager (process & efficiency)
    → Project Manager (execution)
      ↔ Data Analyst (metrics & tracking)
```

### Risk & Compliance
```
Legal Counsel (policy & contracts)
  ↔ Security Analyst (threat & policy enforcement)
  ↔ HR Coordinator (employment law)
    → IT Support (security implementation)
```

---

## Cross-Functional Dependencies

| Primary | Supports | Context | Handoff Trigger |
|---------|----------|---------|-----------------|
| Account Executive | Customer Success Manager | Account transition | Deal closure |
| SDR | Account Executive | Lead qualification | SQLs ready |
| Product Manager | Content Writer | Feature announcement | Launch approved |
| Marketing Coordinator | Social Media Crawler | Campaign launch | Content scheduled |
| Project Manager | All teams | Execution tracking | Project kickoff |
| Data Analyst | All teams | Performance data | Monthly/quarterly |
| Legal Counsel | All teams | Risk clearance | Contract/policy change |
| Executive Assistant | Operations Manager | Leadership priorities | Daily briefing |
| Briefing Officer | Executive Assistant | Strategic intel | On-demand |
| Support Specialist | Account Manager | Escalated issues | Support ticket |
| HR Coordinator | Recruiter | Hiring | Requisition opened |

---

## Critical Handoff Points

### Deal Close → Onboarding
- **Owner:** Account Executive → Customer Success Manager
- **Trigger:** Contract signed
- **What's needed:** Account details, success plan, stakeholder list
- **Success metric:** CSM kickoff meeting within 48 hours

### Feature Launch → Marketing
- **Owner:** Product Manager → Marketing Coordinator
- **Trigger:** Feature approved
- **What's needed:** Launch date, messaging, asset checklist
- **Success metric:** Content ready 2 weeks before launch

### Incident Detection → Remediation
- **Owner:** Security Analyst → IT Support
- **Trigger:** Threat identified
- **What's needed:** Severity, scope, immediate actions
- **Success metric:** Mitigation plan within 4 hours

---

## Escalation Paths

**When work gets stuck:**
1. Identify which employee owns the issue
2. Check if they need input from a coordinating party
3. If blocked → escalate to Operations Manager
4. If legal/compliance → escalate to Legal Counsel
5. If urgent/executive → escalate to Executive Assistant

