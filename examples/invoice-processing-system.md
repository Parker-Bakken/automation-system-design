# Invoice Processing System

## Goal

Receive invoices, extract structured fields, validate them against rules, route exceptions for review, and sync approved records into accounting systems.

## System flow

1. Invoice enters system
2. OCR or file parsing
3. Extract fields
4. Validate vendor, amount, date, PO, totals
5. Detect duplicates
6. Route exceptions
7. Approve or reject
8. Sync approved data
9. Log everything

## Recommended architecture

Intake → OCR/Parsing → Extraction → Validation → Duplicate Check → Approval Queue → Accounting Sync → Audit Log

## Key risks

- extraction errors
- duplicate payment risk
- invalid totals
- incorrect vendor matching
- weak audit trail

## Design notes

- treat low-confidence extraction as review-required
- store original file reference
- make approvals auditable
- avoid auto-payment without strict controls
