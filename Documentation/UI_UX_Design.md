# UI/UX Design — MedChain (Draft v0.1)

## 0. Global Foundations

### Design Principles
- Simple & clear — 3 steps max for common actions.
- Role-aware — each user sees only what they need.
- Responsive — desktop and mobile browsers.
- Trust — clear consent and audit feedback.

### Global Layout
- **Top Bar:** Logo · Page title · User avatar + role badge · Logout
- **Sidebar (desktop) / Bottom Nav (mobile):** role-specific menu items
- **Content Area:** breadcrumb + page content
- **Footer:** version + copyright

### Shared Components
- Data table (sortable, paginated, empty state)
- Form with inline validation
- Toast (success / error / info)
- Confirmation dialog (for destructive actions)
- Loading spinner / skeleton
- Empty state (icon + message + primary CTA)
- Status badge (pending / approved / dispensed / expired / cancelled)

### Global States
| State | Representation |
|-------|----------------|
| Loading | Skeleton placeholders or spinner |
| Empty | Icon + short text + primary action |
| Error | Inline message + retry button |
| Success | Toast + optional redirect |

---

## 1. Authentication Pages

### 1.1 Login — `/login`
- **Access:** Public
- **Layout:** Centered card, logo on top, no sidebar
- **Fields:** Email · Password · "Remember me" checkbox
- **Actions:** Login (primary) · "Create account" link · "Forgot password" link
- **States:** Loading on submit · Error on invalid credentials

### 1.2 Register — `/register`
- **Access:** Public
- **Layout:** Two-step — Step 1 choose role, Step 2 fill details
- **Step 1:** Role cards (Patient / Doctor / Pharmacist)
- **Step 2 Fields (varies by role):**
  - Common: Name · Email · Phone · Password · Confirm Password
  - Doctor: Clinic (dropdown) · Specialty · License Number
  - Pharmacist: Pharmacy (dropdown) · License Number
  - Patient: Date of Birth · Gender · Blood Type (optional)
- **Actions:** Back · Submit
- **Note:** Doctor & Pharmacist accounts go to "Pending Approval" after submit.
- **States:** Success → "Account pending approval" screen for professional roles; Patient → redirect to dashboard.

### 1.3 Forgot Password — `/forgot-password`
- **Access:** Public
- **Fields:** Email
- **Actions:** Send reset link
- **States:** Success message + return to login

---

## 2. Patient Pages

### 2.1 Patient Dashboard — `/patient`
- **Access:** Patient only
- **Layout:** Summary cards (top) + recent activity (below)
- **Widgets:**
  - Card: Total Medical Records
  - Card: Active Prescriptions
  - Card: Active Consents
  - List: Recent Records (title · doctor · date)
  - List: Recent Prescriptions (medication summary · status)
- **Actions:** View all records · View all prescriptions · Manage consents
- **Empty state:** "No records yet — visit a clinic to start your history."

### 2.2 My Medical Records — `/patient/records`
- **Access:** Patient
- **Layout:** Filters bar + table/list
- **Filters:** Date range · Doctor · Clinic · Search by title
- **List items:** Title · Doctor · Clinic · Date · Status badge
- **Actions:** Open record (view detail)
- **Empty state:** informative message + CTA "Find a clinic"

### 2.3 Medical Record Detail — `/patient/records/:id`
- **Access:** Patient (own records only)
- **Layout:** Header (title + date + doctor) + sections
- **Sections:** Diagnosis · Notes · Linked Prescription (if any)
- **Actions:** Download/print (future) · Back to list
- **States:** Loading · Not found · Unauthorized (403 screen)

### 2.4 My Prescriptions — `/patient/prescriptions`
- **Access:** Patient
- **Layout:** Filter chips (All / Pending / Dispensed / Expired) + cards
- **Card contents:** Doctor name · Issue date · Status badge · Medication count
- **Actions:** Open detail · Show QR

### 2.5 Prescription Detail + QR — `/patient/prescriptions/:id`
- **Access:** Patient
- **Layout:** Two columns (details left, QR/action right on desktop; stacked on mobile)
- **Left:** Doctor · Clinic · Issue date · Expiry · Medication items table (name · dosage · frequency · duration)
- **Right:** QR code + unique code text (copyable) · Status badge · Dispensed-by (if dispensed)
- **Actions:** Copy code · Show QR full-screen
- **States:** Pending (waiting for dispense) · Dispensed (show timestamp & pharmacy) · Expired · Cancelled

### 2.6 Consent Management — `/patient/consents`
- **Access:** Patient
- **Layout:** Tabs (Active / Revoked) + list of consents
- **Add Consent:** Modal with fields:
  - Grantee type (Doctor / Pharmacist)
  - Grantee (searchable dropdown)
  - Scope (Records / Prescriptions / Both)
- **List item:** Grantee name + role · Scope · Granted date · Status · Revoke button
- **Actions:** Grant (new) · Revoke (with confirmation)
- **States:** Empty ("No consents yet — you control who sees your data")

