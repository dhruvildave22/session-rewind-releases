# Session Rewind: downloads

Installers for **Session Rewind Notch**, a small Mac app that shows your Claude Code activity around the MacBook notch. Unofficial: not affiliated with Anthropic.

**[Download the latest version](../../releases/latest)**

- Apple Silicon Macs (M1 and later): the `arm64` file.
- Intel Macs: the `x64` file (in 0.1.0 it is the one without a suffix).

## What it does

- A pill at the notch: a dot for your sessions (green = Claude is working, amber = waiting for you), prompts today and corrections today.
- Hover for today's numbers, each session with its context fill, and rule ideas from corrections you repeat, with a copy button.
- **Move it anywhere.** Drag the top bar to put it on any screen as a small pill; drag it back near the notch (or double-click the bar) and it docks again. A smaller panel is the default, with a **Larger panel** option.
- **Alerts** (all local, from your own Claude Code activity):
  - **Claude needs you**: when a session that worked for a while stops and waits for you, the island glows and a notification appears. Silent unless you turn the sound on.
  - **Daily budget**: set $20 to $500 a day; the spend tile fills as you go and you get a notice at 80% and 100%.
  - **Context warnings**: a nudge when a session's context passes 80% ("consider /compact or a new session").
- **At a glance:** a 7-day spend chart, how long each session has been working or waiting, and a click on a session opens its folder in VS Code.
- **Keep it open:** a pin in the panel, or press **Control+Option+N** from anywhere to pin or unpin it.
- **Spend:** today's Claude Code spend (and the last 7 days), in the panel, the menu bar and on each session. It is Claude Code's own cost figure, not your bill on a subscription plan; `~` means part of it is estimated.
- **Switch the Claude Code account** without a terminal: panel, Claude Code account, Switch… (or the menu bar menu). You confirm, then sign in in your browser.
- A menu bar icon with the same counts, and **Launch at login**, **Hide the notch pill** and **Quit**.
- Works on Macs without a notch too (a small pill at the top centre, plus the menu bar icon).

## Privacy

The app only reads `~/.claude/projects` on your Mac. It sends none of your data anywhere.

Its only network use is asking GitHub whether a newer release of the app exists (and downloading it when you update). You can switch that off in the menu bar menu (**Check for updates automatically**). The account section runs the `claude` command on your Mac; the sign-in itself happens in your browser, done by Claude Code.

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

There is no Dock icon. Quit from the menu bar icon.

To check a download: `shasum -a 256 <file>.dmg` should match `SHA256SUMS.txt` on the release.

## Updates

From version 0.3.0 the app checks this page for a newer release every 6 hours (or when you choose **Check for updates…** in the menu bar menu). When there is one, the panel and the menu show **Update and restart**: one click downloads it, checks it, replaces the app and reopens it. In the menu you can also tick **Install updates automatically** (off by default).

- **Every update is signed.** The app installs an update only if its signature verifies against a key built into the app, so a tampered or look-alike file is refused. That is why each release has a `.sig` file next to each `.dmg`.
- The app must be somewhere you can write to (normally Applications). If it cannot replace itself, the menu opens this page instead.
- **Older versions (0.1.x and 0.2.x) cannot update themselves.** Install 0.3.0 or later from the latest release by hand once; after that it updates itself.

## Also

The same engine powers the **Session Rewind** VS Code extension: search "Session Rewind" in the Extensions panel.

This repository only holds the downloads. Source code is not published here.
