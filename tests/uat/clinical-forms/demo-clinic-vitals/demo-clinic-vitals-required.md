---
id: demo-clinic-vitals-required
title: "Demo Clinic Vitals: saving empty is blocked on required questions"
kind: automated
priority: high
feature: clinical-forms
form: Demo Clinic Vitals
workflow: openmrs-clinical-encounters
automated_by: tests/e2e/forms.spec.ts
generator: form
implementations: [implementer-ai-demo-org]
sources: [configs/openmrs/initializer_config/ampathforms/demo-clinic-vitals.json]
---

# Demo Clinic Vitals: saving empty is blocked on required questions

## Preconditions

- A test patient with an active visit
- Signed in as a user who can fill "Demo Clinic Vitals"

## Steps

1. Open the form and click Save without answering anything
   Expected: The form is not saved
2. Look at each required question
   Expected: "Weight (kg)", "Temperature (°C)" are marked as required

## Test data

```json
{
  "required": [
    {
      "id": "weight",
      "label": "Weight (kg)"
    },
    {
      "id": "temperature",
      "label": "Temperature (°C)"
    }
  ]
}
```