### 2.7 Patient Profile — `/patient/profile`
- **Access:** Patient
- **Fields:** Name · Phone · Date of Birth · Gender · Blood Type · Emergency Contact
- **Actions:** Save changes · Change password link
- **States:** Read-only email (no edit) · Success toast on save

---

## 3. Doctor Pages

### 3.1 Doctor Dashboard — `/doctor`
- **Access:** Doctor only
- **Widgets:**
  - Card: Patients seen today
  - Card: Prescriptions issued this week
  - Card: Pending consents from patients (info)
  - List: Recent records created
  - List: Recent prescriptions issued

### 3.2 Patient Search — `/doctor/patients`
- **Access:** Doctor
- **Layout:** Search bar (top) + results list
- **Search by:** Patient ID or Phone
- **Results:** Name · Age · Gender · Last visit date · "Open file" button
- **Actions:** Open patient file
- **States:** Empty query · No results · Loading

### 3.3 Patient File (Doctor view) — `/doctor/patients/:id`
- **Access:** Doctor (only if consent is active)
- **Layout:** Two columns — profile summary + tabs (Records / Prescriptions)
- **Profile summary:** Name · Age · Blood type · Active consents (read-only)
- **Tabs:**
  - Records: list + "New Record" button
  - Prescriptions: list + "New Prescription" button
- **Actions:** Create record · Create prescription
- **States:** No consent → block with message "Patient has not granted access"

### 3.4 Create Medical Record — `/doctor/patients/:id/records/new`
- **Access:** Doctor
- **Fields:** Title · Diagnosis · Notes (rich text) · Optional linked prescription
- **Actions:** Save · Cancel
- **States:** Validation errors · Success → redirect to patient file

### 3.5 Create Prescription — `/doctor/patients/:id/prescriptions/new`
- **Access:** Doctor
- **Layout:** Header (patient info) + dynamic item list
- **Fields (header):** Issue date (auto) · Notes (optional)
- **Item fields (repeatable):** Medication name · Dosage · Frequency · Duration · Notes
- **Actions:** Add item · Remove item · Issue prescription · Cancel
- **States:** Validation (at least one item) · Success → show generated code + redirect to detail

### 3.6 My Prescriptions — `/doctor/prescriptions`
- **Access:** Doctor
- **Layout:** Filter by status + table
- **Columns:** Patient · Issued date · Status · Items count · Actions (View / Cancel)
- **Actions:** View detail · Cancel (before dispense only)
- **Cancel confirmation:** modal with reason field

### 3.7 Doctor Profile — `/doctor/profile`
- **Fields:** Name · Phone · Specialty (read-only) · Clinic (read-only) · License (read-only)
- **Actions:** Save changes · Change password

---

## 4. Pharmacist Pages

### 4.1 Pharmacist Dashboard — `/pharmacist`
- **Widgets:**
  - Card: Dispensed today
  - Card: Pending verifications
  - Card: Prescriptions this week
  - List: Recent dispenses (patient · time · status)

### 4.2 Dispense Screen — `/pharmacist/dispense`
- **Access:** Pharmacist
- **Layout:** Large centered input area
- **Fields:** Prescription code input (text or QR scan placeholder)
- **Actions:** Verify (primary) · Clear
- **States:**
  - Idle: instructions text
  - Loading: verifying spinner
  - Error: invalid / expired / already dispensed / no consent
- **Note:** On verify success → redirect to Prescription Preview.

### 4.3 Prescription Preview (Pharmacist) — `/pharmacist/dispense/:id`
- **Access:** Pharmacist (with active consent)
- **Layout:** Details panel + dispense action panel
- **Details:** Patient name · Doctor · Issue date · Expiry · Medication items table
- **Actions:** **Dispense** (primary) · Cancel
- **States:**
  - Consent missing → show "Request consent from patient" message (no dispense button)
  - Already dispensed → show dispensed info, disabled button
  - Expired → disabled button + reason

### 4.4 Dispense Result — `/pharmacist/dispense/:id/result`
- **Access:** Pharmacist (post-action)
- **Layout:** Centered result card
- **Variants:**
  - ✅ Success: green icon · "Dispensed successfully" · timestamp · "Next" button
  - ❌ Failure: red icon · reason · "Try again" button
- **Actions:** New dispense (reset) · Back to dashboard

### 4.5 Dispense History — `/pharmacist/history`
- **Access:** Pharmacist
- **Layout:** Filters (date range · status) + table
- **Columns:** Prescription code · Patient · Doctor · Dispensed at · Status
- **Actions:** View detail (read-only)

### 4.6 Pharmacist Profile — `/pharmacist/profile`
- **Fields:** Name · Phone · Pharmacy (read-only) · License (read-only)
- **Actions:** Save changes · Change password

---

## 5. Clinic Admin Pages

### 5.1 Clinic Admin Dashboard — `/clinic-admin`
- **Widgets:** Total doctors · Active doctors · Pending doctors · Recent activity
- **Actions:** View doctors · Add doctor

