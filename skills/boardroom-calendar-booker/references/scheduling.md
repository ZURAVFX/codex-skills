# Meetings and calendar coordination

## Build a feasible plan

1. Identify the team and correct work addresses from authorised sources; confirm genuinely ambiguous membership. Read previous relevant meetings and existing future events. Distinguish scheduled, cancelled and declined entries; calendar history alone does not prove a meeting happened.
2. Establish the planning horizon, cadence, duration, office days and daily meeting load. An appraisal counts as a monthly check-in only if the user wants it to. Prefer one team 1:1 per day and offer 30-minute private prep/action blocks as defaults when the user wants focused check-ins, not universal company policy.
3. Aim for roughly one calendar month between individual meetings. Move around leave and holidays; show unusually short or long gaps. Avoid an indefinite recurring series when only a bounded period has been checked.
4. Check Forecast leave for both organiser and guest. Read calendar working-location and absence entries as well as free/busy. Transparent all-day leave may not appear in availability results. Read full event details when search results omit all-day dates. Treat all-day end dates as exclusive.
5. Check the organiser for the whole meeting/prep/action window and guests for the meeting. Existing unrelated 1:1s also count towards workload. Use the same day or nearby working day for focus blocks according to the user's preference. Do not overlap lunch, existing blocks or work-hour limits without a deliberate decision.
6. Inspect Portal availability for the full proposed interval. Prefer Main Boardroom when requested, otherwise choose a suitable available room. A calendar event location is not a room reservation.

For each candidate keep: person/email, prior meeting, proposed date and local times, time zone, prep/action times, calendar check, leave/location evidence, room and any exception. If sources disagree or physical attendance is unclear, flag the particular uncertainty; never infer “in the office” simply from an unallocated Forecast day.

## Commit and verify

Once authorised, recheck the chosen slots. Reserve the room and verify its saved date, start, end and room; then create the invitation with the correct guest and the verified room location. Create private busy prep/action events with no guest or room booking. Explicitly disable Google Meet when an in-person meeting or personal focus block does not need it; some connectors add a conference by default.

Use a task-local ledger containing calendar IDs/event IDs, intended intervals, Portal booking identity if visible, verified room details and per-step status. Before retrying a timed-out create, search that exact date/title/person to see whether it already succeeded. If the room fails, try a checked alternative before sending the invitation. If the calendar fails after reserving a room, repair it or release the newly created unused reservation; report partial results accurately.

Read back saved calendar events. Verify title, guest email, local times, room, status, and private/busy properties of personal blocks. Batch-read tools may return fewer records than requested: compare returned IDs with requested IDs, then read only missing records in smaller batches. In the exercised connector, batches of ten worked; do not assume that limit applies everywhere.

## Reschedule and cancel

Read the existing event and its organiser/recurrence before writing. An instance ID is not the series ID. Match the user's intended scope: one instance, following occurrences or the whole series. Preserve prior history where the interface supports future-only changes. Avoid attempting a split recurrence without understanding the connector's non-atomic behaviour.

When asked to move a named person's upcoming 1:1, identify that exact occurrence and its linked room/prep/action blocks. Preserve future monthly bookings unless the user also asks to adjust the cadence; flag any resulting short gap. Prefer updating the existing invitation and room reservation over creating duplicates. Recheck availability for the new times, including all personal blocks, and verify that the old room slot is released. Never move another team member's meeting just to make space without authorisation.

Changing an attendee's copy can succeed without changing the organiser's invitation. In the exercised workflow, a primary-calendar update returned success but the organiser's calendar still had the old time. If the user is not the organiser, verify the organiser-side result when readable. A successful local update is not evidence that guests were rescheduled. If edit access is denied, stop organiser writes; use an authorised replacement invitation and decline/remove the old invitation on the user's own calendar, or ask the organiser to update it. State which happened.

For cancellations, cancel user-owned invitations, remove associated personal blocks and release the matching Portal reservations. For someone else's recurring series, the user can decline their invitation; that does not cancel the organiser's series. If declining the whole series would also change past RSVP states, prefer the supported future-only scope or explain the scope before applying a broader response. Do not delete past history merely to remove future meetings.

Reconcile all affected services after changes. Keep unrelated appraisals or handovers when the user only cancels following monthly check-ins. Report remaining organiser-owned entries separately from the meetings and rooms you successfully cancelled.
