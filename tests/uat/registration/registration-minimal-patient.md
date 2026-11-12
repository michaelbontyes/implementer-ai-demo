---
id: registration-minimal-patient
title: Register a new patient with the minimum details
kind: automated
priority: high
feature: registration
workflow: openmrs-registration
requirement: Patient registration
automated_by: tests/e2e/registration.spec.ts
generator: registration
locales: [en, fr]
implementations: [implementer-ai-demo-org]
sources: [configs/openmrs/frontend_config/implementer-ai-demo-org-frontend-config.json, configs/openmrs/initializer_config/patientidentifiertypes/demo-clinic-identifier-types.csv, configs/openmrs/initializer_config/idgen/demo-clinic-id-sequence.csv]
---

# Register a new patient with the minimum details

## Preconditions

- Signed in as a user who can register patients
- A test server (never production)

## Steps

1. Open Register patient
   Expected: The registration form opens
2. Enter a test given name and family name, a sex and an estimated age of 30 years
3. Enter a valid Demo Clinic ID (DC followed by 6 digits)
4. Click Register patient
   Expected: The patient chart opens with the new patient in the banner
5. Look at the identifiers in the banner
   Expected: Demo Clinic ID was generated and starts with "DC"
6. Search for the patient by name from the home page
   Expected: The new patient is found

## Test data

```json
{
  "sex": "Female",
  "age_years": 30,
  "generated_prefix": "DC"
}
```
