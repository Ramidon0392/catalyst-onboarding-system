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

## Setup Instructions

1. Clone the repository
2. Copy `config/.env.example` to `config/.env` and fill in credentials
3. Install dependencies: `pip install -r requirements.txt`
4. Run tests: `pytest tests/ -v`

## Live Demo

The system is fully operational with:
- **Airtable CRM**: 3 tables (Leads, Workflow Status, Error Log)
- **Make.com Automation**: Webhook-triggered lead intake with duplicate detection
- **Google Sheets Dashboard**: Real-time metrics across 3 tabs

## Project Structure

```
/src              - Core Python modules (validation, CRM, automation, reporting)
/tests            - 358 automated tests (unit, integration, property-based)
/docs             - Architecture diagrams, automation SOPs, workflow documentation
/config           - Environment variable templates
/scripts          - Utility scripts (cleanup, reporting, duplicate detection)
```

## Future Improvements

- Slack/Teams integration for real-time notifications
- ML-based lead scoring
- Automated advisor assignment
- Client self-service portal
