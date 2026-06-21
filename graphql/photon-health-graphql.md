# Photon Health GraphQL API

GraphQL schema for the [Photon Health](https://www.photon.health) Clinical API — a modern
e-prescribing (eRx) platform for managing patients, prescriptions, orders, the medication
catalog, and pharmacies.

**Endpoint:** `https://api.photon.health/graphql` (production) / `https://api.neutron.health/graphql` (Neutron sandbox)
**Authentication:** OAuth2 Bearer token via an `Authorization` header. Access tokens are minted
through an OAuth2 `client_credentials` exchange (`client_id`, `client_secret`, `audience`,
`grant_type=client_credentials`) against `auth.photon.health`.
**Documentation:** <https://docs.photon.health> · API Reference: <https://docs.photon.health/reference/clinical-api>

- Reference: <https://reference.photon.health/>
- GitHub: <https://github.com/Photon-Health>
- Schema: see [`photon-health-schema.graphql`](./photon-health-schema.graphql) (representative SDL, noted)

---

## Overview

Photon Health is a native GraphQL platform. A single endpoint exposes the entire Clinical API
surface — patient management, prescription writing with drug-interaction screening, routing
orders to pharmacies, searching the medication catalog, and pharmacy lookup. State changes are
delivered to integrators through signed webhooks rather than GraphQL subscriptions, and the same
data is surfaced in embeddable Elements UI components.

> The schema in [`photon-health-schema.graphql`](./photon-health-schema.graphql) is a
> **representative SDL** assembled from Photon's public documentation and API reference. It is
> intended to model the documented operations and types; consult the official reference for the
> authoritative, complete schema.

---

## Type inventory

### Scalars
| Scalar | Purpose |
|--------|---------|
| `ID` | Photon resource identifiers |
| `AWSDate` | ISO-8601 calendar dates (e.g. date of birth) |
| `AWSDateTime` | ISO-8601 timestamps |
| `AWSEmail` | Validated email addresses |
| `AWSPhone` | Validated phone numbers |

### Enums
| Enum | Values |
|------|--------|
| `SexType` | MALE, FEMALE, UNKNOWN |
| `GenderType` | MAN, WOMAN, TRANSGENDER_MAN, TRANSGENDER_WOMAN, NON_BINARY, OTHER, UNKNOWN |
| `PrescriptionState` | ACTIVE, EXPIRED, DEPLETED, CANCELED |
| `OrderState` | ROUTING, PENDING, PLACED, COMPLETED, CANCELED, ERROR |
| `FillState` | SCHEDULED, NEW, SENT, CANCELED |
| `FulfillmentType` | PICK_UP, MAIL_ORDER |
| `MedicationType` | RX, OTC |

### Object types

#### Patient
- `Patient` — patient record: id, externalId, name, dateOfBirth, sex, gender, email, phone, allergies, medicationHistory, address, prescriptions, orders, preferredPharmacies
- `PatientAllergy` — allergen plus onset and comment
- `PatientMedication` — self-reported / synced medication history entry
- `Address` — street1, street2, city, state, postalCode, country

#### Prescription
- `Prescription` — prescriber, patient, state, treatment, dispenseQuantity, dispenseUnit, refillsAllowed, refillsRemaining, daysSupply, instructions, notes, diagnoses, effectiveDate, expirationDate, fills
- `Diagnosis` — ICD-10 code and name
- `PrescriptionTemplate` — reusable prescription pattern saved to a catalog

#### Order & Fill
- `Order` — id, externalId, state, patient, pharmacy, fills, address, fulfillment
- `Fill` — id, state, prescription, order, requestedAt, filledAt
- `OrderFulfillment` — type (PICK_UP / MAIL_ORDER), state, carrier, trackingNumber

#### Medication & Catalog
- `Medication` — id, name, type (RX/OTC), codes (RxNorm/NDC), strength, form
- `MedicationConcept` / `MedicationStrength` / `MedicationForm` / `MedicationProduct` / `MedicationPackage` — drug concept hierarchy
- `MedicalEquipment` — supplies and devices
- `Allergen` — allergen catalog entry
- `Catalog` — organization formulary of treatments and templates
- `DispenseUnit` — available dispensing units

#### Pharmacy
- `Pharmacy` — id, name, NPI, NCPDP, address, fax, phone, fulfillmentTypes

#### Prescriber
- `Prescriber` — provider identity (id, name, NPI, address) associated with prescriptions

---

## Query examples

### Look up a patient and their active prescriptions
```graphql
query GetPatient($id: ID!) {
  patient(id: $id) {
    id
    externalId
    name { full }
    dateOfBirth
    sex
    allergies { allergen { name } }
    prescriptions {
      id
      state
      treatment { name }
      refillsRemaining
    }
    preferredPharmacies { id name }
  }
}
```

### Search the medication catalog
```graphql
query SearchMedications($name: String!) {
  medications(filter: { name: $name }, first: 10) {
    id
    name
    type
    strength
    form
  }
}
```

### Find nearby pharmacies that support pickup
```graphql
query FindPharmacies($lat: Float!, $lng: Float!) {
  pharmacies(
    location: { latitude: $lat, longitude: $lng, radius: 25 }
    type: PICK_UP
    first: 10
  ) {
    id
    name
    NPI
    NCPDP
    address { street1 city state postalCode }
  }
}
```

### Create a patient
```graphql
mutation CreatePatient {
  createPatient(
    externalId: "ext-1001"
    name: { first: "Ada", last: "Lovelace" }
    dateOfBirth: "1990-12-10"
    sex: FEMALE
    email: "ada@example.com"
    phone: "+12025550100"
  ) {
    id
    externalId
  }
}
```

### Write a prescription
```graphql
mutation CreatePrescription($patientId: ID!, $medicationId: ID!) {
  createPrescription(
    patientId: $patientId
    medicationId: $medicationId
    dispenseQuantity: 30
    dispenseUnit: "Each"
    fillsAllowed: 3
    daysSupply: 30
    instructions: "Take one tablet by mouth daily."
  ) {
    id
    state
    refillsAllowed
  }
}
```

### Place an order to a pharmacy
```graphql
mutation CreateOrder($patientId: ID!, $fills: [FillInput!]!, $pharmacyId: ID!) {
  createOrder(
    patientId: $patientId
    fills: $fills
    pharmacyId: $pharmacyId
  ) {
    id
    state
    pharmacy { name }
    fills { id state }
  }
}
```

### Cancel an order
```graphql
mutation CancelOrder($id: ID!) {
  cancelOrder(id: $id) {
    id
    state
  }
}
```

---

## Webhooks

Photon delivers state changes as **signed webhook events** (HMAC signature verification) rather
than GraphQL subscriptions. Typical events include:

- `photon:order:created`, `photon:order:placed`, `photon:order:completed`, `photon:order:canceled`
- `photon:prescription:created`, `photon:prescription:depleted`, `photon:prescription:expired`

Order events commonly trigger fulfillment emails; prescription events are used to save
medications to a patient's profile. See <https://docs.photon.health/docs/webhooks>.

## Elements

The same data powers embeddable **Elements** UI components — for example the `photon-client`
container and the `photon-prescribe-workflow` element — which handle authentication and ensure
only authorized prescribers can send prescriptions. See <https://docs.photon.health/docs/elements>.
