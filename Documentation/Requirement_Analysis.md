# Requirement Analysis — MedChain (Draft v0.1)

## 1. Overview
MedChain is a web platform that manages the medical activity chain
(clinic → doctor → patient → pharmacist) with patient-controlled privacy.
This document defines the high-level requirements for v1.

## 2. Problem Statement
- Medical records are paper-based or scattered across clinics.
- Prescriptions are easy to forge or dispense more than once.
- Patients have no visibility on who accessed their data.
- Pharmacists cannot verify prescription authenticity.
- Clinics and pharmacies lack operational oversight.

## 3. Objectives
- Digitize and centralize the patient's medical record.
- Issue verifiable electronic prescriptions (single dispense).
- Give patients full control over data access (consent).
- Provide role-based dashboards for all stakeholders.
- Maintain an audit trail of critical actions.

## 4. Scope (v1)

### In Scope
- 6 roles: Patient · Doctor · Pharmacist · Clinic Admin · Pharmacy Admin · Platform Admin
- Account registration, approval, and login
- Clinics & pharmacies management
- Medical records creation and viewing
- Electronic prescriptions + dispense flow
- Consent management (grant / revoke)
- Audit log of critical actions
- Role-based dashboards

### Out of Scope (Future Work)
Appointments · Inventory · Payments & insurance · Notifications ·
Mobile app · File attachments · Blockchain layer · External integrations.

## 5. Stakeholders
| Stakeholder | Interest |
|-------------|----------|
| Patient | Own records + privacy control |
| Doctor | Fast record & prescription creation |
| Pharmacist | Verify & dispense prescriptions |
| Clinic Admin | Manage clinic's doctors |
| Pharmacy Admin | Manage pharmacy's pharmacists |
| Platform Admin | Approvals + stats (no medical content) |
| Sponsor (DEPI) | Quality & on-time delivery |

## 6. Business Rules
- BR-01: Prescription dispensed only with active patient consent.
- BR-02: Prescription dispensed once only.
- BR-03: Prescription expires 30 days after issue.
- BR-04: Doctor sees records only with consent.
- BR-05: Doctor/Pharmacist accounts require admin approval.
- BR-06: Admin sees metadata only, not medical content.
- BR-07: All access/modify actions are logged.
- BR-08: Consent revocation takes effect immediately.
- BR-09: Prescription cannot be edited after dispense.
- BR-10: One email = one account, role fixed at registration.

## 7. Functional Requirements (High Level)

### Accounts & Access
- Register as Patient, Doctor, or Pharmacist
- Admin approves or rejects professional accounts
- Secure login with session handling
- Role-based access control (RBAC)

### Clinics & Pharmacies
- Admin creates, edits, deactivates clinics & pharmacies
- Clinic Admin manages doctors of their clinic
- Pharmacy Admin manages pharmacists of their pharmacy

### Medical Records
- Doctor creates records (diagnosis, notes)
- Patient views own records chronologically
- Doctor views patient records only with consent
- Patient search by ID or phone

### Prescriptions
- Doctor issues prescription with multiple items
- Prescription gets a unique code/QR
- Patient views prescriptions and status
- Pharmacist verifies and dispenses
- System prevents double dispense
- Doctor can cancel before dispense

### Consent
- Patient grants consent to a doctor or pharmacist with scope
- Patient revokes consent at any time
- Patient sees all active and revoked consents

### Audit & Admin
- All critical actions logged
- Admin views audit log (metadata only)
- Admin sees summary statistics

## 8. Non-Functional Requirements
| # | Requirement | Target |
|---|-------------|--------|
| NFR-01 | Performance | Page response < 2 seconds |
| NFR-02 | Usability | Dispense flow ≤ 3 steps |
| NFR-03 | Privacy | No access without consent or role permission |
| NFR-04 | Traceability | 100% of critical actions logged |
| NFR-05 | Compatibility | Chrome, Edge, Firefox + mobile browsers |
| NFR-06 | Backup | Daily database backup |
| NFR-07 | Scalability | Easy to add roles/modules later |

## 9. Assumptions
- Users have internet and a device.
- Clinics and pharmacies are centrally managed in v1.
- Patient is the sole decision-maker for consent.
- Prescription is dispensed by one pharmacy (no splitting).

## 10. Constraints
- Timeline: 10 weeks for v1.
- No blockchain in v1.
- No external integrations in v1.
- Tech stack: Go + Gin + PostgreSQL + React.

## 11. Acceptance Criteria (End-to-End)
The v1 is complete when this full scenario works:

> Admin approves a doctor and a pharmacist → Patient grants consent to the doctor →
> Doctor creates a record and issues a prescription → Patient grants consent to the pharmacist →
> Pharmacist dispenses the prescription → Second dispense attempt is rejected →
> Admin sees the action in the audit log without medical content.

## 12. Glossary
| Term | Definition |
|------|------------|
| Consent | Explicit patient approval granting scoped access |
| Prescription | Electronic medication order with items |
| Dispense | Pharmacist action marking prescription as fulfilled |
| Audit Log | Record of critical actions for traceability |
| RBAC | Role-Based Access Control |
| Single Dispense | Rule preventing multiple dispenses of the same prescription |

> Draft — subject to refinement in later revisions.
