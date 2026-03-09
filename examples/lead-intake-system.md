# Lead Intake System

## Goal

Capture leads from forms, enrich company/person data, score lead quality, notify the sales team, and store records in a CRM or database.

## System flow

1. Form submission or webhook intake
2. Validate required fields
3. Normalize company and contact data
4. Check for duplicates
5. Enrich with external APIs
6. Score lead
7. Route by score
8. Notify team
9. Store logs and status

## Recommended architecture

Trigger → Validation → Deduplication → Enrichment → Scoring → Routing → CRM Write → Slack Alert → Logging

## Key risks

- duplicate leads
- bad email/domain data
- enrichment failures
- noisy low-quality leads
- routing mistakes

## Design notes

- use email/domain as part of dedupe logic
- separate enrichment from scoring
- add fallback if enrichment provider fails
- notify only on qualified score threshold
- log all rejected leads for later review

## Example states

- received
- validated
- duplicate
- enriched
- scored
- routed
- stored
- failed
