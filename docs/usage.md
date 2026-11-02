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
2. Configure your AI model in Settings (via Chenbont Studio's model settings) — the underlying model is configured by you.
3. Create or open a session to start AI-assisted coding. File management, Git, terminal, and an in-app browser preview are built in.

## 3. Phone Remote Access (requires self-hosted Studio Relay)

1. Generate a channel QR code from the desktop app's "Remote Access" panel.
2. Deploy the open-source relay service **Studio Relay** on your server (https://gitcode.com/chenbont/studio-relay); wildcard DNS and TLS are required.
3. Scan the QR code with your phone to access your desktop dev environment remotely.

> Studio Relay is a separate open-source project; its deployment and operations are outside the scope of this closed-source desktop client.

## 4. Upgrade & Uninstall

- **Upgrade**: Auto-update is built in, so manual upgrades are usually unnecessary. You may also download a newer release and reinstall.
- **Uninstall**: On Linux run `sudo dpkg -r chenbont-studio` (or delete the AppImage). Other platforms will be documented on release.

## 5. Get Help

- FAQ: [faq.md](./faq.md)
- Issues: https://gitcode.com/chenbont/studio-relay/issues
