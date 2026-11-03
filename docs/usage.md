# Usage Guide

> This document describes only the published installers. No source code is involved.

## 1. Installation

### Linux (.deb)
1. Download `Chenbont-Studio-0.1.56-amd64.deb` from [Releases](../).
2. Install: `sudo dpkg -i Chenbont-Studio-0.1.56-amd64.deb` (run `sudo apt -f install` if dependencies are missing).
3. Launch from the application menu or `chenbont-studio` in a terminal.

### Linux (AppImage)
1. Download `Chenbont-Studio-0.1.56-x86_64.AppImage`.
2. Make it executable: `chmod +x Chenbont-Studio-0.1.56-x86_64.AppImage`.
3. Run by double-click or from the terminal.

### Windows / macOS
Windows / macOS installers are not yet released (shown as "Coming soon"). Instructions will be added when available.

## 2. First Launch

1. Complete the initial setup prompts on first launch.
2. Configure your AI model in **Settings → Models** (any OpenAI-compatible / Responses API endpoint is supported) — the underlying model is configured by you.
3. Create or open a session to start AI-assisted coding. Built-in capabilities include:
   - **File management**: Monaco editor (30+ languages), file tree, three views (Edit / Diff / Preview);
   - **Git**: multi-repo management, branch switching, history, AI-generated commit messages, AI merge-conflict resolution;
   - **Terminal**: multi-tab, keeps running when switching projects;
   - **Browser preview**: multi-tab, element picking, agent-driven automation;
   - **Database management**: SQLite / MySQL / PostgreSQL with AI natural-language SQL generation;
   - **GitHub integration**: browse / merge PRs, manage issues;
   - **Automation & scheduled tasks**: once / interval / daily / weekly / monthly / cron.

## 3. Phone Remote Access

Chenbont Studio offers three ways to access your desktop from a phone:

1. **LAN**: generate a channel QR code from the desktop app's "Remote Access" panel and scan it with your phone (device-token auth);
2. **Official relay (zero-config)**: scan-to-connect (free tier: 1 phone controller + 1 guest; Pro adds more devices — see [docs/中继服务定价.md](./中继服务定价.md));
3. **Self-hosted / SSH tunnel**: deploy the open-source relay service **Studio Relay** on your own server (https://gitcode.com/chenbont/studio-relay; wildcard DNS and TLS required), or set up an SSH reverse tunnel on your own VPS.

From the phone you can watch sessions stream live, send messages, interrupt or rewind turns, approve tool calls, browse files & diffs, and run git operations (including AI commit messages).

> Studio Relay is a separate open-source project; its deployment and operations are outside the scope of this closed-source desktop client.

## 4. Upgrade & Uninstall

- **Upgrade**: Auto-update is built in (pulls from GitHub Releases), so manual upgrades are usually unnecessary. You may also download a newer release and reinstall.
- **Uninstall**: On Linux run `sudo dpkg -r chenbont-studio` (or delete the AppImage). Other platforms will be documented on release.

## 5. Get Help

- FAQ: [faq.md](./faq.md)
- Issues: https://github.com/chenbont/chenbont-studio/issues
