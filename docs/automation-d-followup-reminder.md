# Automation D — Follow-Up Reminder

## Trigger
Scheduled check (hourly or daily).

## Actions
1. Query leads where Status = New Lead AND Date Created > 48 hours ago
2. Idempotency check: skip if reminder already exists
3. Append follow-up reminder to Pending Tasks

## Error Conditions
- CRM query failure: Log error, retry on next scheduled run
- CRM write failure: Log error, affected leads retried next run
