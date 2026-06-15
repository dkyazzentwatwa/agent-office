---
name: email-triage
description: Use when the user says "triage these emails", "sort my inbox", "what emails need replies", "draft replies", or shares email snippets. Sorts emails into reply, delegate, archive, schedule, and needs-decision buckets without sending anything.
---

# Email Triage

Keep this simple. Help the user decide what deserves attention.

## Step 1 - Get the emails

Use pasted emails, summaries, screenshots transcribed by the user, or connected inbox context if available.

If no email content is available, ask the user to paste the messages or provide inbox access. Do not invent inbox contents.

## Step 2 - Sort each email

Use these buckets:

- **Reply now** - needs a direct response today
- **Delegate** - another Agent Office employee should handle it
- **Schedule** - needs a meeting, reminder, or calendar hold
- **Needs decision** - the human owner must decide before anyone acts
- **Archive/reference** - no action needed now

Flag anything involving money, contracts, legal risk, security, private data, credentials, or upset customers.

## Step 3 - Produce the output

```markdown
# Email Triage

## Reply now
| From/Subject | Why it matters | Suggested reply |
|--------------|----------------|-----------------|

## Delegate
| From/Subject | Owner | Task |
|--------------|-------|------|

## Schedule
| From/Subject | Calendar action |
|--------------|-----------------|

## Needs your decision
- [Email] - [decision needed]

## Archive/reference
- [Email] - [why]
```

Keep reply drafts short and editable. Do not send, archive, delete, unsubscribe, or mark anything read unless the user explicitly asks and the tool is available.
