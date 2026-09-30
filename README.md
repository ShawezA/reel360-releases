# REEL/360

An AI-assisted video editor for Linux. Drop in raw footage, say what you want
("make it funny, show what a disaster this build was"), and an AI editor cuts it
the way a skilled human editor would. Then you watch, tweak and override in a
native editor that works like Premiere or Resolve.

This repository hosts the **releases** only.

## Download and run

1. Download **[REEL360-x86_64.AppImage](../../releases/latest/download/REEL360-x86_64.AppImage)**
   (or pick a version under [Releases](../../releases)).
2. Make it executable and start it:

   ```sh
   chmod +x REEL360-x86_64.AppImage
   ./REEL360-x86_64.AppImage
   ```

   Most file managers can do the same: right-click → Properties → "Allow executing as program".

Nothing else to install: Python, Qt, ffmpeg and everything else are inside the one file.
Works on 64-bit Linux distributions from about 2022 on (Ubuntu 22.04+, Debian 12+, Fedora 36+, …).

## First start

A setup window walks you through:

- **Claude Code**: the AI editor runs on Claude Code with **your own** Claude subscription
  (Pro or Max). The window installs it with Anthropic's official installer and opens a
  terminal so you can sign in.
- **App menu**: adds REEL/360 to your applications menu.
- **API keys** (optional): hosted models for transcription and vision (OpenRouter, Qwen, Gemini)
  use your own accounts. Keys stay on your machine in `~/.config/reel360/settings.env`,
  readable only by you.

## Updates

At every start REEL/360 checks this repository for a newer release. When one is out, an
**UPDATE** key appears in the status bar. It shows what's new, replaces the AppImage in
place (checksum-verified), and restarts. You can also run `./REEL360-x86_64.AppImage update`,
or turn the check off in Settings → AI & Hardware → Updates.

Keep the AppImage somewhere you own (for example `~/Applications`) so it can update itself.

## Command line

```sh
./REEL360-x86_64.AppImage my-project.reel   # open a project
./REEL360-x86_64.AppImage doctor            # check your setup
./REEL360-x86_64.AppImage --help            # all commands
```

## Licence

REEL/360 is proprietary, not open source: see **[LICENSE.txt](LICENSE.txt)**. In short: the
download is free and the manual editor works without a licence; a free trial covers three AI edits;
a paid licence (Founder, or a monthly / yearly subscription, sold through Polar) unlocks the AI
editor, rendering and export. Enter the key in Help → Licence…. You may pass the unmodified AppImage
on (package managers and mirrors are welcome); a licence key is personal. The AI services you
connect (Claude Code, OpenRouter, …) run on your own accounts, under those providers' terms and costs.

The AppImage also contains open-source software: Python, Qt / PySide6 (LGPL v3), FFmpeg (the
libraries REEL/360 uses: LGPL; the separate `ffmpeg` / `ffprobe` programs: GPL v3), OpenCV,
MediaPipe, ONNX Runtime, faster-whisper, yt-dlp, Deno, the Plex fonts and more. Each keeps its
own licence, and the REEL/360 licence does not limit what those licences allow you to do (for
example, replacing the LGPL libraries with your own builds).

- **[THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt)**: every component, its licence and the
  full licence texts
- **[SOURCES.txt](SOURCES.txt)**: the source code of the GPL / LGPL components. It is attached to
  every release as `REEL360-<version>-sources.tar`.
- The same files are inside the AppImage: `./REEL360-x86_64.AppImage --licenses`, or
  Help → About → LICENCES.

These files are updated by every release; the ones attached to a release belong to that version.
