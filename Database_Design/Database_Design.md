# Database Design — MedChain (Draft v0.1)

## Core Entities

| Table | Purpose |
|-------|---------|
| users | Central accounts (all roles) |
| clinics | Clinic registry |
| pharmacies | Pharmacy registry |
| doctor_profiles | Doctor-specific data (clinic, specialty) |
| pharmacist_profiles | Pharmacist-specific data (pharmacy, license) |
| patients | Patient-specific data |
| medical_records | Diagnosis & notes per visit |
| prescriptions | Issued prescriptions (header) |
| prescription_items | Medication lines of a prescription |
| consents | Patient-granted access permissions |
| audit_logs | Traceability of critical actions |

## Key Relationships

- A **user** has exactly one **role**.
- A **doctor** belongs to a **clinic**.
- A **pharmacist** belongs to a **pharmacy**.
- A **patient** owns many **medical_records** and **prescriptions**.
- A **prescription** has many **items** and one lifecycle:
  `pending → dispensed` (or `cancelled` / `expired`).
- A **consent** links a **patient** to a grantee (doctor or pharmacist)
  with a scope (records / prescriptions / both) and a status.

## Key Rules

- Prescription is dispensed **once only**.
- Prescription expires **30 days** after issue.
- Access requires an active consent or matching role permission.
- All access/modify actions are recorded in `audit_logs`.

## Design Notes

- Roles are separated via profile tables (cleaner than one wide users table).
- `audit_logs` acts as the v1 integrity/traceability layer.
- Blockchain is deferred to future work.

> Draft schema — subject to refinement during implementation.
