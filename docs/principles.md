# Design Principles

## 1. Design systems, not isolated automations

A workflow should not be treated as the whole product.  
Every production automation should be designed as part of a broader system with defined inputs, outputs, dependencies, monitoring, and recovery paths.

## 2. Validate early

Validate incoming data as close to the entry point as possible.

Examples:
- required fields exist
- email format is valid
- payload schema is correct
- duplicate requests are blocked
- unsupported event types are rejected

## 3. Make workflows idempotent

If a workflow runs twice with the same input, the result should not create unintended duplicates.

Examples:
- use unique request IDs
- check whether a record already exists before creation
- store processing status before executing side effects

## 4. Separate orchestration from business logic

The orchestration layer should decide:
- what runs
- in what order
- under which conditions

The business logic layer should perform:
- transformations
- scoring
- enrichment
- generation
- routing

## 5. Add human review for high-risk actions

Human approval is often required before:
- sending external communications
- publishing content
- charging money
- deleting records
- escalating legal/compliance-sensitive items

## 6. Log enough to debug later

A production system should capture:
- workflow name
- run ID
- input source
- timestamps
- step-level outcome
- external API response metadata
- error details
- retry count

## 7. Build for failure

Every external dependency will fail eventually.

Design for:
- retries
- fallbacks
- dead-letter handling
- partial completion
- manual replay

## 8. Prefer explicit states

Track state explicitly rather than inferring it from scattered tools.

Examples:
- pending
- validated
- enriched
- awaiting_approval
- processing
- completed
- failed
- archived

## 9. Optimize for maintainability

A workflow that only its creator understands is fragile.

Use:
- standard naming
- modular flows
- documentation
- reusable sub-workflows
- configuration variables

## 10. Measure outcomes, not just executions

“Workflow succeeded” is not the same as “system delivered value.”

Measure:
- throughput
- error rate
- SLA compliance
- approval latency
- business outcome conversion
- cost per successful run
