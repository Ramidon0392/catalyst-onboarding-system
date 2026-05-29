# Automation A — Lead Intake

## Trigger
New form submission webhook received from Intake Form.

## Actions
1. Parse and validate submission fields (email RFC 5321, phone 10-digit NA)
2. Duplicate check by email against Leads table
3. Create Leads record + Workflow Status record (atomic)
4. Route validation failures to Error Log

## Error Conditions
- CRM timeout: Log Automation Failure, no partial record
- Missing email: Route to manual review
- Invalid phone: Flag for review
- Duplicate email: Suppress new record, update existing
