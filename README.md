# Catalyst Onboarding System

## Project Overview

The Catalyst Onboarding System is a client onboarding and workflow automation pipeline designed for a financial services organization. It connects four distinct platform layers — intake, CRM, automation, and reporting — into a cohesive, event-driven pipeline that orchestrates the entire client onboarding lifecycle with minimal manual intervention.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.x | Utility scripts, validation logic, automation orchestration |
| Airtable | CRM database for leads and workflow tracking |
| Make.com | Automation engine for workflow orchestration |
| Google Sheets | Reporting dashboard with live metrics |
| Google Forms | Client intake form |
| Hypothesis + pytest | Property-based and unit testing (358 tests) |

## Architecture

```
Intake Form → Webhook → Make.com → Airtable CRM → Google Sheets Dashboard
                                       ↓
                                  Error Log → Admin Notification
```

## Live System Links

The system is fully operational. Click below to inspect each layer:

| Layer | Link |
|-------|------|
| **Automation Workflow** | [Make.com Scenario](https://us2.make.com/public/shared-scenario/c4k8NQeR0sL/integration-webhooks) |
| **Reporting Dashboard** | [Google Sheets Dashboard](https://docs.google.com/spreadsheets/d/176uXQzi_Faz-k_cconH5g9ebniTKMzCj1G1LZvJdrko/edit) |
| **Source Code** | [GitHub Repository](https://github.com/Ramidon0392/catalyst-onboarding-system) |

## Setup Instructions

1. Clone the repository
2. Copy `config/.env.example` to `config/.env` and fill in credentials
3. Install dependencies: `pip install -r requirements.txt`
4. Run tests: `pytest tests/ -v`

## Project Structure

```
/src              - Core Python modules (validation, CRM, automation, reporting)
/tests            - 358 automated tests (unit, integration, property-based)
/docs             - Architecture diagrams, automation SOPs, workflow documentation
/config           - Environment variable templates
/scripts          - Utility scripts (cleanup, reporting, duplicate detection)
```

## Key Features

- **Duplicate Detection**: Email-based deduplication prevents duplicate CRM records
- **Error Handling**: No silent failures — every error is logged with structured metadata
- **Role-Based Access Control**: Only Automation_Engine and Systems_Administrator can write to CRM tables
- **Follow-Up Reminders**: Scheduled automation flags stale leads after 48 hours
- **Real-Time Dashboard**: Metrics refresh on every CRM event (Total Leads, Funnel, Advisor Counts)

## Future Improvements

- Slack/Teams integration for real-time notifications
- ML-based lead scoring from historical conversion data
- Automated advisor assignment based on capacity/specialization
- Client self-service portal for document uploads
- OAuth authentication for webhook endpoint security
