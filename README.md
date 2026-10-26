# Photon Health (photon-health)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
