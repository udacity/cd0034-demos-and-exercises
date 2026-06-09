## Design an Incremental Ingestion Strategy for a SaaS API

**CloudServe Inc.** is integrating a new project management SaaS tool (similar to Jira/Asana) into their lakehouse. The API has these characteristics:

| Attribute | Detail |
|-----------|--------|
| API type | REST, paginated (100 records/page) |
| Auth | OAuth 2.0, token expires every 60 minutes |
| Rate limit | 5,000 requests/hour |
| Entities | Projects, Tasks, Comments, Users |
| Record counts | Projects: 2,000 / Tasks: 150,000 / Comments: 500,000 / Users: 800 |
| Change detection | `updated_at` field on all entities |
| Daily change volume | ~5,000 tasks + ~15,000 comments updated/created |

---

## Requirements

1. **Design the initial load strategy.** How will you extract all records within the rate limit? Estimate how long it will take.

2. **Design the incremental load strategy.** Specify:
   - Change detection method
   - Sync frequency
   - High-water mark storage
   - How you handle deletes (if the API supports soft-delete via a `deleted_at` field)

3. **Define error handling** for:
   - API returns 429 (rate limited)
   - API returns 500 on page 47 of 150
   - OAuth token expires mid-extraction
   - A record fails schema validation

4. **Define how schema evolution is handled** when the SaaS vendor adds a new field to the Tasks entity.

5. **Draw a Mermaid sequence or flow diagram** of the incremental sync process.

---

## Deliverable

Complete your work in the provided notebook. Your response should include:
- Initial load plan with time estimate
- Incremental strategy specification
- Error handling matrix (scenario → response)
- Schema evolution approach
- Mermaid diagram of the sync flow