### 5.2 Doctors List — `/clinic-admin/doctors`
- **Access:** Clinic Admin
- **Layout:** Filters (search · status) + table
- **Columns:** Name · Email · Specialty · License · Status · Actions
- **Actions:** Add new · Edit · Deactivate
- **States:** Empty · Loading · Filtered empty

### 5.3 Add/Edit Doctor — `/clinic-admin/doctors/new` · `/clinic-admin/doctors/:id/edit`
- **Fields:** Name · Email · Phone · Specialty · License Number
- **Actions:** Save · Cancel
- **States:** Validation · Success redirect to list

### 5.4 Clinic Admin Profile — `/clinic-admin/profile`
- **Fields:** Name · Email (read-only) · Phone · Clinic (read-only)
- **Actions:** Save · Change password

---

## 6. Pharmacy Admin Pages

### 6.1 Pharmacy Admin Dashboard — `/pharmacy-admin`
- **Widgets:** Total pharmacists · Active · Pending · Recent activity
- **Actions:** View pharmacists · Add pharmacist

### 6.2 Pharmacists List — `/pharmacy-admin/pharmacists`
- **Columns:** Name · Email · License · Status · Actions
- **Actions:** Add new · Edit · Deactivate

### 6.3 Add/Edit Pharmacist — `/pharmacy-admin/pharmacists/new` · `/:id/edit`
- **Fields:** Name · Email · Phone · License Number
- **Actions:** Save · Cancel

### 6.4 Pharmacy Admin Profile — `/pharmacy-admin/profile`
- **Fields:** Name · Email (read-only) · Phone · Pharmacy (read-only)
- **Actions:** Save · Change password

---

## 7. Platform Admin Pages

### 7.1 Admin Dashboard — `/admin`
- **Widgets:**
  - Card: Total Users (by role breakdown)
  - Card: Total Clinics
  - Card: Total Pharmacies
  - Card: Pending Approvals (highlighted)
  - Card: Prescriptions dispensed this week
  - Card: Recent audit activity (last 10)

### 7.2 Pending Approvals — `/admin/approvals`
- **Access:** Platform Admin
- **Layout:** Tabs (Doctors / Pharmacists) + list
- **List item:** Name · Email · License · Applied date · Actions (Approve / Reject)
- **Approve action:** confirmation modal
- **Reject action:** modal with reason field (required)
- **States:** Empty ("No pending approvals") · Success toast

### 7.3 Clinics Management — `/admin/clinics`
- **Columns:** Name · Address · Phone · License · Status · Actions
- **Actions:** Add · Edit · Deactivate
- **Add/Edit fields:** Name · Address · Phone · License Number

### 7.4 Pharmacies Management — `/admin/pharmacies`
- **Same structure as Clinics** with pharmacy-specific fields

### 7.5 Users Management — `/admin/users`
- **Access:** Platform Admin (no medical content visible)
- **Layout:** Filters (role · status · search) + table
- **Columns:** Name · Email · Role · Status · Created at
- **Actions:** View details · Deactivate (with confirmation)
- **Note:** No access to medical records or prescriptions content.

### 7.6 Audit Logs — `/admin/audit-logs`
- **Layout:** Filters (date range · user · action type · entity) + table
- **Columns:** Timestamp · User · Role · Action · Entity · Entity ID · IP
- **Actions:** View detail (metadata only, no medical content)
- **Export:** CSV download button
- **States:** Empty · Loading · Filtered empty

### 7.7 Admin Profile — `/admin/profile`
- **Fields:** Name · Email (read-only) · Password change
- **Actions:** Save

---

## 8. Shared / Utility Pages

### 8.1 Unauthorized (403) — `/403`
- **Message:** "You don't have permission to view this page."
- **Action:** Back to dashboard

### 8.2 Not Found (404) — `/404`
- **Message:** "Page not found."
- **Action:** Back to dashboard

### 8.3 Pending Approval Screen — `/pending`
- **Access:** Doctor/Pharmacist after registration
- **Message:** "Your account is under review. You'll get access once approved."
- **Action:** Logout

### 8.4 Change Password — `/change-password`
- **Fields:** Current Password · New Password · Confirm
- **Actions:** Save · Cancel
- **States:** Validation · Success toast

---

## 9. Prototype Deliverables Checklist

For each page in Figma, include:
- [ ] Desktop view (1440px)
- [ ] Tablet view (768px)
- [ ] Mobile view (375px)
- [ ] Loading state
- [ ] Empty state
- [ ] Error state (where applicable)
- [ ] Success state (for form submissions)
- [ ] Hover / focus states for interactive elements

---

## 10. Notes

- This is an initial draft — visual style (colors, typography, spacing) will be defined in the Figma design system.
- Wireframes come first (low-fidelity), then high-fidelity mockups.
- All forms must use inline validation and accessible labels.
- All destructive actions require confirmation.
- QR code display must be large enough on mobile for scanning.

> Draft — subject to refinement.
