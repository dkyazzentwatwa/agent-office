---
name: calendar-triage
description: Use when the user says "triage my calendar", "review my day", "what meetings need prep", "find calendar conflicts", "plan my schedule", or shares calendar events. Sorts meetings into prepare, attend, reschedule, delegate, and protect-focus-time actions.
---

# Calendar Triage

Help the user see the day clearly and protect attention.

## Step 1 - Get the calendar

Use pasted events, a shared daily agenda, screenshots transcribed by the user, or connected calendar context if available.

If no calendar data is available, ask for the events or calendar access. Do not invent events.

## Step 2 - Review the day

Look for:

- Back-to-back meetings
- Missing prep time
- Conflicting events
- Meetings without a clear purpose
- Calls that need notes, briefs, or follow-up
- Work blocks that should be protected

## Step 3 - Sort actions

Use these buckets:

- **Prepare** - needs a brief, agenda, notes, or decision list
- **Attend** - keep as-is
- **Reschedule** - conflict, low value, or bad timing
- **Delegate** - another Agent Office employee can draft prep or follow-up
- **Protect** - focus time, admin time, break, or recovery buffer

## Step 4 - Produce the output

```markdown
# Calendar Triage - [DATE]

## Top priorities
1. [Most important event or decision]
2. [Second priority]
3. [Third priority]

## Meeting actions
| Time | Event | Action | Prep needed |
|------|-------|--------|-------------|

## Conflicts or overload
- [Issue] - [recommended fix]

## Prep list
- [Meeting] - [what to prepare]

## Suggested schedule changes
- [Change] - [why]
```

Do not create, move, cancel, or invite people to meetings unless the user explicitly asks and the tool is available.
