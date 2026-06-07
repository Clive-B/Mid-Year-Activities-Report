# NCA Mid-Year Activity Report Dashboard Handoff

## Current State

- Project folder: `C:\Users\codro\Desktop\Activities For Mid-Year Review`
- GitHub repository: `https://github.com/Clive-B/Mid-Year-Activities-Report.git`
- Branch: `main`
- Current dashboard file: `Mid-Year Activity Report Dashboard.html`
- Current generated JSON sample/live data file: `nca-mid-year-dashboard-data.json`
- Current Excel workbook sample: `NCA Mid-Year Activity Report - 2026.xlsx`
- Current logo asset: `nca-logo.png`
- Current watermark asset: `nca-building-watermark.png`
- Original small building image: `images.jpg`

The dashboard is a browser-based HTML app. It reads data from uploaded Excel/CSV files and can also fetch online JSON from a Power Automate HTTP endpoint.

## Backup Practice

Before each major change, create a copy of the current working dashboard. Recent backups include:

- `Mid-Year Activity Report Dashboard-working-before-leave-holiday-calculation.html`
- `Mid-Year Activity Report Dashboard-working-before-color-print.html`
- `index-working-before-android-logo-sharp-watermark.html`
- `index-working-before-mobile-friendly.html`
- `index-working-before-unit-head-fields.html`
- `index-working-before-narrative-timeline.html`
- `index-working-before-data-quality-monitor.html`
- `index-working-before-division-spotlight.html`
- `index-working-before-presentation-mode.html`
- `index-working-before-auto-brief.html`
- `index-working-live-fetch-version.html`

Continue this pattern before future changes.

## Project Timeline

1. Initial repository setup and push to GitHub.
2. Built the first NCA Mid-Year Activity Report dashboard using the Excel workbook in the folder.
3. Added NCA branding, NCA color theme, logo, and building watermark.
4. Added Excel upload support for `.xlsx`, `.xls`, and `.csv`.
5. Added dashboard cards for total submissions, divisions, activities, foreign travels, and leave records.
6. Added charts for submissions by division, leave by type, foreign travel by destination, and activity status/count.
7. Added detailed submission records.
8. Added chart downloads and chart type selectors.
9. Fixed chart rendering error caused by an undefined `textColor` variable.
10. Added executive summary.
11. Added smart insight cards.
12. Added local rule-based `Ask the Dashboard`.
13. Added presentation mode.
14. Added data quality monitor.
15. Added official division context and missing-division checks.
16. Added division spotlight reports.
17. Fixed leave day totals in division spotlight by reading numbered leave-duration fields.
18. Added narrative timeline.
19. Updated footer text to `Generated dashboard template for NCA Mid-Year Activity Report workflow.`
20. Added support for new JSON columns, including `Are you a unit head`.
21. Added unit-head charts.
22. Made the page phone friendly for iOS and Android.
23. Fixed mobile logo by embedding the logo in the HTML.
24. Added a higher-resolution building watermark asset.
25. Renamed the active dashboard from `index.html` to `Mid-Year Activity Report Dashboard.html`.
26. Added print CSS to preserve dashboard colors, though browser/printer settings may still force grayscale if `Background graphics` is off or the printer is in black-and-white mode.

## Power Automate Workflows

Two Power Automate flows were discussed and configured:

### 1. Hourly JSON Generator

Purpose: read the Microsoft Forms-connected Excel table every hour and update/create `nca-mid-year-dashboard-data.json`.

Main logic:

- Trigger: Recurrence, every hour.
- Excel Online for Business: List rows present in a table.
- Compose actions: format rows and metadata into JSON.
- OneDrive/SharePoint: Update file for `nca-mid-year-dashboard-data.json`.

Important note: the Excel response range must be formatted as an Excel Table because Power Automate's Excel connector reads table rows.

### 2. Serve NCA Dashboard JSON

Purpose: safely serve the JSON file through a Power Automate HTTP endpoint.

Main logic:

