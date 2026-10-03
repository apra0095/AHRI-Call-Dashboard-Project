# AHRI Call Dashboard

A Power BI dashboard that gives the Australian HR Institute (AHRI) Member Engagement Team visibility of inbound and outbound phone activity from Microsoft Teams telephony. Built as part of the AHRI x Monash Call Stats Dashboard project.

## Background

AHRI members contact the institute by email or online enquiry form and by phone through Microsoft Teams. Staff also make outbound calls to members, for example to follow up overdue fees. AHRI currently has no reporting on phone data beyond raw exports that IT can pull manually. This project turns one of those exports into a clear, visual dashboard.

This version uses only Ehsan's Direct Routing and Outbound Excel exports. There are no legacy CSV dependencies. The Power BI project contains five pages: Demand and timing, Routing and queue destinations, Outcomes and Duration, Outbound activity, and Outbound outcome.

Observed coverage is 6 April through 1 September 2026, with incomplete boundary dates. The file does not establish staff answer rate, queue abandonment or customer resolution. Interpret shared IDs as related-record groups.

File structure and source totals were checked. Power BI Desktop refresh, DAX execution and actual visual rendering must still be verified in Windows. No commit or push was performed.

## Scope

**In scope** - Inbound calls: when calls arrive, how they are routed and how they end at the system level - Outbound calls: who makes calls, when, how they end at the system level and how long connected calls last - Current-state visibility only

**Out of scope**

-   Real-time or live reporting
-   Any measure of individual staff performance. The outbound pages show call activity, not performance.

## Data

| Source | File | Used for | Coverage |
|----|----|----|----|
| Inbound | `data/source/DirectRouting_Ehsan_2026-09-01.xlsx` | Inbound pages | 6 April to 1 September 2026 |
| Outbound | `data/source/Export_Outbound.xlsx` | Outbound pages | 6 April to 1 September 2026 |

The outbound export contains both call directions. Only rows where Call Direction is Outbound are loaded into FactOutbound. Inbound reporting continues to use the original inbound file.

## Data limitations

The export does not establish:

-   Staff answer rate
-   Queue abandonment
-   Customer resolution

Microsoft Teams call data expires after roughly 30 days and can only be extracted by AHRI's IT team, so any long-term version of this dashboard needs a storage layer that ingests the raw data regularly.

## Dashboard pages

| Page | Question it answers | What it shows |
|----|----|----|
| Inbound Call Overview | How many calls arrive, and when? | Inbound demand over time and patterns by day and time |
| Routing and queue destinations | Where do callers go? | IVR options, queues reached and overflow |
| Outcome and Duration | How do inbound calls end, and how long do they take? | Outcomes, and call duration |
| Outbound activity | Who is making outbound calls, and when does activity happen? | Total attempts, staff with activity, average attempts per weekday, daily trend, attempts by team with drill-down to staff, monthly weekday average |
| Outbound outcome and duration | How do outbound calls end, and how long do they last? | Successful and unsuccessful attempts, success rate, unsuccessful attempts by reason, duration of successful attempts, average call length |

## Data model

| Table | Purpose |
|----|----|
| `DimRoutingDate` | Date dimension shared by inbound and outbound (date, complete day/month flags, weekday, year-month) |
| `DimQualityCheck` | Data quality check labels (inbound) |
| `DimStaff` | Staff-to-team mapping (outbound) |
| `FactDirectRouting` | Inbound direct routing records |
| `FactRoutingGroup` | Inbound related-record groups |
| `FactOutbound` | Outbound attempts, one row per attempt |
| `_RoutingMeasures` | DAX measures for the inbound pages |
| `_OutboundMeasures` | DAX measures for the outbound pages |
