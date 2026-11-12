---
id: registration-identifier-format-demo-clinic-id
title: "Demo Clinic ID: the format is enforced (DC followed by 6 digits)"
kind: manual
priority: high
feature: registration
workflow: openmrs-registration
requirement: Unique patient identifier
generator: registration
implementations: [implementer-ai-demo-org]
sources: [configs/openmrs/initializer_config/patientidentifiertypes/demo-clinic-identifier-types.csv]
---

# Demo Clinic ID: the format is enforced (DC followed by 6 digits)

## Preconditions

- Signed in as a user who can register patients
- A test server (never production)

## Steps

1. Type a Demo Clinic ID that does not match DC\d{6}
   Expected: The form refuses it

## Test data

```json
{
  "identifier_type": "Demo Clinic ID",
  "format": "DC\\d{6}"
}
```
