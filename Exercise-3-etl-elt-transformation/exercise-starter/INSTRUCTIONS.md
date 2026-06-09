## Write Data Quality Rules for Bronze → Silver

**CloudServe Inc.** has a bronze table called `support_tickets_raw` that lands from the Zendesk API every hour. Here's a sample of the raw data:

```json
{"ticket_id": "TKT-90421", "created_at": "2026-05-15T14:32:00Z", "customer_email": "jane@acme.com", "subject": "Login failure", "priority": "high", "status": "open", "assigned_agent": "agent_042", "resolution_time_hrs": null}
{"ticket_id": "TKT-90421", "created_at": "2026-05-15T14:32:00Z", "customer_email": "jane@acme.com", "subject": "Login failure", "priority": "high", "status": "resolved", "assigned_agent": "agent_042", "resolution_time_hrs": 2.5}
{"ticket_id": null, "created_at": "2026-05-15T15:01:00Z", "customer_email": "not-an-email", "subject": "", "priority": "critical", "status": "open", "assigned_agent": null, "resolution_time_hrs": -3}
{"ticket_id": "TKT-90499", "created_at": "invalid-date", "customer_email": "bob@widgets.io", "subject": "Billing question", "priority": "low", "status": "open", "assigned_agent": "agent_007", "resolution_time_hrs": null}
```

The target silver table is `support_tickets` with enforced schema and clean data.

---

## Requirements

1. **Define at least 6 data quality rules** for the bronze → silver transformation. For each rule specify:
   - Rule name
   - What it checks
   - Action on failure (reject, fix, flag, or default)

2. **Apply your rules to the sample data above.** For each of the 4 records, state which rules it violates and what happens to it.

3. **Define the silver table schema** with column names, data types, and constraints.

4. **Specify how duplicates are handled** (which key, which record wins).

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- A data quality rules table
- A record-by-record analysis of the sample data
- The silver table schema definition
- Deduplication strategy
