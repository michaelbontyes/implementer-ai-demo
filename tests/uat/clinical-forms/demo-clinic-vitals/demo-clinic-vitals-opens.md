---
id: demo-clinic-vitals-opens
title: Demo Clinic Vitals opens on every page
kind: automated
priority: high
feature: clinical-forms
form: Demo Clinic Vitals
workflow: openmrs-clinical-encounters
automated_by: tests/e2e/forms.spec.ts
generator: form
locales: [en, fr]
implementations: [implementer-ai-demo-org]
sources: [configs/openmrs/initializer_config/ampathforms/demo-clinic-vitals.json]
---

# Demo Clinic Vitals opens on every page

## Preconditions

- A test patient with an active visit
- Signed in as a user who can fill "Demo Clinic Vitals"

## Steps

1. Open the patient chart and start "Demo Clinic Vitals" from Clinical forms
   Expected: The form opens without an error
2. Go to the page "Vitals"
   Expected: The page shows "Vital signs"

## Test data

```json
{
  "pages": [
    "Vitals"
  ]
}
```
