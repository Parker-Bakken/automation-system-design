# Orchestration Strategies

## What orchestration means

Orchestration is the control layer that determines:
- when workflows run
- what dependencies they have
- how data moves between steps
- what happens when something fails

## Common orchestration models

### 1. Single master workflow
One workflow coordinates everything.

Use when:
- system is small
- debugging simplicity matters
- process is mostly sequential

### 2. Parent-child workflows
A parent workflow triggers smaller sub-workflows.

Use when:
- logic can be modularized
- parts are reusable
- different branches have different responsibilities

### 3. Event-based orchestration
Actions happen in response to emitted events.

Use when:
- multiple downstream systems react differently
- extensibility matters

### 4. Queue-worker orchestration
Jobs are stored in a queue and processed by workers.

Use when:
- tasks are long-running
- failures need safe retries
- rate limits matter

## Orchestration design rules

- keep triggers thin
- isolate side effects
- centralize config where possible
- avoid giant unreadable workflows
- store run identifiers
- make retries explicit
- define timeouts for every external dependency

## Recommended naming convention

- `trigger__new_lead_received`
- `subflow__validate_payload`
- `subflow__enrich_company_data`
- `subflow__generate_summary`
- `action__send_slack_alert`
- `action__write_to_airtable`

## Anti-patterns

- using one workflow for everything
- no separation between validation and execution
- hidden branching logic
- implicit state stored only in memory
- retries without idempotency protections
