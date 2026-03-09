# Architecture Patterns

## 1. Linear pipeline

Best for:
- simple sequential processing
- low-volume internal workflows

Flow:
Trigger → Validate → Transform → Execute → Notify → Log

Pros:
- easy to understand
- fast to build

Cons:
- brittle at scale
- hard to recover mid-process

---

## 2. Fan-out / fan-in

Best for:
- parallel enrichment
- multi-API lookups
- media generation

Flow:
Trigger → Split into parallel tasks → Aggregate results → Continue processing

Pros:
- faster throughput
- clean for independent steps

Cons:
- more complex error handling
- aggregation logic required

---

## 3. Queue-based async processing

Best for:
- high-volume systems
- rate-limited APIs
- long-running jobs

Flow:
Intake → Queue → Worker → Result store → Notification

Pros:
- resilient
- scalable
- handles spikes well

Cons:
- requires more infrastructure
- debugging is more complex

---

## 4. State machine pattern

Best for:
- multi-step systems with approvals or retries
- complex business workflows

Flow:
Entity moves through explicit states until completion

Pros:
- easy to reason about
- strong auditability
- cleaner recovery logic

Cons:
- more planning required up front

---

## 5. Event-driven architecture

Best for:
- systems with many downstream consumers
- modular automations

Flow:
Event occurs → event emitted → subscribers react independently

Pros:
- loosely coupled
- extensible

Cons:
- event sprawl
- tracing becomes harder

---

## 6. Human-in-the-loop pattern

Best for:
- AI-generated outputs
- sensitive business actions
- ambiguous classifications

Flow:
Process → confidence check → approval/review → continue or reject

Pros:
- safer
- improves quality

Cons:
- slower
- requires review operations

---

## Pattern selection guide

Choose based on:
- volume
- latency tolerance
- failure cost
- number of integrations
- need for approvals
- audit requirements
- team sophistication
