# HOROOMED™ — Unified Digital Health Platform

**Integrated Electronic Medical Record & Health Information Platform**

HOROOMED™ is an electronic medical record and health information system for Ethiopian
health facilities, by HOROO INNOVATION PLC. It follows a patient from the card room through
triage and the outpatient department (OPD) to the laboratory, imaging, pharmacy and the
delivery ward. At the end of each month it produces the Ministry of Health's HMIS figures.

This repository describes how the system is built and how it protects patient data. It holds
documents only. The source code is kept in a private repository.

| Document | What it covers |
|---|---|
| [Architecture](docs/architecture.md) | The parts of the system and how they fit together |
| [Patient flow](docs/patient-flow.md) | The journey of a patient and the records made at each step |
| [Data protection](docs/data-protection.md) | How patient data is kept confidential, intact and traceable |
| [Standards and integration](docs/standards.md) | The Ethiopian calendar, HMIS/DHIS2, payers and fiscal registration |

## At a glance

- **Card room:** registration with a medical record number (MRN) that is never reused, and
  names written as name, father's name and grandfather's name. Patients who know only their
  age can be registered, and duplicates are checked before a record is created.
- **Payers:** cash, community-based health insurance (CBHI), social health insurance (SHI),
  credit organizations, and exempt services. An exemption needs a reason and an authorized
  user.
- **Clinical care:** triage and vital signs, OPD consultations, diagnoses, orders, laboratory
  results verified by a second person, imaging reports, dispensing, and the delivery register.
- **Reporting:** dates are shown in both the Ethiopian and Gregorian calendars. Monthly HMIS
  reports run by Ethiopian month.
- **Business core:** cashier and receipts, MoR fiscal registration, pharmacy stock with
  batches and expiry, purchasing, finance and staff.

Copyright © HOROO INNOVATION PLC. HOROOMED is a trademark of HOROO INNOVATION PLC.
