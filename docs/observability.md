# Observability

## Why observability matters

Without observability, an automation system becomes impossible to trust at scale.

You need to know:
- what ran
- what failed
- where it failed
- how often it fails
- how long it takes
- whether it delivered the intended business result

## Minimum observability stack

### Logs
Track:
- workflow start
- workflow completion
- step completion
- step failure
- retries
- approvals
- downstream notifications

### Metrics
Measure:
- runs per day
- success rate
- retry rate
- median execution time
- failure by step
- cost per run
- human review rate

### Alerts
Alert on:
- repeated failures
- backlog growth
- credential/auth errors
- SLA breaches
- abnormal cost spikes

## Example dashboard questions

- Which workflow fails most often?
- Which step causes the most retries?
- What is the average time from intake to completion?
- How many items are waiting for approval?
- Which integrations are unstable this week?
