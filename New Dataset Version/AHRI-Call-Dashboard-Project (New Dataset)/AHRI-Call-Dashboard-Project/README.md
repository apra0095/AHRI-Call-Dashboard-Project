# AHRI Call Dashboard

A Power BI dashboard that gives the Australian HR Institute (AHRI) Member Engagement Team visibility of inbound phone activity from Microsoft Teams telephony. Built as part of the AHRI x Monash Call Stats Dashboard project.

## Background 

AHRI members contact the institute by email or online enquiry form and by phone through Microsoft Teams. AHRI currently has no reporting on phone data beyond raw exports that IT can pull manually. This project turns one of those exports into a clear, visual dashboard.

This version uses only Ehsan's Direct Routing Excel export. There are no legacy CSV dependencies. The Power BI project contains three pages: Demand and timing, Routing and queue destinations, and Outcomes and Duration.

Only inbound records are represented. Observed coverage is 6 April through 1 September 2026, with incomplete boundary dates. The file does not establish staff answer rate, queue abandonment or customer resolution. Interpret shared IDs as related-record groups.

File structure and source totals were checked. Power BI Desktop refresh, DAX execution and actual visual rendering must still be verified in Windows. No commit or push was performed.

## Scope

**In scope**

-   Inbound call activity only
-   What calls came in, when, and where they were routed

**Out of scope**

-   Real-time or live reporting
-   Outbound call data

## Data limitations

The export does not establish:

-   Staff answer rate
-   Queue abandonment
-   Customer resolution

Microsoft Teams call data expires after roughly 30 days and can only be extracted by AHRI's IT team, so any long-term version of this dashboard needs a storage layer that ingests the raw data regularly.

## Dashboard pages

| Page | What it shows |
|----|----|
| Demand and timing | Call volume over time and patterns by day and time |
| Routing and queue destinations | How calls were routed and where they ended up |
| Outcomes and Duration | Call outcomes and call duration |
