## Design a Star Schema from Denormalized Data

**CloudServe Inc.** has a silver-layer table called `interactions_clean` that contains one row per customer interaction:

| Column | Type | Example |
|--------|------|---------|
| interaction_id | string | INT-20260515-001 |
| interaction_date | timestamp | 2026-05-15 14:30:00 UTC |
| channel | string | voice, chat, email |
| customer_id | string | CUST-4421 |
| customer_name | string | Acme Corp |
| customer_industry | string | Manufacturing |
| customer_tier | string | Enterprise |
| agent_id | string | AGT-042 |
| agent_name | string | Sarah Chen |
| agent_team | string | Tier 2 Support |
| duration_sec | int | 340 |
| resolution_status | string | resolved, escalated, pending |
| satisfaction_score | decimal | 4.5 |
| topic | string | billing, technical, onboarding |

They need a gold-layer star schema optimized for Power BI dashboards that answer:
- What's the average handle time by channel and agent team?
- Which customer tier has the highest satisfaction?
- What's the weekly interaction volume trend?

---

## Requirements

1. **Design a star schema** with one fact table and at least 3 dimension tables. Define columns, types, and keys for each.

2. **Identify the grain** of the fact table (what does one row represent?).

3. **Define 3 pre-aggregated KPI columns** that should be computed in the gold layer (not left for BI tools to calculate).

4. **Specify the refresh cadence** and explain why.

5. **Draw a Mermaid entity-relationship diagram** showing the star schema.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- Fact and dimension table definitions (columns + types)
- Grain statement
- Pre-aggregated KPIs with formulas
- Refresh cadence with rationale
- Mermaid ER diagram
