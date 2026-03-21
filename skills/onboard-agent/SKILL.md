---
name: onboard-agent
description: Use when the user says "add a new agent", "create a new role", "hire a [role]", "onboard a [role]", or wants to add a new employee to the office. Guides through role definition, capability scoping, coordination setup, and roster update.
---

# Onboard New Agent

You are helping create a new AI employee role file for the agent-office system.

## Step 1 — Define the role

Ask the user (if not already provided):
- What is the role title?
- What is the primary function of this role?
- Which department does it belong to?

## Step 2 — Create the role file

Create `employee/[role_name].md` using lowercase underscores. Use this exact structure:

```markdown
# [Role Title]

## Role & Purpose
[1-2 sentence description of what this agent does and why it exists]

## Tone & Style
- [Tone descriptor, e.g. "Professional and analytical"]
- [Communication style, e.g. "Direct, data-driven responses"]
- [Format preference, e.g. "Use structured lists and clear headings"]

## Core Capabilities
- [Capability 1]
- [Capability 2]
- [Capability 3]
- [Add as needed]

## Response Guidelines

**Always:**
- [Behavior to always exhibit]
- [Behavior to always exhibit]

**Never:**
- [Behavior to avoid]
- [Behavior to avoid]

## Output Formats

### [Template Name]
[Template structure or example output]

## Coordination

**Works closely with:**
- [Role Name] — [reason/handoff trigger]
- [Role Name] — [reason/handoff trigger]

**Receives requests from:**
- Operations Manager (routed tasks)
- [Other role if applicable]

**Escalates to:**
- Operations Manager — [escalation trigger]

## Escalation Triggers
- [Situation that requires escalation]
- [Situation that requires escalation]
```

## Step 3 — Update ROSTER.md

Add the new role to `OFFICE_OPS/employees/ROSTER.md` with:
- Role name
- Department
- Utilization % (start at 0%)
- Capacity notes

## Step 4 — Update COORDINATION_MATRIX.md

If the new role has handoffs with existing agents, add the relevant flow to `OFFICE_OPS/coordination/COORDINATION_MATRIX.md`.
