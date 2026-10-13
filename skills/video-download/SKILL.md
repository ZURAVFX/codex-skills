---
name: video-download
description: Download user-supplied video or audio URLs locally with yt-dlp from supported platforms, including extractor repair, format selection and the user's browser session when login is needed.
---

# Video downloads

Download requested links from yt-dlp-supported sites, including YouTube, Instagram, Vimeo and TikTok, for local editing or reference analysis. Support varies by site and URL; inspect the actual extractor result. Use CLI tools first.

## Fast route

1. Find `yt-dlp` (or an existing Python environment with `python -m yt_dlp`) and read `--version`. Reuse the installed tool and the user's chosen output directory.
2. For public links, try without cookies first. If the user explicitly requests authenticated content, use their chosen browser session directly. Preserve requested quality, format and audio-only requirements. Batch independent links in one invocation:

```bash
yt-dlp --no-playlist --retries 1 --fragment-retries 1 --socket-timeout 20 --no-progress --no-overwrites --write-info-json -o "OUTPUT_DIRECTORY/%(extractor_key)s-%(id)s.%(ext)s" "VIDEO_URL"
```

Pass commands as argument arrays where possible. With a shell, quote each URL and output template appropriately for that shell. Do not interpolate arbitrary user text into command code. The extractor prefix avoids ID collisions between platforms. Keep `--no-playlist` for individual links; use playlist download only when requested, with the requested item limit. Default yt-dlp quality selection is appropriate unless the user specifies otherwise. Separate video/audio streams need ffmpeg to merge. Audio extraction (`-x`) may also need ffmpeg; preserve the original audio unless conversion is requested. Use `-F` when format selection is unclear. Do not promise every result will be MP4.

3. If extraction fails and the installation is outdated, update once through its owning installer and retry publicly. For a pip installation, use that same Python interpreter:

```bash
python -m pip install --upgrade yt-dlp --disable-pip-version-check
```

For a self-updating standalone executable, use `yt-dlp -U`. Package-manager installations should use their package manager. Do not switch interpreters or install multiple copies blindly.

4. When the error actually requires login, use the user's named or default supported browser session. An authentication error does not always require an update first:

```bash
yt-dlp --cookies-from-browser firefox --no-playlist --retries 1 --fragment-retries 1 --socket-timeout 20 --no-progress --no-overwrites --write-info-json -o "OUTPUT_DIRECTORY/%(extractor_key)s-%(id)s.%(ext)s" "VIDEO_URL"
```

Firefox was the successful session fallback in the originating workflow. Do not assume Chrome. Substitute the supported browser the user actually uses. A Chrome DPAPI decryption failure is a cookie-access failure, not evidence that the public download is impossible. Do not keep retrying the same failed cookie extraction or bypass browser security.

## Confirm the result

Use the printed final path, confirm the file is non-empty, then inspect it with:

```bash
ffprobe -v error -show_entries format=duration:stream=codec_type,width,height,avg_frame_rate -of json "DOWNLOADED_FILE"
```

Confirm the requested video or audio stream and plausible duration; for video, check dimensions and actual frame rate. Preserve source frame rate unless conversion is requested. If ffprobe is unavailable, report that validation limitation rather than claiming the media was inspected. Report the actual files downloaded and any remaining failures. Metadata and contact sheets alone do not establish audio quality, motion quality or full visual matching.

Keep downloaded client media, `.info.json` files (which can include signed URLs), cookies and authentication details out of source control. Do not print cookie contents or export a reusable cookie file. Cache successful files so subsequent analysis does not download them again.

After one relevant update and one appropriate browser-session attempt, report the specific remaining error and request an uploaded file or user-assisted download if necessary. Skip irrelevant repair routes for deleted URLs, unsupported extractors, DRM or unavailable media. Do not enter repeated repair loops, bypass access controls or use Computer Use automatically. These steps improve reliability but cannot guarantee access to private, removed or restricted media.

## Instagram-specific historical evidence

In October 2026, yt-dlp 2026.03.17 failed three supplied Instagram reels with login/extractor errors. Updating the same pip installation to 2026.08.19 allowed all three to download publicly. Firefox session extraction also succeeded; Chrome session extraction had failed with DPAPI. Treat those versions as historical evidence, not dependency pins.
