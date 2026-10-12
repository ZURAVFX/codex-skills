# Codex skills

Skills for the Codex app. Each one lives under `skills/`.

## zura-releases

Ship, back up and present Zura / OA Motion projects. It records where a release goes, how source development files are backed up, and how a project gets a landing page that matches zuravfx.com.

## Install

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
