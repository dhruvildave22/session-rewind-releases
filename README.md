# Session Rewind: downloads

Installers for **Session Rewind Notch**, a small Mac app that shows your Claude Code activity around the MacBook notch. Unofficial: not affiliated with Anthropic.

**[Download the latest version](../../releases/latest)**

- Apple Silicon Macs (M1 and later): the `arm64` file.
- Intel Macs: the other `.dmg`.

## What it does

- A pill at the notch: a dot for your sessions (green = Claude is working, amber = waiting for you), prompts today and corrections today.
- Hover for today's numbers, each session with its context fill, and rule ideas from corrections you repeat, with a copy button.
- A menu bar icon with the same counts, and **Launch at login**, **Hide the notch pill** and **Quit**.
- Works on Macs without a notch too (a small pill at the top centre, plus the menu bar icon).

## Privacy

The app only reads `~/.claude/projects` on your Mac. It makes no network requests and sends nothing anywhere.

## Install

1. Download the `.dmg` for your Mac from the latest release.
2. Open it and drag **Session Rewind Notch** to Applications.
3. Open it. macOS will say it cannot verify the app, because it is not notarized (that needs a paid Apple account). Click **Done**, then allow it once:
   - **System Settings → Privacy & Security**, scroll to the bottom, click **Open Anyway** (it appears after the first attempt and stays for about an hour), or
   - run this in Terminal and open the app again:
     ```bash
     xattr -dr com.apple.quarantine "/Applications/Session Rewind Notch.app"
     ```
4. Hover the notch, or click the rewind icon in the menu bar. Tick **Launch at login** in its menu to start it automatically.

There is no Dock icon. Quit from the menu bar icon. There is no auto-update yet: download the new `.dmg` and replace the app.

To check a download: `shasum -a 256 <file>.dmg` should match `SHA256SUMS.txt` on the release.

## Also

The same engine powers the **Session Rewind** VS Code extension: search "Session Rewind" in the Extensions panel.

This repository only holds the downloads. Source code is not published here.
