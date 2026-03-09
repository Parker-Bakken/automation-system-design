# Security Considerations

## Security basics for automation systems

Automation systems often touch:
- customer data
- financial data
- credentials
- private internal operations
- AI-generated outputs that may be unsafe or incorrect

## Core practices

### 1. Least privilege
Grant each integration only the permissions it actually needs.

### 2. Secret management
Never hardcode secrets in workflows or repos.
Use environment variables or secret managers.

### 3. Input sanitization
Treat all inbound payloads as untrusted.

### 4. Auditability
High-risk actions should leave a visible audit trail.

### 5. Approval gates
Require human approval before sensitive external actions.

### 6. Data minimization
Store only the data required for the system to function.

## Common risks

- exposed API keys
- insecure webhooks
- accidental duplicate billing or messaging
- prompt injection through user-provided text
- over-permissioned integrations
- sensitive data leakage in logs
