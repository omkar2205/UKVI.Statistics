# UKVI Student Visa Statistics

Fresh rebuild of the UKVI study visa dashboard using Supabase as the backend.

## Architecture

- Frontend: static single-page site in `index.html`
- Backend: Supabase project `fmharbqedtutphukhskz`
- Public data source: read-only Supabase Data API with Row Level Security
- Source workbook: `UKVI Data 2020-2026 Q2.xlsx`
- Source workbook storage: private Supabase Storage bucket `ukvi-source-files`, path `current/UKVI Data 2020-2026 Q2.xlsx`

## Database objects

- `public.ukvi_applications`
- `public.ukvi_outcomes`
- `public.ukvi_metadata`
- `public.ukvi_dashboard_rows` view

The public site can only read the dashboard data. Import/write operations are not available to anonymous visitors.

## Dashboard calculations

- Grant Rate = Issued / (Issued + Refused)
- Refusal Rate = Refused / (Issued + Refused)

## Source

UK Home Office immigration system statistics data tables:
https://www.gov.uk/government/statistical-data-sets/immigration-system-statistics-data-table
