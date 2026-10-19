---
name: boardroom-calendar-booker
description: Coordinate One Agency Portal rooms, Google Calendar meetings, and Harvest or Forecast work planning. Use for availability checks, scheduling, room reservations, time and capacity reviews, and requested updates in these services, including connection setup.
---

# Boardroom Calendar Booker

Help any department head use One Portal, Forecast, Harvest and Google Calendar together. Support standalone tasks in any of these services as well as meeting workflows. A skill supplies instructions, not access: discover the tools and permissions actually available.

## Choose the route

- For first use, missing tools, login problems or a different user's account, read [setup.md](references/setup.md).
- For meetings, monthly 1:1s, preparation blocks, rescheduling or cancellations, read [scheduling.md](references/scheduling.md).
- Before reading or changing boardroom bookings, read [one-portal.md](references/one-portal.md). It records the working UI method and an important date-input failure.
- For leave, allocation, timesheets, reporting or resource planning, read [harvest-forecast.md](references/harvest-forecast.md). The Forecast method was exercised; Harvest-specific operations must be discovered from the connected tools or live UI.

Use only the references relevant to the current request. Do not demand all four services for a task that needs only one.

## Establish scope once

For Elliot McKenzie's team, the user confirmed that office days are always Monday, Wednesday and Thursday. Apply this standing rule to their in-person scheduling without asking again; explicit leave, sickness and off-site commitments still override it. Keep this preference scoped to Elliot's team when sharing the skill with other departments.

Infer the user's requested outcome and existing authorisation from the conversation. Identify any missing account, team, date range, time zone, office-day rule or write scope that materially affects the task. Ask a small, consolidated question when necessary and continue independent checks. Do not assume the originating team's membership, Monday/Wednesday/Thursday attendance, meeting lengths or monthly cadence applies to everyone.

For a whole-team request, establish which department/team is theirs and who belongs in scope before booking. Reuse a previously confirmed roster; otherwise ask the user to identify the team and confirm any uncertain members. For a named-person request, work only with that person and the requested meeting. Do not ask for a whole-team roster or change the rest of their series unless needed to resolve ambiguity or explicitly requested. A reschedule includes that meeting's linked room, prep and follow-up blocks.

If the user requests a plan before booking, prepare the concrete dates, guests, room choices and focus blocks before seeking approval. Once approved, complete the authorised work without repeatedly asking to continue. A later change, such as someone moving teams, should update all associated meetings, rooms and personal blocks.

Prefer connected service tools. Use the available approved browser runtime for services without a suitable connector. Read its current documentation; do not assume this skill's historical selectors are still correct. Inspect live UI before acting. Never extract cookies, hidden application state or session credentials to construct an undocumented API client.

## Cross-service correctness

- Treat Forecast leave, calendar conflicts and Portal room availability as separate checks. None alone proves physical attendance.
- Check the user's current calendar, not just the guest's: the meeting and every prep/follow-up block must fit around existing meetings and busy time. Re-read current records rather than relying on an earlier planning run. If no slot meets the user's office-day or daily meeting-load constraints, explain the conflict and ask which constraint may change before booking an exception.
- Confirm people by work email or account ID; abbreviated names can identify different colleagues.
- Use local times with an IANA time zone, including daylight-saving changes. Prefer :00 or :30 starts for meetings and focus blocks unless the user specifies otherwise.
- Recheck the specific slot before committing. Maintain a local task ledger of intended and verified changes, with event IDs and room details, to avoid duplicates after interruptions. Keep this operational data outside the shared skill and repository.
- A success toast is evidence of submission, not proof of the saved duration or both parties' calendars. Verify relevant saved fields and account context.
- Treat multi-service writes as non-atomic. Track partial success and repair only the task's own changes. After an unknown outcome, read before retrying.
- A 403 or explicit access denial is a boundary. Do not retry through another identity or endpoint. Explain what remains and who can complete it; continue unaffected work.

Report the final result in plain language: what is booked or changed, what was verified, and any specific unresolved item. Do not say invitations were accepted just because they were created. Keep screenshots, employee data, booking ledgers and credentials out of the reusable package.

## Example requests

- “Use $boardroom-calendar-booker to plan monthly team 1:1s for the next quarter. Check leave and rooms, and show me the plan before booking.”
- “Find a boardroom for a project review next Wednesday, invite these colleagues and reserve 30 minutes afterwards for actions.”
- “Compare next month's Forecast capacity with last month's Harvest actuals for this department.”
- “Cancel this person's future check-ins, release the rooms and remove my related prep blocks.”
