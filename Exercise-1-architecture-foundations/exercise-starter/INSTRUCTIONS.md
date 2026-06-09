## Classify Architecture Pain Points

A mid-size SaaS company, **CloudServe Inc.**, has the following data platform:

- **PostgreSQL (RDS):** Stores transactional data AND serves as the reporting database. Product teams run analytical queries directly against production tables.
- **Amazon S3:** Raw event logs land here from Kinesis, but files are small (avg 200KB), unpartitioned, and in JSON format.
- **Amazon Redshift:** A 2-node cluster running 24/7. Multiple teams write directly to it via Lambda functions. No sort keys or distribution keys defined.
- **Tableau:** Connected directly to Redshift. Dashboard refreshes compete with ETL writes for cluster resources.
- **AWS Glue:** 15 ETL jobs, 4 of which are deprecated but still scheduled. No dependency management between jobs.
- **No data catalog or governance layer exists.**

Monthly cost: ~$18,000/mo.

---

## Requirements

1. Identify **at least 5 distinct pain points** from the description above.
2. For each pain point, classify it into one of these categories:
   - **Cost** — unnecessary spend or waste
   - **Performance** — slow queries, resource contention, bottlenecks
   - **Governance** — missing catalog, lineage, access control, or ownership
   - **Scalability** — inability to grow or add new sources
   - **Reliability** — risk of failure, data loss, or inconsistency

3. For each pain point, name the **specific service** causing it and describe the **measurable impact** (cost figure, performance symptom, or risk).

4. Create a Mermaid diagram of CloudServe's architecture that visually annotates the problem areas.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- A table of pain points (service, category, impact)
- An annotated Mermaid architecture diagram
