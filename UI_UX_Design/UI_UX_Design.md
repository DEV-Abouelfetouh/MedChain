# UI/UX Design — MedChain (Draft v0.1)

## Design Principles

- **Simple & clear** — 3 steps max for common actions (e.g., dispense).
- **Role-aware** — each user sees only what they need.
- **Responsive** — works on desktop and mobile browsers.
- **Trust** — clear consent and audit feedback to the patient.

## Primary Screens (Draft)

| # | Screen | Role |
|---|--------|------|
| 1 | Login / Register | All |
| 2 | Patient Dashboard | Patient |
| 3 | Doctor Dashboard | Doctor |
| 4 | Pharmacist Dashboard | Pharmacist |
| 5 | Admin Dashboard | Admin |
| 6 | Medical Record Detail | Patient / Doctor |
| 7 | Prescription Create | Doctor |
| 8 | Prescription View + QR | Patient |
| 9 | Dispense Screen | Pharmacist |
| 10 | Consent Management | Patient |

## Core Flows (Visual Intent)

- **Issue Prescription:** form with multiple items, clear submit.
- **Dispense:** enter code → validate → show result clearly (✅ / ❌).
- **Consent:** toggle-based grant/revoke with visible status.

## Navigation

- Persistent sidebar (desktop) / bottom nav (mobile).
- Top bar: user info + role badge + logout.
- Every destructive/important action → confirmation dialog.

## Feedback Standards

- Loading indicators on all async actions.
- Toast messages for success/error.
- Empty states with guidance text.

> Draft design — wireframes and visual style to be finalized in Figma.
