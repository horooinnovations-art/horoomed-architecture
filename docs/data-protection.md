# Data protection

Health data is sensitive personal data under Ethiopia's Personal Data Protection Proclamation
No. 1321/2024. HOROOMED™ is designed around four rules.

## 1. Personal details are encrypted at rest

| Field | Stored as |
|---|---|
| Phone, national or kebele ID, CBHI/SHI membership number | Encrypted, with a keyed blind index (HMAC) for exact search |
| House number, marital status, education, religion, occupation, residence type | Encrypted together |
| Emergency contact (name, phone, relationship) | Encrypted together |
| Names, sex, date of birth, region, zone, woreda, kebele | Plain. The card room must find patients by part of a name, and monthly reports count by sex, age and area |

The blind indexes let the card room find a patient by phone, ID or membership number without
storing those values in a form that can be read. Phone numbers are matched on their last nine
digits, so `0911 …`, `+251 911 …` and `911…` find the same patient.

## 2. Access follows the job

Each clinical action has its own permission, and each role gets only the permissions its job
needs.

- The cashier sees what a visit owes and the patient's name and MRN. The cashier never sees
  the clinical record, diagnoses or results.
- Clinical notes and results are open only to clinical roles.
- The HMIS officer works with counts, not individual records.
- Giving a service free is its own permission, separate from taking payment.

## 3. Every view is recorded

Every opening of a patient's record writes an audit entry: who, which patient, what was
opened, and when. This covers the record, the edit form and the printed card. Creating and
changing records is audited too. Audit entries name the record but never copy the personal
details into the log.

## 4. Signed records change only by amendment

A verified laboratory result, a signed consultation or a delivery record is never edited in
place. A correction is added as an amendment, which keeps the old value, the person who
corrected it and the reason.

## Other safeguards

- Sign-in with two-factor authentication for administrators, account lockout, and a
  content security policy that forbids inline scripts.
- Uploaded images and PDFs are type-checked on the server and stored outside the public web
  root.
- Medical record numbers and visit numbers are allocated under a database lock and never
  reused.
- Duplicate patients are checked by phone, ID, membership number, and name with birth year
  before a new record is made.
- Encrypted backups.
- Test data is always invented. Real patient data is never used in testing or
  demonstrations.
