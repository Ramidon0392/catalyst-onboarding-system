# Automation B — Welcome Communication

## Trigger
New record created in Leads table.

## Actions
1. Send welcome email with consultation booking URL
2. Send advisor notification (Full Name, Email, Preferred Meeting Time if non-empty)

## Error Conditions
- Email delivery failure: Log error, continue to advisor notification
- Advisor notification failure: Log error, pipeline continues
- Missing/malformed email: Skip send, set stage to On Hold
