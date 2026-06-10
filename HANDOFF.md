# NCA Mid-Year Activity Report Dashboard Handoff

Last updated: 2026-06-09

## Current State

- Project folder: `C:\Users\codro\Desktop\Activities For Mid-Year Review`
- GitHub repository: `https://github.com/Clive-B/Mid-Year-Activities-Report.git`
- Branch: `main`
- Active dashboard file: `Mid-Year Activity Report Dashboard.html`
- Active dashboard size: about `16.8 MB`
- Excel workbook sample: `NCA Mid-Year Activity Report - 2026.xlsx`
- Generated/live JSON file: `nca-mid-year-dashboard-data.json`
- Current logo asset file: `nca-logo.png`
- Current building watermark asset file: `nca-building-watermark.png`
- Original small building image: `images.jpg`

The dashboard is a standalone browser-based HTML app for the NCA Mid-Year Activity Report workflow. It can read uploaded Excel/CSV files, or fetch JSON generated from a Microsoft Forms-connected online Excel workbook through Power Automate.

Important: the current active HTML embeds both the logo and the NCA building watermark as Base64 images. This means the active dashboard can be moved to another laptop as a single HTML file and the logo/building watermark will still show.

## Standing Working Doctrine

The user has asked that NYAME MIND OMEGA and VPF governance preferences apply across projects.

Practical effect for this project:

- Create backups before major changes.
- Check live files before acting.
- Validate before release.
- Keep an audit trail through commits, handoff notes, and concise summaries.
- Avoid overclaiming; call out uncertainty, browser limitations, and external workflow dependencies.
- Preserve human approval before major, irreversible, or externally committed changes.
- Prefer African-first, dignity-preserving, sovereignty-aware, and institutionally governed design choices where relevant.

Durable cross-project memory notes were created outside this repo:

- `C:\Users\codro\.codex\memories\extensions\ad_hoc\notes\2026-06-08-nyame-mind-governance-layer.md`
- `C:\Users\codro\.codex\memories\extensions\ad_hoc\notes\2026-06-08-vpf-cross-project-governance-layer.md`

## Backup Practice

Before each major dashboard change, create a working backup of the active HTML. Existing backups include:

- `Mid-Year Activity Report Dashboard-working-before-embedded-building-watermark.html`
- `Mid-Year Activity Report Dashboard-working-before-leave-working-days-upgrade.html`
- `Mid-Year Activity Report Dashboard-working-before-leave-holiday-calculation.html`
- `Mid-Year Activity Report Dashboard-working-before-color-print.html`
- `index-working-before-android-logo-sharp-watermark.html`
- `index-working-before-watermark-logo-fix.html`
- `index-working-before-watermark-visibility.html`
- `index-working-before-phone-friendly.html`
- `index-working-before-mobile-friendly.html`
- `index-working-before-unit-head-fields.html`
- `index-working-before-narrative-timeline.html`
- `index-working-before-division-spotlight.html`
- `index-working-before-data-quality-monitor.html`
- `index-working-before-presentation-mode.html`
- `index-working-before-auto-brief.html`
- `index-working-before-chart-options.html`
- `index-working-live-fetch-version.html`

Continue this naming pattern before future changes.

## Full Project Timeline

1. The user first asked to push the local folder contents to the GitHub repository `Clive-B/Mid-Year-Activities-Report.git`.
2. The local project was placed under Git, linked to the GitHub remote, committed, and pushed to `main`.
3. The user then asked for a dashboard using the Excel workbook in the folder, with the NCA building as a light/watermark background, the NCA logo, NCA colors, and a professional interactive layout.
4. A first dashboard was created using the workbook structure and sample/dummy data.
5. Upload support was added for `.xlsx`, `.xls`, and `.csv` files.
6. The dashboard started with NCA logo, hero/header, NCA blue/gold theme, upload toolbar, KPI cards, filters, charts, and detailed records.
7. Core KPI cards were added: total submissions, divisions, activities, foreign travels, and leave records.
8. Initial charts were added: submissions by division, leave by type, foreign travel by destination, and activity status/count.
9. The user asked what additional charts would be useful; the dashboard was expanded with management-oriented charts.
10. A chart layout bug was fixed where text in `Leave Days by Division` was scrambled.
11. An executive summary panel was added.
12. The page was made more interactive: clickable cards, filters, search, chart actions, and table interactions.
13. Chart download buttons were added for each chart.
14. Chart type selectors were added so users can switch chart views.
15. The NCA building background was adjusted to become more visible.
16. A bug was fixed where Excel upload failed with `textColor is not defined`.
17. The user described the online Excel connected to Microsoft Forms and asked for online fetch capability.
18. Option 3 using Power Automate to generate JSON from the Excel table was explored.
19. The user configured the Excel response range as an Excel Table so Power Automate could read it.
20. The hourly Power Automate JSON generator was designed:
    - Recurrence trigger every hour.
    - Excel Online for Business: List rows present in a table.
    - Compose JSON metadata/body.
    - OneDrive/SharePoint file update to `nca-mid-year-dashboard-data.json`.
