## Define Domain Boundaries and Data Product Contracts

**CloudServe Inc.** has these teams producing and consuming data:

- **Support Engineering** — owns ticket data, agent metrics, escalation workflows
- **Product Team** — owns user activity, feature usage, customer health scores
- **Finance** — owns billing, revenue recognition, contract data
- **Sales** — owns CRM accounts, pipeline, opportunity data
- **Platform/Data Engineering** — owns infrastructure, pipelines, catalog

Multiple teams need `customer_id` to join across their datasets. Currently, each team defines "customer" differently (some use account-level, some use user-level).

---

## Requirements

1. **Define 4 data domains** with: name, owning team, scope (what data they own), and 2–3 data products per domain.

2. **Write a full data product contract** for one product from each of two different domains. Each contract must include:
   - Owner
   - Schema (key fields with types)
   - SLA (freshness + availability)
   - Quality checks (at least 2 per product)
   - Access control (who can read, any restrictions)
   - Lifecycle stage (reference: Placeholder → WIP → MVP → Published → Archive)

3. **Define the shared identifier standard** for `customer_id`: format, owning domain, and rules for how other domains reference it.

4. **Draw the responsibility split** between the platform team and domain teams as a table (who owns what).

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- Domain definitions table
- 2 full data product contracts
- Shared identifier specification
- Platform vs. domain responsibility matrix
