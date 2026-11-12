# Demo Clinic

OpenMRS 3 for Demo Clinic, started by Implementer AI from the OpenMRS 3 reference application.

- `docker-compose.yml`: the OpenMRS 3 services. Start with `docker compose up -d`, then open `http://<server>/openmrs/spa`. The first start takes 15 to 20 minutes.
- `configs/openmrs/frontend_config/implementer-ai-demo-org-frontend-config.json`: the frontend configuration of this implementation (read after the reference application's own).
- `configs/openmrs/initializer_config/`: the backend configuration, loaded by Initializer.

## How to change this implementation

Frontend changes show after a page reload. Backend changes load when the backend restarts (a deploy recreates the containers).

### Application name and logo

In `configs/openmrs/frontend_config/implementer-ai-demo-org-frontend-config.json`, set the logo of the navigation bar:

```json
{
  "@openmrs/esm-primary-navigation-app": {
    "logo": { "src": "/openmrs/spa/site-config/logo.png", "alt": "Demo Clinic", "name": "Demo Clinic" }
  },
  "@openmrs/esm-styleguide": {
    "logo": { "src": "/openmrs/spa/site-config/logo.png", "alt": "Demo Clinic" },
    "Brand color #1": "#005d5d",
    "Brand color #2": "#004144",
    "Brand color #3": "#007d79"
  }
}
```

Put the logo file next to the configuration file in `configs/openmrs/frontend_config/`: every file there is served at `/openmrs/spa/site-config/<file>`.

### Patient identifiers

- Identifier types: a CSV file in `configs/openmrs/initializer_config/patientidentifiertypes/` (columns as in the Initializer documentation: Uuid, Name, Description, Required, Format, Format description, Validator, Location behavior, Uniqueness behavior).
- Automatic numbers: a CSV file in `configs/openmrs/initializer_config/idgen/` (an identifier source for that type, with its prefix, length and character set).
- To offer the type at registration, add its uuid to `defaultPatientIdentifierTypes` of `@openmrs/esm-patient-registration-app` in `configs/openmrs/frontend_config/implementer-ai-demo-org-frontend-config.json`.

### Clinical forms

Add the form JSON to `configs/openmrs/initializer_config/ampathforms/` and its translations to `configs/openmrs/initializer_config/ampathformstranslations/`. Use an encounter type and CIEL concepts that exist in the reference application demo content.

### Languages

The allowed languages and the default one are in `configs/openmrs/initializer_config/globalproperties/implementer-ai-demo-org-globalproperties.xml` (`locale.allowed.list`, `default_locale`); the frontend default is `SPA_DEFAULT_LOCALE` in `docker-compose.yml`.
