# Codex Instructions

Use this repo with Codex as a local documentation and workflow workspace.

## What Codex should read first

1. `AGENTS.md` - repository rules, structure, verification, and safety expectations
2. `README.md` - human-facing overview and beginner skill menu
3. `OFFICE_OPS/employees/ROSTER.md` - current employee list, capacity, and routing shortcuts
4. `OFFICE_OPS/coordination/COORDINATION_MATRIX.md` - handoffs and escalation paths
5. `skills/*/SKILL.md` - reusable office routines when the user request matches a skill

Current Codex behavior: Codex automatically reads `AGENTS.md` guidance for the repository. Codex repo skills are auto-discovered from `.agents/skills`; this project keeps the beginner-facing skill library in `skills/`, so read the matching `SKILL.md` directly unless the skills are mirrored into `.agents/skills`.

## Beginner skill menu

| User wants to... | Natural prompt | Read |
|------------------|----------------|------|
| Sort email | "Triage these emails." | `skills/email-triage/SKILL.md` |
| Review the day | "Triage my calendar." | `skills/calendar-triage/SKILL.md` |
| Research safely | "Search the web and verify this." | `skills/safe-agent-web-search/SKILL.md` |
| Find the right employee | "Who should handle this?" | `skills/office-manager-router/SKILL.md` |
| Sort mixed task items | "Run daily triage." | `skills/daily-triage/SKILL.md` |
| Get today's quick status | "Give me a standup." | `skills/standup/SKILL.md` |
| Check workload and risks | "Do an office health check." | `skills/office-health-check/SKILL.md` |
| Summarize the week | "Write a weekly brief." | `skills/weekly-brief/SKILL.md` |
| Add a new specialist | "Add a new agent for partnerships." | `skills/onboard-agent/SKILL.md` |

## Operating behavior

- Route each request to the best employee or small group before answering.
- Label the active role at the top of the response, such as `[Operations Manager]`.
- Use the roster and coordination matrix before inventing ownership.
- Prefer smaller beginner skills before heavier routines.
- Do not claim external actions were completed unless tools were actually used.
- Do not place secrets, private customer data, credentials, or sensitive operational data in committed docs.

## Verification

- Documentation or skill changes: sanity-check paths, role names, and references.
- Dashboard changes: open `OFFICE_OPS/dashboard.html` directly in a browser. Do not start a local server.
- Skill changes: confirm each skill folder has a `SKILL.md` with matching `name:` frontmatter.