- Trigger: When an HTTP request is received.
- OneDrive for Business: Get file content using path.
- Response: status `200`, header `Content-Type: application/json`, body from the file content.

Important note: the HTTP trigger expects POST, not GET. The dashboard fetch button was updated to send POST.

## Current Dashboard Features

- Local Excel/CSV upload.
- Online JSON fetch through Power Automate endpoint.
- Endpoint button for setting/changing the online fetch URL.
- Print / Save as PDF button.
- Reset button.
- Presentation mode.
- Download button for each chart.
- Chart type selector for each chart.
- Search and filters for division, designation, and free text.
- Executive summary.
- Auto executive brief.
- Smart insight cards.
- Rule-based Ask the Dashboard.
- Data Quality Monitor.
- Division Spotlight.
- Narrative Timeline.
- Unit-head charts.
- Detailed Submission Records, including Brief Description.

## Current Official Divisions

The dashboard recognizes these official NCA divisions:

1. RIPS
2. ENGINEERING
3. FINANCE
4. HUMAN RESOURCE
5. AUDIT
6. ADMINISTRATION
7. LEGAL
8. CONSUMER AFFAIRS
9. CYBERSECURITY
10. PROCUREMENT AND PROTOCOL
11. INFORMATION TECHNOLOGY

The Data Quality Monitor should flag official divisions with no visible submissions.

## Current Known Issues and Notes

- Print preview may still show grayscale if the browser/printer setting uses black-and-white output.
- In Chrome/Edge print preview, `Background graphics` must be checked for full color backgrounds and watermark effects.
- The Canon printer profile shown by the user appeared to force grayscale in preview. Test with `Save as PDF` and color mode enabled.
- `nca-mid-year-dashboard-data.json` is currently untracked and should normally remain uncommitted unless the user asks to publish a sample JSON.
- The dashboard currently does not recalculate leave days by excluding weekends or Ghana public holidays. It reads submitted leave-day values from the data.

## Next Planned Enhancement

Add working-day leave calculation:

- Use leave start date and leave end date.
- Exclude Saturdays and Sundays.
- Exclude Ghana public holidays.
- Compare calculated working days against the submitted number of leave days.
- Update charts, Division Spotlight, and Data Quality Monitor to use/validate the recalculated leave duration.

Primary holiday source should be the official Ministry of the Interior Ghana holiday list:

- `https://www.mint.gov.gh/statutory-public-holidays/`

The Data Quality Monitor should then flag:

- Leave selected but start/end dates missing.
- End date before start date.
- Submitted leave days missing.
- Submitted leave days different from calculated working days.
- Leave date ranges that include weekends/public holidays but appear to have counted them.
- Cases where the dashboard cannot calculate because relevant date columns are missing.

## Validation Checklist

Before committing dashboard edits:

1. Create a backup copy of the active dashboard.
2. Run a JavaScript syntax check by extracting inline script and using `node --check`.
3. Check `git status --short`.
4. Do not commit `nca-mid-year-dashboard-data.json` unless requested.
5. Commit the active dashboard, backup, and any new required assets.
6. Push to `origin main`.

## Git History Landmarks

- `4b79bf7` Add mid-year activity report files
- `cc931e3` Add interactive NCA activity dashboard
- `9d91550` Add dashboard management charts
- `bbda4bb` Add chart downloads and type options
- `8214b32` Add online Excel fetch button
- `71ea083` Use POST for online Excel fetch
- `a4b6e05` Add brief description chart and table column
- `ecf2629` Add auto executive brief insights
- `f9bbb5f` Add smart insight cards
- `0a07500` Add local ask the dashboard feature
- `ffea5e7` Add executive presentation mode
- `2178c3b` Add data quality monitor
- `47bfb4e` Track missing official division submissions
- `92f14f1` Add division spotlight reports
- `c39cd2b` Add narrative activity timeline
- `059c4d5` Add unit head dashboard views
- `c57c3d5` Make dashboard phone friendly
- `cef2f8d` Fix Android logo and sharpen watermark
- `8cec2b0` Preserve dashboard colors when printing

