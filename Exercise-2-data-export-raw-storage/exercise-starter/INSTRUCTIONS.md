## Design a Raw Landing Zone

**CloudServe Inc.** is redesigning their data ingestion. They have four data sources that need to land in S3 as their bronze layer:

| Source | Format | Frequency | Volume |
|--------|--------|-----------|--------|
| User clickstream events | JSON | Real-time (~2,000 events/sec) | ~50 GB/day |
| Billing transactions | CSV | Daily batch export at 2 AM UTC | ~500 MB/day |
| Support tickets (Zendesk API) | JSON | Hourly API poll | ~10,000 records/day |
| Product usage metrics | Parquet | Every 15 minutes from internal service | ~5 GB/day |

---

## Requirements

1. **Design the S3 prefix structure** for the bronze layer. Define the path pattern for each source, including how you partition the data (by date, hour, source, etc.).

2. **Choose the file format** for each source's landing zone. Justify why you'd keep the source format or convert on landing.

3. **Specify the ingestion tool/service** for each source (e.g., Kinesis Firehose, Glue, Step Functions, Lambda). Explain why it fits the source's characteristics.

4. **Define buffering/batching rules** to avoid the small-file problem. For each streaming or high-frequency source, specify the buffer size or time window.

5. **Add lifecycle policies**: Define retention and tiering rules for the bronze layer.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- An S3 prefix structure diagram or table
- A source-to-landing mapping table (source → tool → format → partition → buffer)
- Lifecycle policy definitions
