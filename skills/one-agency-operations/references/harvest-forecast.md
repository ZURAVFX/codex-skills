# Harvest and Forecast

## Use the right evidence

Forecast is the future planning/allocation source. Harvest records tracked time and exposes reports according to the user's permissions. Actual hours do not prove future office attendance, and allocations do not prove someone is free at a particular time. Avoid treating the two products as interchangeable.

The originating workflow exercised Forecast's browser schedule and leave display. It did not validate Harvest-specific edit/report controls. For Harvest tasks, discover supported connector tools or inspect the live UI and verify each operation rather than inventing selectors or endpoints.

## Forecast attendance and capacity

Open the signed-in team schedule, confirm the workspace and filter to the relevant department or named people. Inspect enough weeks to cover every candidate, including both organiser and attendee. The observed route was `/ACCOUNT_ID/schedule/team` with a visible search filter and a `startDate` week parameter. Discover ACCOUNT_ID from the signed-in page; never hard-code another user's workspace or department abbreviation.

The observed three-week view showed weekday allocation cells. `Off` indicated time off; `Full`, `open` and `over` described allocation capacity, not timed calendar conflicts. Blank cells did not prove office attendance. Expand the person row or open an assignment's visible detail to establish exact dates, partial-day hours and notes when needed. Inspect without changing assignments; close/cancel any edit form used for a read.

DOM-backed reads used `.content-parent-row`, its `h3` person name, and `.allocation-total` text plus visible `style.left`/`style.width`. At that zoom, weekdays occupied 48 pixels each and a week 240 pixels. **Those dimensions are historical, not constants.** Before mapping any position to a date, establish the current visible week start, zoom, weekday/weekend layout and scale from the rendered UI. Prefer explicit date labels or assignment details where available. Check a boundary example before applying a derived mapping across rows. Do not infer dates from bar order alone.

Week navigation exposed `a.test-next-week` and `a.test-previous-week`. Use these only when observed in the current DOM. A direct navigation using the current page's exposed week parameter can be useful when permitted by the runtime. Observe the resulting dates and wait for actual person rows; a briefly empty page during loading is not a schedule with no leave.

Cross-check calendar absence and working-location entries. Explicit leave overrides nominal office-day rules. Partial leave needs a time-of-day check. If leave spans outside the displayed range, inspect the next/previous view or underlying assignment detail. Record the source and date checked, not a permanent claim about a person's attendance.

## Other Forecast and Harvest tasks

Support the specific requested operation using available tools/UI: capacity review, allocations, project staffing, time-entry review, reporting or corrections. Establish the workspace, people/projects, date range, units and requested write scope. Discover actual task/project identifiers and available report fields; do not select the first similarly named person or project.

For comparison reports, keep planned hours and actual hours separate, align period boundaries and time zones, and explain how leave, capacity, rounding and billable filters affect comparisons. Do not claim missing or hidden records are zero. Limit employee information to what the user needs and is permitted to access.

For requested writes, read the existing record first. Confirm the exact target and values, preserve unrelated entries, and verify the saved result. Handle partial success and uncertain submissions with a ledger and read-before-retry. Financial actions such as invoicing, payments, rates or approvals require their own explicit task scope and applicable authorisation; a scheduling request does not grant it.

If an operation is unavailable or access is denied, state the exact limitation and the minimum next step. Continue any useful permitted analysis. Do not promise this skill grants administrator access or covers an untested operation automatically.
