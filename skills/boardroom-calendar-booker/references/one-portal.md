# One Portal boardrooms

This method was exercised in October 2026 at https://portal.oneagencymedia.co.uk/boardrooms. Inspect the current page; labels and layouts can change. Do not reuse historical numeric accessibility indexes or tab handles.

## Read availability

The page exposed Main Boardroom, Small Boardroom, Sales Boardroom and Snug Boardroom tabs, with previous/selected/next week navigation and Month/Week/Day views. Confirm the selected room and week before reading bookings. Check each reservation's actual day and interval; a flat list of event titles can lose column association.

In the observed DOM snapshot, each day's bookings appeared before that day's 08:00 slot button, rather than next to their time-row buttons. Do not generalise this layout without checking it. A screenshot or opening the event detail can establish the column/date when ambiguous. Empty-slot buttons remained present even where an event existed, so a clickable slot is not evidence of availability.

## Create a booking

Click an observed slot for the desired date/time. The Add Event form exposed Title, Subtitle, Start, End, Meeting Type and Recurrence. Use a concise ordinary scheduling title, with no private discussion notes. Select Internal for an internal meeting when appropriate. Use Does not repeat for individually checked dates.

Working DOM locators included textbox names `Title`, `Start`, `End`; a combobox matching `Meeting Type`; option `Internal`; and button `Confirm`. Native accessibility rendered the button as `CONFIRM` while the DOM used `Confirm`. Label-based selectors were not always usable; obtain fresh runtime-specific names from the page rather than assuming equivalent casing or labels.

**Critical input pitfall:** DOM `fill()` on the date/time fields appeared to set values but the saved reservations retained their original half-hour defaults. Native accessibility `setValue()` on the current Start/End date-field indexes successfully committed the changes in that session. Use that method when supported, or another documented user-input method. Re-read the form, submit, then open/read the saved booking. Verify the actual persisted interval, not just the form's displayed value or success toast.

The UI briefly retained an old/modal snapshot after save. Obtain a fresh observation or wait for the documented modal-hidden condition before the next action; do not blindly repeat Confirm and create duplicates. A toast reading “Event has been created!” confirms creation but not its correctness.

## Edit or release a room

Open the matching booking by date/title and inspect its detail. Observed icon test IDs were `EditRoundedIcon`, `DeleteRoundedIcon` and `ClearRoundedIcon`; use them only if still present in the live DOM. Editing exposed the same Start/End fields. The native date-field method above repaired saved durations; reopening the event verified the correction.

Deletion had two stages: the detail's Delete control, then a separate “Delete event?” confirmation. Complete the intended cancellation and verify the booking is absent from the correct room/week. Dismissing the first popover alone is not cancellation. Follow the host's confirmation policy if an action requires fresh user confirmation.

For repeated operations, helper functions may derive current indexes from fresh accessibility output and use observed semantic locators. Keep mutations sequential. Stop on a mismatched date, missing element, validation error or ambiguous save, inspect, then continue from verified state.

After all writes, audit the saved bookings against the calendar ledger: date, time, duration and room. Save a screenshot that visibly includes relevant results when the browser runtime requires proof of work. Keep the evidence local to the task, not in this shared skill.
