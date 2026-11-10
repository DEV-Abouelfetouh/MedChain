# Test Status — MedChain (Draft v0.1)

## Current Status

| Item | Status | Notes |
|------|--------|-------|
| Prototype (Figma) | ✅ Done | All main screens drafted |
| Test Cases (documented) | ✅ Done | See test cases section below |
| Testing Execution | 🔄 In Progress | Re-running after updates |

## Prototype Coverage

| # | Screen | Prototype | Status |
|---|--------|:---------:|--------|
| 1 | Login / Register | ✅ | Done |
| 2 | Patient Dashboard | ✅ | Done |
| 3 | Doctor Dashboard | ✅ | Done |
| 4 | Pharmacist Dashboard | ✅ | Done |
| 5 | Admin Dashboard | ✅ | Done |
| 6 | Prescription + QR | ✅ | Done |
| 7 | Dispense Screen | ✅ | Done |
| 8 | Consent Management | ✅ | Done |
| 9 | Audit Log | ✅ | Done |
| 10 | Approvals (Admin) | ✅ | Done |

## Test Cases (High Level)

| ID | Area | Scenario | Expected Result | Status |
|----|------|----------|-----------------|--------|
| TC-01 | Auth | Login with valid credentials | Redirect to role dashboard | ✅ Passed |
| TC-02 | Auth | Login with invalid credentials | Error message shown | ✅ Passed |
| TC-03 | Auth | Register as patient | Auto-redirect to dashboard | ✅ Passed |
| TC-04 | Auth | Register as doctor | "Pending approval" screen | ✅ Passed |
| TC-05 | Admin | Approve doctor account | Account activated | ✅ Passed |
| TC-06 | Admin | Reject doctor account | Account rejected with reason | ✅ Passed |
| TC-07 | Records | Doctor creates record | Record visible to patient | ✅ Passed |
| TC-08 | Records | Doctor opens patient without consent | Access blocked | ✅ Passed |
| TC-09 | Prescription | Doctor issues prescription | Unique code generated | ✅ Passed |
| TC-10 | Prescription | Pharmacist dispenses with consent | Status → dispensed | ✅ Passed |
| TC-11 | Prescription | Dispense without consent | Blocked with message | 🔄 Re-testing |
| TC-12 | Prescription | Double dispense attempt | Blocked with message | 🔄 Re-testing |
| TC-13 | Prescription | Dispense expired prescription | Blocked with message | ⬜ Pending |
| TC-14 | Consent | Patient grants consent | Doctor gains access | ✅ Passed |
| TC-15 | Consent | Patient revokes consent | Access removed immediately | 🔄 Re-testing |
| TC-16 | Audit | Critical action logged | Entry visible in audit log | ✅ Passed |
| TC-17 | Access | Patient accesses another patient's data | 403 blocked | ✅ Passed |
| TC-18 | Admin | Admin opens audit log | No medical content visible | ⬜ Pending |

## Summary

| Status | Count |
|--------|-------|
| ✅ Passed | 13 |
| 🔄 In Progress / Re-testing | 3 |
| ⬜ Pending | 2 |
| ❌ Failed | 0 |
| **Total** | **18** |

## Next Steps

- [ ] Re-run TC-11, TC-12, TC-15 after fixes
- [ ] Execute TC-13 and TC-18
- [ ] Add test cases for edge cases (expired consent, invalid QR)
- [ ] Update this document after each test cycle

## Notes

- Prototype is complete and available in Figma.
- Test cases are documented and being re-executed against the latest build.
- This file will be updated with results after each testing round.

> Draft status — updated regularly during development.
