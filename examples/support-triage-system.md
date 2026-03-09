# Support Triage System

## Goal

Automatically classify inbound support requests, assign urgency, route to the correct queue, and assist agents with summaries.

## System flow

1. Email or form submission received
2. Parse and validate message
3. Detect account/customer context
4. Classify issue type
5. Score urgency
6. Route to team or queue
7. Generate agent summary
8. Log triage results

## Recommended architecture

Intake → Parsing → Context Lookup → Classification → Priority Scoring → Routing → Summary Generation → Ticket Update → Logging

## Key risks

- incorrect classification
- false urgency scores
- incomplete customer context
- unsafe auto-replies

## Design notes

- keep AI away from irreversible actions
- use human review for sensitive cases
- track model confidence
- separate ticket creation from response generation
