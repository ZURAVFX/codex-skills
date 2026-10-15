# Codex skills

Skills for the Codex app. Each one lives under `skills/`.

## one-agency-operations

Coordinate One Agency Portal boardrooms, Google Calendar meetings, Forecast leave and capacity, and Harvest time/reporting tasks. Includes first-use connection guidance, department-specific planning, room/calendar verification, and rescheduling or cancellation handling.

Paste this into Codex:

> Install the one-agency-operations skill from https://github.com/ZURAVFX/codex-skills/tree/main/skills/one-agency-operations into my personal Codex skills folder.

Then ask:

> Use $one-agency-operations to plan my team's monthly 1:1s. Help me connect the services we need, check leave and rooms, and ask me before booking.

Google Calendar is the connection used for calendar bookings; Gmail is optional for email tasks. Each department head connects their own Portal, Harvest and Forecast accounts. The skill contains no credentials or employee records. See [setup and sharing](skills/one-agency-operations/references/setup.md).

## zura-releases

Ship, back up and present Zura / OA Motion projects. It records where a release goes, how source development files are backed up, and how a project gets a landing page that matches zuravfx.com.

## video-download

Download video or audio from yt-dlp-supported platforms, including YouTube, Instagram, Vimeo and TikTok. Includes format selection, bounded extractor repair and a browser-session fallback when login is needed.

Paste this into Codex:

> Install the video-download skill from https://github.com/ZURAVFX/codex-skills/tree/main/skills/video-download into my Codex skills folder. If my old instagram-download skill is this collection's unchanged version, replace it with video-download.

Then ask: “Use video-download to download these links into my reference folder.”

## Install zura-releases

Windows PowerShell:

```powershell
python "$env:USERPROFILE\.codex\skills\.system\skill-installer\scripts\install-skill-from-github.py" --repo ZURAVFX/codex-skills --path skills/zura-releases
```

macOS or Linux:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo ZURAVFX/codex-skills --path skills/zura-releases
```

The skill is available on your next turn. The installer stops if the skill is already installed, so update by deleting the folder and running it again.

## Install without the helper

Windows PowerShell:

```powershell
git clone --depth 1 https://github.com/ZURAVFX/codex-skills.git "$env:TEMP\codex-skills"
Copy-Item -Recurse -Force "$env:TEMP\codex-skills\skills\zura-releases" "$env:USERPROFILE\.codex\skills\"
```

macOS or Linux:

```bash
git clone --depth 1 https://github.com/ZURAVFX/codex-skills.git /tmp/codex-skills
cp -R /tmp/codex-skills/skills/zura-releases ~/.codex/skills/
```

## Updating

Delete `~/.codex/skills/zura-releases` (or `%USERPROFILE%\.codex\skills\zura-releases`) and install again.
