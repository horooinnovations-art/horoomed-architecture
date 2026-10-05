# Patient flow

```mermaid
flowchart TD
    A["Card room: find the patient by MRN, phone, ID, membership number or name, or register a new one"] --> B["Open today's visit: new or repeat; OPD, emergency or delivery; payer"]
    B --> C{"Card fee"}
    C -- "cash" --> D["Cashier: paid as a sale, with a receipt and fiscal registration"]
    C -- "CBHI / SHI / credit" --> E["Covered: goes on the payer's account and into its monthly claim"]
    C -- "exempt" --> F["Free: needs a reason and an authorized user, and is audited"]
    C -- "free repeat within N days" --> G
    D & E & F --> G["Triage: vital signs and urgency"]
    G --> H["OPD: complaint, history, examination, diagnosis"]
    H --> I["Orders: lab, imaging, prescription, procedure, referral, admission to delivery"]
    I --> J["Cashier: each order is a bill line, settled before the service"]
    J --> K["Laboratory: sample, result, verification by a second user"]
    J --> L["Imaging: performed, report, image or PDF"]
    J --> M["Pharmacy: dispensed from stock, earliest expiry first"]
    J --> N["Delivery: admission, labour, delivery, newborn, discharge"]
    K & L --> H
    H & M & N --> O["Visit closed: counted in the month's HMIS report"]
```

## The payment rule

A service is not given until it is paid for or covered by the patient's payer. The one
exception is an emergency. A named, authorized user can mark it, and the mark is audited.

## Records made at each step

| Step | Record | Who |
|---|---|---|
| Registration | Patient: MRN, names, sex, date of birth or age, address, contact, payer | Card room |
| Visit | Visit: number, type, department, payer, arrival time, status | Card room |
| Payment | Charge settled: sale and receipt, payer cover, or exemption with reason | Cashier, or an authorizer for exemptions |
| Triage | Vital signs and urgency | Triage nurse |
| Consultation | Notes, diagnoses (new or repeat, primary or secondary), orders | Doctor |
| Laboratory | Sample, results, verification | Lab technician, then lab verifier |
| Imaging | Report and images | Radiographer |
| Pharmacy | Dispensing against the prescription | Pharmacist |
| Delivery | Labour and delivery register, newborn | Midwife |

## Dates

Dates are stored in the Gregorian calendar and shown in both the Ethiopian and Gregorian
calendars. A birth date may be entered in either calendar, or estimated from an age in years,
months and days.
