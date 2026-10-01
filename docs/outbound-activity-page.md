# Outbound activity page

Added after the outbound source-path fix (32bbb8b). Uses existing FactOutbound, DimStaff, DimRoutingDate and _OutboundMeasures; no changes to their definitions. Existing pages, including Outbound Validation, are retained.

## Reading the page

- Date, team and staff slicers filter the page. The date slicer is not synced with inbound pages.
- Cards show attempts, staff with activity, and average attempts per weekday. Counts use exact display units.
- Daily trend shows daily attempts, without a trailing-average claim.
- Team bar chart supports drilling from Team to StaffName. Volume is not a productivity score.
- Monthly chart restricts to IsCompleteMonth=true (May–August in this export). Date selections and cross-filtering still apply; select entire months for full-month comparisons.
- Weekday/hour matrix shows attempt totals in Melbourne time, not exposure-adjusted rates. Weekdays sort using the existing WeekdayNumber model setting.

## Coverage and validation

Current calendar and complete-day/month flags are based on the inbound export. This is suitable only while the inbound and outbound exports share the same coverage window. Update the calendar and coverage rules when future exports differ. Completeness between observed boundary dates is assumed, not proven by the logs.

Expected unfiltered checks from the previously validated model: 6,046 attempts; 18 staff; 57.4 average weekday attempts. Team totals: Membership 5,275; HRSC 680; Events 91.

Report definitions are statically validated. Power BI Desktop rendering and DAX execution must be checked after opening the project. Refresh requires data/source/Export_Outbound.xlsx on the local machine and the correct ProjectRoot parameter.

## Desktop check

1. Save and close Power BI before pulling.
2. Open powerbi/AHRI-Call-Dashboard.pbip and select Outbound activity.
3. Check that all visuals render and card totals match Outbound Validation.
4. Select each team, then a staff member and a date range; check all visuals respond.
5. Test the team chart drill controls, month ordering and weekday ordering.
6. Clear selections and save.
