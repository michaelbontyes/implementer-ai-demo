---
id: registration-identifier-unique-demo-clinic-id
title: "Demo Clinic ID: two patients cannot share the same value"
kind: automated
priority: high
feature: registration
workflow: openmrs-registration
requirement: Unique patient identifier
automated_by: tests/e2e/registration.spec.ts
generator: registration
implementations: [implementer-ai-demo-org]
sources: [configs/openmrs/initializer_config/patientidentifiertypes/demo-clinic-identifier-types.csv]
---

# Demo Clinic ID: two patients cannot share the same value

## Preconditions

- Signed in as a user who can register patients
- A test server (never production)
- A test patient already registered with Demo Clinic ID "a known value"

## Steps

1. Register another patient with the same Demo Clinic ID
   Expected: Registration is refused because the Demo Clinic ID is already used

## Test data

```json
{
  "identifier_type": "Demo Clinic ID"
}
```
