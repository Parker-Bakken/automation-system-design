# Deployment Checklist

## Before launch

- [ ] workflow purpose is documented
- [ ] inputs and outputs are defined
- [ ] validation rules are documented
- [ ] retry rules are documented
- [ ] failure paths are defined
- [ ] logging is implemented
- [ ] alerts are configured
- [ ] human review points are defined
- [ ] secrets are stored securely
- [ ] test payloads exist
- [ ] duplicate prevention is in place
- [ ] rollback or replay path exists

## After launch

- [ ] monitor first 10 runs manually
- [ ] review failure logs daily
- [ ] measure time-to-completion
- [ ] review unexpected edge cases
- [ ] tighten prompts and schemas
- [ ] update docs based on real failures
