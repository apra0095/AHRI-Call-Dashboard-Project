# Open this version

1. Close Power BI Desktop. Extract the entire ZIP into a separate folder; do not open the PBIP directly inside the ZIP.
2. Open powerbi/AHRI-Call-Dashboard.pbip in the extracted folder.
3. In Transform data > Manage Parameters, set ProjectRoot to the folder that directly contains data and powerbi. Use your actual Windows extraction path without surrounding quotation marks.
4. Choose Close & Apply, then Refresh. Only the included DirectRouting_Ehsan_2026-09-01.xlsx file is needed.
5. With no date filter, confirm 3,986 Main IVR entries, 6,361 linked groups, 1,262 queue groups, 337 overflow groups, 786 unsuccessful records and a 7.97% unsuccessful-record rate. Successful Main IVR entry duration has a median of 70 seconds and 90th percentile of 88 seconds.
6. Inspect all four pages. This environment cannot run Power BI Desktop, so send any complete error message if opening or refreshing fails.

This replacement project removes the legacy tables and pages. Do not overlay it onto the previous powerbi folder: leftover TMDL or page files could be loaded. To use it in your existing Git repository after verification, back up the old project, retain .git, and replace the whole powerbi folder with this version. Copy the included new Excel source into data/source. Set ProjectRoot to the repository folder and save. The old CSVs may be retained as historical files outside the model; they are not read by this version. Review and commit on your existing main branch. This session has not pushed changes.
