## Write an Architecture Decision Record

**CloudServe Inc.** must choose a query engine for their new lakehouse. The gold-layer Iceberg tables are built on S3. They need to serve:
- 12 Tableau dashboards (currently on Redshift)
- 25 ad-hoc analysts running SQL
- An ML pipeline reading large datasets nightly

The two finalists are:

**Option A: Amazon Athena (serverless)**
- Pay-per-query ($5/TB scanned)
- No infrastructure to manage
- Native Iceberg support
- Cold-start latency: 2–5 seconds
- Integrates with Lake Formation for governance

**Option B: Redshift Serverless**
- Pay per RPU-hour (~$0.375/RPU-hour)
- Sub-second cached query results
- Familiar to existing team (already using Redshift)
- Requires Redshift Spectrum config for Iceberg/S3
- Separate governance from Lake Formation

Current query volume: ~200 queries/day, scanning ~500 GB/day total.

---

## Requirements

1. **Write a complete ADR** using this structure:
   - **Status**: (Accepted/Proposed/Deprecated)
   - **Context**: What problem are you solving? Why now?
   - **Options Considered**: At least 2 options with pros and cons for each
   - **Decision**: Which option and why
   - **Trade-offs**: Genuine downsides of your chosen option (at least 3)
   - **Consequences**: What changes as a result of this decision

2. **Estimate monthly cost** for both options given the stated query volume.

3. **Identify one scenario** where you would revisit this decision (what would trigger a switch to the other option).

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- A full ADR in the structured format above
- Cost comparison calculation
- Decision reversal trigger
