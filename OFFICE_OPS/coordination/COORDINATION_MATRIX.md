# Employee Coordination Matrix

**Purpose:** Map interdependencies and handoffs between employees
**Owner:** Operations Manager
**Last Updated:** 2026-05-24

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

### Sales Team Management
```
Sales Manager (coaching & forecast)
  → Sales Development Rep (prospecting targets)
  → Account Executive (pipeline & close rate)
  → Business Development Manager (strategic channel opportunities)
```

### Marketing & Content
```
Product Manager (strategy)
  → Content Writer (creation)
    → Marketing Coordinator (distribution & campaigns)
      → Social Media Crawler (monitoring & insights)
        → Data Analyst (performance metrics)
```

### Marketing & Brand
```
Brand Manager (positioning & identity)
  → Social Media Manager (channel execution)
    → Community Manager (engagement & moderation)
  → SEO Specialist (search visibility)
    → Content Writer (SEO-aligned content)
  → Marketing Coordinator (campaign distribution)
```

### Finance & Accounting
```
CFO (strategy & controls)
  → Financial Analyst (reporting & forecasting)
    → Payroll Specialist (compensation processing)
    → Procurement Specialist (vendor spend)
      → Legal Counsel (contract review)
```

### Technology & Delivery
```
CTO (tech strategy & architecture)
  → DevOps Engineer (infrastructure & deployment)
  → Solutions Architect (solution design & pre-sales)
  → Release Manager (change control & launches)
    → Technical Writer (documentation)
    → Quality Assurance Manager (release readiness)
```

### People & Culture
```
HR Coordinator (talent operations)
  → Recruiter (sourcing & screening)
  → Payroll Specialist (compensation)
  → Training Specialist (onboarding & skill development)
```

### Operations & Leadership
```
Executive Assistant (schedule & priorities)
  ↔ Briefing Officer (intelligence & analysis)
  ↔ Operations Manager (process & efficiency)
    → Project Manager (execution)
      ↔ Data Analyst (metrics & tracking)
```

### Executive & Strategy
```
CEO / Strategy (direction & decisions)
  ↔ CFO (financial oversight)
  ↔ CTO (technical oversight)
  → Briefing Officer (intelligence synthesis)
  → Internal Communications (staff alignment)
  → Investor Relations (external stakeholder comms)
    → Legal Counsel (disclosure review)
```

### Risk & Compliance
```
Legal Counsel (policy & contracts)
  ↔ Security Analyst (threat & policy enforcement)
  ↔ Compliance Officer (regulatory checks & audit readiness)
  ↔ HR Coordinator (employment law)
    → IT Support (security implementation)
```

### Community Support Triage
```
Community Manager (space health and tone)
  ↔ Flow Helper Support Admin (support analysis, routing, and reply drafts)
    → Support Specialist (troubleshooting and unresolved issues)
    → Customer Success Manager (onboarding and retention signals)
    → Operations Manager (process gaps and ownership ambiguity)
    → Security Analyst / Legal Counsel (sensitive risk review)
```

---

## Cross-Functional Dependencies

| Primary | Supports | Context | Handoff Trigger |
|---------|----------|---------|-----------------|
| Account Executive | Customer Success Manager | Account transition | Deal closure |
| SDR | Account Executive | Lead qualification | SQLs ready |
| Sales Manager | SDR | Quota & targeting | Territory/quota set |
| Sales Manager | Account Executive | Pipeline review | Weekly forecast |
| Product Manager | Content Writer | Feature announcement | Launch approved |
| Brand Manager | Content Writer | Brand-aligned content | Brand guidelines updated |
| Brand Manager | Marketing Coordinator | Campaign alignment | Campaign brief approved |
| SEO Specialist | Content Writer | SEO-optimized content | Keyword targets set |
| Marketing Coordinator | Social Media Crawler | Campaign launch | Content scheduled |
| Social Media Manager | Community Manager | Community engagement | Channel content posted |
| Project Manager | All teams | Execution tracking | Project kickoff |
| Data Analyst | All teams | Performance data | Monthly/quarterly |
| Data Scientist | Product Manager | Predictive insights | Experiment results ready |
| Legal Counsel | All teams | Risk clearance | Contract/policy change |
| Compliance Officer | Legal Counsel | Regulatory updates | New regulation identified |
| CFO | Financial Analyst | Financial review | Month-end close |
| Financial Analyst | Operations Manager | Budget variance | Variance >5% flagged |
| Procurement Specialist | Legal Counsel | Contract review | Vendor contract drafted |
| Payroll Specialist | HR Coordinator | Compensation changes | Offer accepted / role change |
| CTO | Release Manager | Architecture decisions | Architecture approved |
| CTO | Solutions Architect | Pre-sales technical support | RFP or demo requested |
| Release Manager | Quality Assurance Manager | Release readiness | Code freeze reached |
| Release Manager | Technical Writer | Documentation | Feature code-complete |
| DevOps Engineer | Security Analyst | Security posture | Infrastructure change |
| HR Coordinator | Recruiter | Hiring | Requisition opened |
| HR Coordinator | Training Specialist | New hire onboarding | Offer accepted |
| Training Specialist | Operations Manager | Process adoption | New SOP published |
| UX/UI Designer | Product Manager | Design handoff | Prototype approved |
| Internal Communications | Executive Assistant | Staff announcements | Leadership message drafted |
| Investor Relations | Legal Counsel | Disclosure review | Board materials prepared |
| Executive Assistant | Operations Manager | Leadership priorities | Daily briefing |
| Briefing Officer | Executive Assistant | Strategic intel | On-demand |
| Support Specialist | Account Manager | Escalated issues | Support ticket |
| Flow Helper Support Admin | Community Manager | Community support triage | New support scan or member-routing issue |
| Flow Helper Support Admin | Support Specialist | Troubleshooting handoff | Unresolved support request |
| Flow Helper Support Admin | Customer Success Manager | Onboarding or retention signal | Overwhelm, churn, or activation risk |
| Flow Helper Support Admin | Security Analyst | Sensitive risk | Credentials, suspicious access, or data exposure |
| Flow Helper Support Admin | Operations Manager | Process improvement | Recurring support pattern or routing gap |

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

### New Release → Documentation
- **Owner:** Release Manager → Technical Writer
- **Trigger:** Feature code-complete
- **What's needed:** Feature spec, user-facing change summary, known limitations
- **Success metric:** Docs published day of release

### Brand Refresh → Social & Content
- **Owner:** Brand Manager → Social Media Manager + Content Writer
- **Trigger:** Brand guidelines updated
- **What's needed:** Updated guidelines, asset library, messaging examples
- **Success metric:** All channels and content templates updated within 1 week

### New Hire → Onboarding
- **Owner:** HR Coordinator → Training Specialist
- **Trigger:** Offer accepted
- **What's needed:** Role brief, team context, day-1 program outline
- **Success metric:** Day-1 program delivered on start date

### Community Question → Support Front Door
- **Owner:** Community Manager → Flow Helper Support Admin
- **Trigger:** Member support question appears in Get Support, Introductions, Start Here, Welcome Checklist, or sanitized DM summary
- **What's needed:** Source link/date, member-facing context, sensitivity check, recommended owner
- **Success metric:** Human-approved reply or escalation prepared with clear routing

---

## Escalation Paths

**When work gets stuck:**
1. Identify which employee owns the issue
2. Check if they need input from a coordinating party
3. If blocked → escalate to Operations Manager
4. If legal/compliance → escalate to Legal Counsel or Compliance Officer
5. If financial → escalate to CFO
6. If technical/architecture → escalate to CTO
7. If urgent/executive → escalate to Executive Assistant
