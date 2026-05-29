# Automation C — Reporting Update

## Trigger
CRM record created or updated.

## Actions
1. Aggregate metrics (Total Leads, New This Week, Scheduled, Completed)
2. Compute operational metrics (Pending Follow-Ups, Avg Response Time, Advisor Counts)
3. Write to Google Sheets Dashboard with refresh timestamp

## Error Conditions
- Dashboard write failure: Log Automation Failure, notify admin
- CRM read failure: Log error, dashboard retains previous values
