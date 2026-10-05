# Standards and integration

## Ethiopian calendar

Dates convert between the Ethiopian and Gregorian calendars through the Julian day number,
so leap years come out right. Meskerem 1 falls on 11 September, or on 12 September in the
year after an Ethiopian leap year, and Pagume has 6 days in an Ethiopian leap year. The
system stores Gregorian dates, shows both calendars, and accepts Ethiopian dates written
`dd/mm/yyyy`.

## HMIS and DHIS2

The Ministry of Health's monthly HMIS reporting runs on DHIS2. HOROOMED™ will produce:

- OPD visits, new and repeat, by sex and age group;
- the top diseases, by sex and age group;
- laboratory tests done;
- deliveries by mode, with births and outcomes;
- visits by payer: CBHI, SHI and credit.

Reports run by Ethiopian month. The age groups and data elements are taken from the
facility's current HMIS forms and kept in a single configuration file, so a revised form
needs a configuration change, not a code change. They are never invented. Output is a
printable report in the HMIS layout and a spreadsheet export. Sending the figures straight to
DHIS2 through its API is a later step.

## Diagnoses

Diagnoses come from the Ethiopian disease list used by HMIS, which is based on ICD. The list
is loaded from the file the Ministry issues.

## Payers

| Payer | How charges are settled |
|---|---|
| Cash | Paid at the cashier as a sale, with a receipt |
| CBHI | Covered on presentation of a membership number, and claimed monthly |
| SHI | Covered on presentation of a membership number, and claimed monthly |
| Credit organization | Covered on the organization's account and invoiced as a credit sale |
| Exempt | Free with a reason and an authorized user, audited |

## Fiscal registration

Cash sales, including card fees and paid orders, are registered with the Ministry of
Revenues' e-invoicing system through the same fiscal service used for every other sale.
Offline operation retries automatically.

## Identifiers

- **MRN:** a per-facility prefix followed by a zero-padded number, never reused. It is printed
  on the patient card as a Code 128 barcode, which any USB scanner reads as typed text.
- **Visit number:** year and month, followed by a running number.