21. The user completed the JSON update flow successfully.
22. A second safer flow was designed to serve the JSON through a Power Automate HTTP endpoint:
    - Trigger: When an HTTP request is received.
    - Get file content using path.
    - Response with `Content-Type: application/json`.
23. The dashboard was given an `Endpoint` button and a `Fetch Online Excel` button.
24. An HTTP 401 issue was diagnosed as endpoint/security/trigger access related.
25. A GET-vs-POST issue was diagnosed from the browser error `TriggerRequestMethodNotValid`; the dashboard fetch was updated to use POST.
26. Online fetch worked after the user corrected the Power Automate flow.
27. The user asked for `Brief Description` to appear in Detailed Submission Records and be charted.
28. The dashboard was updated to include Brief Description in the table and added a description/keyword chart.
29. Auto Executive Brief was added to generate management-style narrative summaries after upload/fetch.
30. Insight Cards were added:
    - Most active division.
    - Activity concentration risk.
    - Travel-heavy unit.
    - Leave pattern observation.
    - Data completeness issue.
31. Ask the Dashboard was added as a local rule-based question box, with examples such as:
    - Which division had the most foreign travel?
    - Show completed activities.
    - Who took annual leave?
    - Summarize RIPS.
32. Presentation Mode was added with executive slide-style navigation and chart download support.
33. Data Quality Monitor was added to flag missing divisions, blank activity titles, missing travel dates, leave duration issues, duplicate names, and incomplete submissions.
34. A layout issue in Data Quality Monitor was fixed, including removing an unwanted right-side panel effect and making `Full Data View` restore the full dataset.
35. The user provided the official NCA division list:
    - RIPS
    - ENGINEERING
    - FINANCE
    - HUMAN RESOURCE
    - AUDIT
    - ADMINISTRATION
    - LEGAL
    - CONSUMER AFFAIRS
    - CYBERSECURITY
    - PROCUREMENT AND PROTOCOL
    - INFORMATION TECHNOLOGY
36. The dashboard was updated to use those official divisions and flag official divisions with no submissions.
37. Division Spotlight was added so clicking a division creates a mini-report with staff, activities, travel, leave, status breakdown, and observations.
38. Leave day totals in Division Spotlight initially showed zero; this was fixed by reading numbered leave-duration columns such as `Duration1`.
39. Narrative Timeline was added to turn activities into a month-by-month story.
40. The footer was changed to `Generated dashboard template for NCA Mid-Year Activity Report workflow.`
41. The user changed the Microsoft Forms/JSON columns and supplied an updated JSON file.
42. The dashboard was checked for the new column `Are you a unit head?`.
43. Unit Head support was added:
    - Parses `Are you a unit head?`.
    - Adds unit-head response charts.
    - Adds unit-head-by-division charts.
    - Uses unit-head context in staff/spotlight logic.
44. The dashboard was made phone friendly for iOS and Android.
45. Mobile layout was adjusted so controls stack cleanly and the logo/watermark remain visible.
46. The user reported that the NCA building watermark was too opaque/hidden between cards.
47. The watermark layering and opacity were adjusted.
48. The Android browser showed the logo as broken text; the logo was copied to `nca-logo.png` and later embedded as Base64 inside the HTML.
49. The NCA building background was blurry because `images.jpg` was only `245 x 206`; a larger `nca-building-watermark.png` was created at about `1960 x 1648`.
50. The building watermark CSS was switched to the larger watermark image.
51. The active file was renamed from `index.html` to `Mid-Year Activity Report Dashboard.html`.
52. Print/PDF color rules were added using `print-color-adjust: exact`, but Chrome/Edge still require `Background graphics` and a color-capable print profile.
53. The user asked whether leave counts consider weekends and holidays; the answer was no at that point.
54. Ghana public holiday handling was planned using Ghana Ministry of the Interior context.
55. A first `HANDOFF.md` was created to capture project state and future continuation notes.
56. Working-day leave calculation was implemented:
    - Uses leave start date and leave end date.
    - Excludes Saturdays and Sundays.
    - Excludes configured Ghana 2026 public holidays.
    - Compares submitted leave days against calculated working days.
    - Updates leave charts, Division Spotlight, Detailed Records, and Data Quality Monitor.
