# AHRI Call Dashboard

This version uses only Ehsan's Direct Routing Excel export. There are no legacy CSV dependencies. The Power BI project contains four pages: Demand and timing, Routing and queue destinations, Technical outcomes, and Duration and data confidence.

The original source is included at data/source/DirectRouting_Ehsan_2026-09-01.xlsx. Set ProjectRoot to the extracted project folder containing data and powerbi. Metric explanations are provided in the accompanying chat and as measure descriptions in the model.

Only inbound records are represented. Observed coverage is 6 April through 1 September 2026, with incomplete boundary dates. The file does not establish staff answer rate, queue abandonment or customer resolution. Interpret shared IDs as related-record groups.

File structure and source totals were checked. Power BI Desktop refresh, DAX execution and actual visual rendering must still be verified in Windows. No commit or push was performed.
