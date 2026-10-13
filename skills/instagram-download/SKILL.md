---
name: instagram-download
description: Download user-supplied Instagram reel or post URLs locally with yt-dlp, including outdated extractor repair and a Firefox or chosen-browser login fallback.
---

# Instagram downloads

Download the requested links with yt-dlp for local editing or reference analysis. Use CLI tools first. Browser automation and manual file selection are unnecessary when this route works.

## Fast route

1. Find `yt-dlp` (or an existing Python environment with `python -m yt_dlp`) and read `--version`. Reuse the installed tool and the user's chosen output directory.
2. Try the public URL first, without cookies. Batch independent links in one invocation:

```bash
yt-dlp --no-playlist --retries 1 --fragment-retries 1 --socket-timeout 20 --no-progress --no-overwrites --write-info-json -o "OUTPUT_DIRECTORY/%(id)s.%(ext)s" "INSTAGRAM_URL"
```

Pass commands as argument arrays where possible. With a shell, quote each URL and output template appropriately for that shell. Do not interpolate arbitrary user text into command code.

3. If extraction fails and the installation is outdated, update once through its owning installer and retry publicly. For a pip installation, use that same Python interpreter:

```bash
python -m pip install --upgrade yt-dlp --disable-pip-version-check
```

For a self-updating standalone executable, use `yt-dlp -U`. Package-manager installations should use their package manager. Do not switch interpreters or install multiple copies blindly.

4. Only if the updated extractor still requires login, use the user's named or default browser session:

```bash
yt-dlp --cookies-from-browser firefox --no-playlist --retries 1 --fragment-retries 1 --socket-timeout 20 --no-progress --no-overwrites --write-info-json -o "OUTPUT_DIRECTORY/%(id)s.%(ext)s" "INSTAGRAM_URL"
```

Firefox was the successful session fallback in the originating workflow. Do not assume Chrome. Substitute the supported browser the user actually uses. A Chrome DPAPI decryption failure is a cookie-access failure, not evidence that the public download is impossible. Do not keep retrying the same failed cookie extraction or bypass browser security.

## Confirm the result

Use the printed final path, confirm the file is non-empty, then inspect it with:

```bash
ffprobe -v error -show_entries format=duration:stream=codec_type,width,height,avg_frame_rate -of json "DOWNLOADED_FILE"
```

Confirm a video stream, plausible duration and dimensions. Do not force 24 fps: approved references can have different frame rates. Report the actual files downloaded and any remaining failures. Metadata and contact sheets alone do not establish audio quality, motion quality or full visual matching.

Keep downloaded client media, `.info.json` files (which can include signed URLs), cookies and authentication details out of source control. Do not print cookie contents or export a reusable cookie file. Cache successful files so subsequent analysis does not download them again.

After one relevant update and one appropriate browser-session attempt, report the specific remaining error and request an uploaded file or user-assisted download if necessary. Do not enter repeated repair loops or use Computer Use automatically. These steps improve reliability but cannot guarantee access to private, removed or restricted posts.

## Evidence behind this workflow

In October 2026, yt-dlp 2026.03.17 failed three supplied Instagram reels with login/extractor errors. Updating the same pip installation to 2026.08.19 allowed all three to download publicly. Firefox session extraction also succeeded; Chrome session extraction had failed with DPAPI. Treat those versions as historical evidence, not dependency pins.