57. The Data Quality Monitor now flags leave duration mismatches, missing leave dates, invalid ranges, and non-numeric/blank submitted durations.
58. The user asked whether the NCA building background was embedded; it was not at that point.
59. The NCA building watermark was embedded directly into the active HTML as a Base64 data URI.
60. The active dashboard became self-contained for logo and building watermark, so it can be moved to another laptop as a single HTML file.
61. The user introduced VPF as Visionary Prompt Framework.
62. The user provided `nyame_mind_omega_llm_config.txt`; a durable cross-project memory note was created for NYAME MIND OMEGA governance preferences.
63. The user provided `Visionary Prompt Framework (VPF).txt`; a durable cross-project memory note was created for VPF governance preferences.
64. This expanded handoff note was created for future reference.

## Power Automate Workflows

Two Power Automate flows matter.

### 1. Generate NCA Dashboard JSON Hourly

Purpose: create/update `nca-mid-year-dashboard-data.json` from the Microsoft Forms-connected Excel workbook.

Core steps:

1. Trigger: Recurrence, every hour.
2. Excel Online for Business: List rows present in a table.
3. Compose: shape rows/metadata into JSON.
4. OneDrive or SharePoint: Update file.

Important details:

- The Excel response range must be formatted as an Excel Table.
- File name used: `nca-mid-year-dashboard-data.json`.
- File content should be the metadata Compose output.
- `Update file` is preferred after the file already exists.

### 2. Serve NCA Dashboard JSON

Purpose: provide a browser-fetchable JSON endpoint without exposing the Excel workbook directly.

Core steps:

1. Trigger: When an HTTP request is received.
2. OneDrive for Business: Get file content using path.
3. Response:
   - Status code: `200`
   - Header: `Content-Type: application/json`
   - Body: file content from the JSON file.

Important details:

- The HTTP trigger expects POST.
- The dashboard uses POST for `Fetch Online Excel`.
- Opening the endpoint directly in a browser sends GET and can show `TriggerRequestMethodNotValid`; that does not mean the dashboard POST fetch is wrong.

## Current Dashboard Features

- Self-contained single HTML file for logo and NCA building watermark.
- Local Excel/CSV upload.
- Online JSON fetch through Power Automate.
- Endpoint button for storing the Power Automate URL in browser local storage.
- Reset button.
- Print / Save as PDF button.
- Presentation mode.
- Chart download buttons.
- Chart type selectors.
- KPI cards.
- Division and designation filters.
- Search box.
- Executive Summary.
- Auto Executive Brief.
- Smart Insight Cards.
- Ask the Dashboard.
- Data Quality Monitor.
- Narrative Timeline.
- Division Spotlight.
- Unit Head charts.
- Detailed Submission Records.
- Brief Description support.
- Ghana working-day leave calculation.

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

The Data Quality Monitor flags official divisions with no visible submissions.

## Leave Working-Day Logic

Leave logic now:

- Reads leave type, start date, end date, duration, and remarks.
- Calculates leave days from start/end dates where available.
- Excludes Saturdays.
- Excludes Sundays.
- Excludes configured Ghana 2026 public holidays.
- Treats submitted values like `1 week` as 5 submitted working days.
- Uses calculated working days for charts and summaries when valid.
- Keeps submitted duration for comparison and audit.

Data Quality Monitor flags:

- Missing leave start or end date.
- End date before start date.
- Missing or non-numeric submitted duration.
- Submitted leave days different from calculated working days.
- Leave date ranges where weekends/holidays appear to have been counted.

Holiday source context:

- Ghana Ministry of the Interior statutory/public holiday information was used as the reference context.
- `https://www.mint.gov.gh/statutory-public-holidays/`

