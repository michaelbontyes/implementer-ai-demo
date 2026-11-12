---
id: demo-clinic-vitals-saves
title: Demo Clinic Vitals saves with the required questions answered
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

# Demo Clinic Vitals saves with the required questions answered

## Preconditions

- A test patient with an active visit
- Signed in as a user who can fill "Demo Clinic Vitals"

## Steps

1. Open the form
   Expected: The form opens
2. Answer "Weight (kg)" with "1"
3. Answer "Temperature (°C)" with "1"
4. Click Save
   Expected: A confirmation says the form was saved
5. Open the visit in the patient chart
   Expected: A "Demo Clinic Vitals" encounter shows the answers given

## Test data

```json
{
  "fill": [
    {
      "id": "weight",
      "label": "Weight (kg)",
      "value": "1"
    },
    {
      "id": "temperature",
      "label": "Temperature (°C)",
      "value": "1"
    }
  ],
  "encounter_type": "67a71486-1a54-468f-ac3e-7091a9a79584"
}
```
