# Error Handling and Retries

## Failure is normal

Every automation system should assume:
- APIs time out
- payloads break
- schemas change
- users submit bad data
- credentials expire
- third-party services degrade

## Error categories

### 1. Validation errors
Examples:
- missing fields
- malformed JSON
- unsupported input values

Action:
- reject early
- log details
- notify if needed

### 2. Transient errors
Examples:
- timeout
- 429 rate limit
- temporary 5xx API failure

Action:
- retry with backoff
- cap retry count
- log each attempt

### 3. Permanent errors
Examples:
- invalid API key
- deleted resource
- unsupported endpoint

Action:
- fail fast
- route to human intervention
- create alert

### 4. Business logic errors
Examples:
- duplicate invoice
- lead missing qualification criteria
- approval denied

Action:
- handle as business state, not system crash

## Retry design rules

- only retry transient failures
- use exponential backoff
- set maximum retry counts
- log attempt number
- preserve run context
- prevent duplicate side effects

## Recovery options

- manual replay
- dead-letter queue
- partial reprocessing
- fallback vendor/API
- escalation alert

## Minimum logging for failures

Capture:
- workflow name
- execution ID
- input record ID
- failed step
- timestamp
- error type
- raw error message
- retry count
- external service name
