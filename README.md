# Photon Health (photon-health)

Photon Health is a modern e-prescribing (eRx) platform that lets digital-health organizations create patients, write prescriptions, route orders to pharmacies, and manage fulfillment through a single GraphQL Clinical API. The platform pairs the API with embeddable Elements UI components, webhooks, and a transparent prescription marketplace for pharmacy price and fulfillment comparison.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/photon-health/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/photon-health/refs/heads/main/apis.yml)

## Tags

- Health
- e-Prescribing
- eRx
- Prescriptions
- Pharmacy
- GraphQL

## Timestamps

- **Created:** 2026-06-21
- **Modified:** 2026-06-21

## APIs

### Photon Health Patients API

GraphQL queries and mutations for creating and managing patients - demographics, sex and gender, contact details, allergies, medication history, addresses, and preferred pharmacies - via patient, patients, createPatient, and updatePatient.

- **Human URL:** [https://docs.photon.health/reference/clinical-api](https://docs.photon.health/reference/clinical-api)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Patients
- Demographics
- Allergies

#### Properties

- [Documentation](https://docs.photon.health/docs/sync-patients)
- [API Reference](https://docs.photon.health/reference/clinical-api)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Photon Health Prescriptions API

Write and manage prescriptions with dosing, dispense quantity, refills, days supply, instructions, diagnoses, and effective/expiration dates via prescription, prescriptions, createPrescription, createPrescriptions, and cancelPrescription, including built-in drug-drug interaction screening.

- **Human URL:** [https://docs.photon.health/reference/clinical-api](https://docs.photon.health/reference/clinical-api)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Prescriptions
- eRx
- Refills

#### Properties

- [Documentation](https://docs.photon.health/docs/getting-started)
- [API Reference](https://docs.photon.health/reference/clinical-api)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Photon Health Orders API

Route prescriptions to pharmacies as orders with fills and delivery addresses, and track fulfillment state via order, orders, createOrder, updateOrder, cancelOrder, and the fill query.

- **Human URL:** [https://docs.photon.health/reference/clinical-api](https://docs.photon.health/reference/clinical-api)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Orders
- Fulfillment
- Fills

#### Properties

- [Documentation](https://docs.photon.health/docs/place-orders)
- [API Reference](https://docs.photon.health/reference/clinical-api)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Photon Health Catalog & Medications API

Search the medication catalog and manage organization formularies and reusable prescription templates via medications, medicationConcepts, medicationStrengths, medicationForms, medicationProducts, medicationPackages, medicalEquipment, dispenseUnits, allergens, catalog, catalogs, and the addToCatalog / createPrescriptionTemplate mutations.

- **Human URL:** [https://docs.photon.health/reference/clinical-api](https://docs.photon.health/reference/clinical-api)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Catalog
- Medications
- Templates

#### Properties

- [Documentation](https://docs.photon.health/reference/clinical-api)
- [API Reference](https://docs.photon.health/reference/clinical-api)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Photon Health Pharmacies API

Search pharmacies by name, location, and fulfillment type (PICK_UP or MAIL_ORDER) and retrieve NPI, NCPDP, address, fax, and phone via the pharmacy and pharmacies queries.

- **Human URL:** [https://docs.photon.health/reference/clinical-api](https://docs.photon.health/reference/clinical-api)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Pharmacies
- NPI
- NCPDP

#### Properties

- [Documentation](https://docs.photon.health/reference/clinical-api)
- [API Reference](https://docs.photon.health/reference/clinical-api)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Photon Health Webhooks API

Subscribe to signed webhook events to receive state changes for orders (photon:order:created and related) and prescriptions (photon:prescription:* events), typically used to trigger fulfillment emails and save medications to patient profiles.

- **Human URL:** [https://docs.photon.health/docs/webhooks](https://docs.photon.health/docs/webhooks)
- **Base URL:** `https://api.photon.health/graphql`

#### Tags

- Webhooks
- Events
- Notifications

#### Properties

- [Documentation](https://docs.photon.health/docs/webhooks)
- [API Reference](https://docs.photon.health/docs/order-events)
- [GraphQL](graphql/photon-health-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [OpenAPI](openapi/photon-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/photon-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/photon-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/Photon-Health)
- [LinkedIn](https://www.linkedin.com/company/photon-health)
- [Website](https://www.photon.health)
- [Documentation](https://docs.photon.health)
- [Plans](plans/photon-health-plans-pricing.yml)
- [Rate Limits](rate-limits/photon-health-rate-limits.yml)
- [Fin Ops](finops/photon-health-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
