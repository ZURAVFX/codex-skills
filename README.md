# Codex skills

Skills for the Codex app. Each one lives under `skills/`.

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
