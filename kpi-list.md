# AHRI Call Dashboard

## Lists of KPI & Business Questions

## Data summary

|   | Auto Attendant file | Call Queue file |
|------------------------|------------------------|------------------------|
| Columns | `Last Activity Date`, `Total Call Count`, `Resource Account` | `Last Activity Date`, `Total Call Count`, `Resource Account` |
| Date range | 2026-08-04 to 2026-08-31 (daily) | 2026-08-04 to 2026-08-31 (daily) |
| Distinct resource accounts | 4 (mainivr, membershipenquiries, eventnetwork, educationenquiries) | 15 |

**Call Queue resource accounts (primary / overflow pairs):**

| Base queue      | Primary account        | Overflow account                |
|-----------------|------------------------|---------------------------------|
| Reception       | `cq-reception-v2`      | `cq-reception-overflow-v2`      |
| Career support  | `cq-careersupport-v2`  | `cq-careersupport-overflow-v2`  |
| Corporate sales | `cq-corporatesales-v2` | `cq-corporatesales-overflow-v2` |
| Membership      | `cq-membership-v2`     | `cq-membership-overflow-v2`     |
| Org members     | `cq-orgmembers-v2`     | `cq-orgmembers-overflow-v2`     |
| Student support | `cq-studentsupport-v2` | `cq-studentsupport-overflow-v2` |
| CPD events      | *(none found)*         | `cq-cpdevents-overflow-v2`      |
| CDP events      | `cq-cdpevents-v2`      | *(no overflow)*                 |
| Group training  | `cq-grouptraining-v2`  | *(no overflow)*                 |

## 1. Call Volume & Demand

**Question:** What is the volume of inbound calls over time, and what is the overall trend?

| KPI | Definition | Fields used |
|------------------------|------------------------|------------------------|
| Total Call Volume | Sum of CallCount over the selected period | `CallCount` (AutoAttendantDaily + CallQueueDaily) |
| Daily Call Trend | CallCount plotted by date | `CallCount`, `Date` |
| Monthly Call Volume | CallCount aggregated by month, month-over-month | `CallCount`, `Month`, `MonthNumber` |

## 2. Weekday / Demand Pattern

**Question:** Which days of the week see the highest and lowest call demand?

| KPI | Definition | Fields used |
|------------------------|------------------------|------------------------|
| Calls by Weekday | Sum of CallCount grouped by day of week | `CallCount`, `Weekday`, `WeekdayNumber` |
| Peak Day Identification | Day with the highest CallCount in the selected period | `CallCount`, `Weekday` |

## 3. Auto Attendant / Routing Mix

**Question:** How are calls distributed and routed across Auto Attendants?

| KPI | Definition | Fields used |
|------------------------|------------------------|------------------------|
| Calls by Auto Attendant | Sum of CallCount grouped by Auto Attendant | `CallCount`, `AutoAttendant` |
| Auto Attendant Share (%) | Percentage share of each Auto Attendant vs. total | `CallCount`, `AutoAttendant` |
| Calls by Resource Account | Sum of CallCount grouped by resource account | `CallCount`, `ResourceAccount` |

## 4. Queue Activity

**Question:** Which queues see the most activity, and how does that change over time?

| KPI | Definition | Fields used |
|------------------------|------------------------|------------------------|
| Calls by Queue | Sum of CallCount grouped by Call Queue | `CallCount`, `CallQueue` |
| Queue Volume Trend | CallCount per queue over time | `CallCount`, `Date`, `CallQueue` |

## 5. Primary vs Overflow

**Question:** What proportion of calls are handled as primary vs. overflow, and which queues overflow most often?

| KPI | Definition | Fields used |
|------------------------|------------------------|------------------------|
| Primary vs Overflow Split | Sum of CallCount grouped by derived IsOverflow flag | `CallCount`, `ResourceAccount` |
| Overflow Rate by Queue | \% of each base queue's calls that went to overflow | `CallCount`, `ResourceAccount` |

-   Answer Rate
-   Abandon Rate
-   Average Wait Time
-   Average Talk Time
-   Hour-of-Day Peaks
-   Individual Call Journey
