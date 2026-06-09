## Build a Phased Migration Plan with Rollback Triggers

**CloudServe Inc.** needs to migrate their reporting from Redshift to Athena + Iceberg. Here's their current state:

- **Redshift** (2-node dc2.large, $6,400/mo): 12 Tableau dashboards connected, 3 Glue jobs writing to it, 25 active users running ad-hoc queries
- **Target**: Athena querying Iceberg tables on S3 (gold layer already built and validated in dev)
- **Constraint**: Finance closes books on the 5th of each month — no disruption allowed during days 1–7
- **Timeline**: Must complete within 60 days

---

## Requirements

1. **Create a 2-phase migration plan** (Phase 1: Days 1–30, Phase 2: Days 31–60). For each phase specify:
   - 4–6 concrete tasks
   - Dependencies between tasks
   - Measurable success criteria for the phase

2. **Define the dual-running strategy.** How do both systems operate in parallel? How do you validate that Athena results match Redshift?

3. **Define 3 rollback triggers** — specific, measurable conditions that would cause you to revert a consumer back to Redshift. For each trigger, specify the action and recovery time.

4. **Identify at least 3 risks per phase** (6 total) with specific mitigations.

5. **Define success metrics** with baseline (current) and target values for: cost, query latency, and data freshness.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- 2-phase plan with tasks, dependencies, and success criteria
- Dual-running validation approach
- Rollback trigger table (condition → action → recovery time)
- Risk register (6+ risks with mitigations)
- Success metrics table (baseline vs. target)