## Print and PDF Notes

The dashboard includes print CSS to preserve color, but browser/printer settings still matter.

If print preview appears black-and-white:

1. Select `Save as PDF` first to isolate browser behavior from a printer driver.
2. Open `More settings`.
3. Enable `Background graphics`.
4. Choose color mode if available.
5. If a physical printer is selected, confirm the printer profile is not grayscale/black-and-white.

The Canon printer shown by the user appeared to force grayscale in preview. That is likely outside the HTML.

## File Portability

The active file `Mid-Year Activity Report Dashboard.html` embeds:

- NCA logo as Base64.
- NCA building watermark as Base64.

Therefore the active dashboard can be moved by itself to another laptop and still show the logo and watermark.

Still useful but no longer required for the active dashboard:

- `nca-logo.png`
- `nca-building-watermark.png`
- `images.jpg`

Keep them for source/reference and future regeneration.

## Git History Landmarks

- `4b79bf7` Add mid-year activity report files
- `cc931e3` Add interactive NCA activity dashboard
- `9d91550` Add dashboard management charts
- `5e02b22` Fix chart value label overlap
- `92b7ea7` Add executive summary panel
- `401fb42` Make dashboard fully interactive
- `17c1700` Fix leave days chart layout
- `457f2dc` Preserve working dashboard before chart options
- `bbda4bb` Add chart downloads and type options
- `00b8208` Fix chart renderer variable errors
- `8214b32` Add online Excel fetch button
- `71ea083` Use POST for online Excel fetch
- `9cc083d` Preserve working live fetch dashboard
- `a4b6e05` Add brief description chart and table column
- `aaa8336` Preserve working dashboard before auto brief
- `ecf2629` Add auto executive brief insights
- `f9bbb5f` Add smart insight cards
- `0a07500` Add local ask the dashboard feature
- `054383f` Preserve working dashboard before presentation mode
- `ffea5e7` Add executive presentation mode
- `d54644e` Preserve working dashboard before data quality monitor
- `2178c3b` Add data quality monitor
- `b832157` Fix data quality monitor layout
- `e49e09e` Add official division context
- `47bfb4e` Track missing official division submissions
- `92f14f1` Add division spotlight reports
- `5461324` Fix leave day totals in division spotlight
- `e21b38e` Handle numbered leave duration fields
- `c39cd2b` Add narrative activity timeline
- `308f768` Update dashboard footer text
- `059c4d5` Add unit head dashboard views
- `c57c3d5` Make dashboard phone friendly
- `f75762f` Improve NCA building watermark visibility
- `a203a6f` Fix watermark layer and mobile logo
- `cef2f8d` Fix Android logo and sharpen watermark
- `8cec2b0` Preserve dashboard colors when printing
- `1130a0d` Add dashboard handoff and leave calculation backup
- `69dfccf` Calculate leave days using working days
- `2627929` Embed building watermark in dashboard

## Known Current Workspace Notes

- `nca-mid-year-dashboard-data.json` is untracked and should remain uncommitted unless the user explicitly asks to publish a sample JSON.
- The dashboard file is large because images are embedded.
- Future edits should account for the large Base64 strings; avoid unnecessary reformatting.
- `nca-building-watermark.png` remains as a source image even though the active dashboard embeds it.
- The Git warning about `C:\Users\codro/.config/git/ignore` permission has appeared but has not blocked commits/pushes.

## Validation Checklist Before Future Commits

1. Read this `HANDOFF.md`.
2. Check `git status --short`.
3. Create a backup copy of `Mid-Year Activity Report Dashboard.html`.
4. Make scoped edits only.
5. Extract inline JavaScript and run `node --check`.
6. Check for accidental non-ASCII unless intentionally needed.
7. Do not commit `nca-mid-year-dashboard-data.json` unless requested.
8. Commit the dashboard, backup, and any required handoff update.
9. Push to `origin main`.

## Recommended Next Improvements

- Add a visible note in the dashboard explaining that leave days are calculated as Ghana working days.
- Add an optional holiday list editor for future years.
- Add a compact print-only executive report layout to avoid depending on browser background graphics settings.
- Add a version label inside the dashboard so users can tell which HTML build they are using.
- Consider whether the embedded 16.8 MB HTML should remain self-contained or whether a lighter asset-folder version is also needed.
