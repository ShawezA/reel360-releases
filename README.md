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

## Bundled software

ffmpeg/ffprobe (GPL build, https://ffmpeg.org), Qt / PySide6 (LGPL), and Python packages
under their own licenses.
