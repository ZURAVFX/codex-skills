# Setup and sharing

## Discover capabilities before requesting setup

Inspect the available tools and installed connections. Tool names vary by host; match capabilities rather than hard-coding a connector namespace. A missing tool in the initial listing does not prove a plugin is unavailable: use tool discovery or plugin search if provided.

| Task | Needed access |
| --- | --- |
| Read or create calendar meetings and personal blocks | Google Calendar connection with the relevant read/write capabilities |
| Read historical email context or send a requested email | Gmail connection, only when email is part of the request |
| Check or reserve boardrooms | Signed-in One Agency Portal browser session, or an actually available supported connector |
| Check future leave and allocations | Forecast account with access to the relevant team |
| Review actual hours, time entries or reports | Harvest account with access to the relevant people/projects |

Gmail alone does not enable Google Calendar bookings. Installing this skill does not install plugins, sign anyone in, grant permissions or make browser automation available.

If Google Calendar is missing, use the host's plugin search/setup flow for Google Calendar and guide the user to connect the intended work account. If no setup tool is available, explain the missing capability and ask them to connect it through their app's integrations UI. Avoid inventing exact menu names. Verify setup with a harmless calendar read, not a test invitation. A read-only connection cannot create events.

For Portal, use https://portal.oneagencymedia.co.uk/boardrooms. For Harvest or Forecast, prefer the user's existing tab or a verified service link. Let the user complete passwords, MFA and any access-consent steps that require them. Ask for the minimum missing login, then resume and verify the displayed account/workspace. Do not request passwords or tokens in chat or store them in the skill.

Harvest and Forecast can share a sign-in provider, but access to one does not establish access to the other. Discover the actual workspace, department filter and permissions. Never copy the originating user's account ID, email, tab ID or saved session into another user's setup.

## If browser access is unavailable

Use a suitable supported connector if available. Otherwise ask the user to enable the host's browser capability or complete the specific UI action themselves. Do not claim room availability was checked when you only checked Google Calendar. Preserve the proposed plan while setup is completed.

In the originating session, a disconnected Windows network-drive mapping disrupted browser tooling; removing it was a user-authorised machine-specific fix. It is not a setup dependency or a general repair step. Do not change drive mappings, browser profiles or security settings merely to use this skill.

## Install for another department head

Share this repository path:

https://github.com/ZURAVFX/codex-skills/tree/main/skills/one-agency-operations

They can ask Codex:

> Install the one-agency-operations skill from ZURAVFX/codex-skills, path skills/one-agency-operations, into my personal Codex skills folder.

Use the available skill installer, or copy the complete folder into the host's personal skill directory (normally `~/.codex/skills/`). Respect `CODEX_HOME` when configured. Preserve customised existing files during updates. Start a new turn/session or reload skills as required by that host, then invoke `$one-agency-operations`.

First-run prompt:

> Help me connect the services needed to schedule my team's meetings. My department is [department], my time zone is [zone], and our office days are [days]. Plan [date range] first, then ask me before making bookings.

Each user connects their own accounts. No credentials, employee information or session files are distributed with this skill.
