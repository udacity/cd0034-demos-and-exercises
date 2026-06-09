## Map Consumers to Lakehouse Layers

**CloudServe Inc.** has completed their medallion architecture. Now they need to connect consumers to the right layer. Here are the consumers requesting data access:

| Consumer | Need | Latency Tolerance | Technical Skill |
|----------|------|-------------------|-----------------|
| Executive dashboards (Power BI) | Weekly KPI summaries (revenue, CSAT, volume) | Hours | Low (no SQL) |
| Data science team | Raw interaction transcripts for model training | Days | High (Python, SQL) |
| Product managers | Customer health scores for account reviews | Same-day | Medium (basic SQL) |
| Real-time alerting service | Escalation events for on-call routing | Seconds | High (API consumer) |
| Finance team | Monthly revenue reconciliation against billing system | Daily | Medium (Excel/BI) |
| ML inference pipeline | Enriched customer profiles for personalization | Minutes | High (API consumer) |

Available layers:
- **Bronze:** Raw, append-only, schema-on-read
- **Silver:** Cleansed, conformed, entity-level tables
- **Gold:** Pre-aggregated, star schema, governed data products

---

## Requirements

1. **Assign each consumer to the appropriate layer** (bronze, silver, or gold). Justify each choice based on their needs.

2. **Specify the access method** for each consumer (Athena ODBC, Athena API, direct S3 read, scheduled export, streaming).

3. **Identify one consumer that should NOT read from the lakehouse directly.** Explain what serving layer or pattern is more appropriate.

4. **Define access controls** for at least 2 consumers where column or row-level restrictions are needed.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- Consumer-to-layer mapping table with justifications
- Access method for each consumer
- One alternative serving pattern recommendation
- Access control definitions
