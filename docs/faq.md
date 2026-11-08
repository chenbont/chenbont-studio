# FAQ

> Covers only distribution and usage questions — no source code or internal implementation details.

## Contents

- [1. Is this open source?](#1-is-this-open-source)
- [2. Download is slow / failing — what now?](#2-download-is-slow--failing--what-now)
- [3. Is the installer safe? Any antivirus false positives?](#3-is-the-installer-safe-any-antivirus-false-positives)
- [4. Which systems are supported?](#4-which-systems-are-supported)
- [5. Is the software free?](#5-is-the-software-free)
- [6. Can I resell or redistribute it?](#6-can-i-resell-or-redistribute-it)
- [7. Where is my data stored? Is anything uploaded?](#7-where-is-my-data-stored-is-anything-uploaded)
- [8. How do I access from my phone?](#8-how-do-i-access-from-my-phone)
- [9. Do I need to install a CLI / agent runtime separately?](#9-do-i-need-to-install-a-cli--agent-runtime-separately)
- [10. Which models / engines can I use?](#10-which-models--engines-can-i-use)
- [11. Do I need an API key? Can I use a local model?](#11-do-i-need-an-api-key-can-i-use-a-local-model)
- [12. Which UI languages are available?](#12-which-ui-languages-are-available)
- [13. How do I update?](#13-how-do-i-update)
- [14. How do I back up / migrate / fully uninstall?](#14-how-do-i-back-up--migrate--fully-uninstall)
- [15. Something crashed — how do I troubleshoot?](#15-something-crashed--how-do-i-troubleshoot)
- [16. How do I report bugs or suggest features?](#16-how-do-i-report-bugs-or-suggest-features)
- [17. Where do I get the latest version?](#17-where-do-i-get-the-latest-version)
- [18. Enterprise licensing / business inquiries](#18-enterprise-licensing--business-inquiries)

## 1. Is this open source?
No. The Chenbont Studio **desktop app** is proprietary (closed-source) software. This repository provides only documentation and release downloads — no source code. Use is governed by the [LICENSE](../LICENSE). The app is a derivative work of the open-source Mcode project (MIT); upstream copyright and license notices are in [THIRD-PARTY-NOTICES.md](../THIRD-PARTY-NOTICES.md).

## 2. Download is slow / failing — what now?
- Check your network, or retry during a different time window;
- Some networks have limited access to GitHub — try another network or a proxy;
- AppImages need `chmod +x` before they can run;
- Verify file integrity against the `checksums.txt` shipped with each release.

## 3. Is the installer safe? Any antivirus false positives?
Our installers are built and sha256-verified (`checksums.txt`); auto-updates also verify signatures and digests. Some antivirus tools flag Electron apps or unsigned binaries falsely — add the app to your allowlist. If you are still unsure, do not install.

## 4. Which systems are supported?
See "Supported Platforms" in [README](../README.md). Linux (.deb and AppImage, x86_64) is available now; Windows / macOS builds are "Coming soon". Systems below the minimum requirements (e.g. glibc < 2.31) may not run.

## 5. Is the software free?
The software is obtained through this repository (the official channel) — beware of third-party resellers. The client itself is free to use; **AI usage is billed by the model service you configure**, and you control that cost. Off-LAN remote connections go through the official Chenbont relay and require a cloud account: P2P direct traffic is not metered, while relayed traffic includes a monthly allowance and excess is charged at the published rate from your wallet balance. Top up from the remote-control panel.

## 6. Can I resell or redistribute it?
**No.** Unauthorized redistribution, resale, reverse engineering, or embedding into other products is prohibited — see [LICENSE](../LICENSE).

## 7. Where is my data stored? Is anything uploaded?
Chenbont Studio runs locally; sessions and project data stay in the app's user data directory on your machine:

- Sessions, settings and snapshots live in the SQLite database `chenbont-studio.db` (Linux `~/.config/Chenbont Studio/`, Windows `%APPDATA%\Chenbont Studio\`, macOS `~/Library/Application Support/Chenbont Studio/`);
- Logs are under `logs/` in the same directory;
- Engine credentials and configuration live in `~/.chenbont/`.

AI features connect to the model service you configure — see in-app docs and the model provider's terms for data flows. The author does not proactively collect your code. When using the official relay, the relay only forwards encrypted traffic and does not store plaintext.

## 8. How do I access from my phone?
Two options, both under **“Remote Control”** in the left sidebar:
1. **LAN**: the desktop app shows a pairing QR code plus a 6-digit code; scan it (or enter the pairing ID + code) on your phone;
2. **Official relay**: all off-LAN connections go through the official relay and require signing in to a cloud account with an email verification code inside the **Remote Control → Allow external access** panel; connections prefer P2P direct transport, and relayed traffic includes a monthly allowance with excess charged at the published rate from your wallet balance. Self-hosted relays and SSH tunnels are not supported.

Paired devices show their online status in the panel and can be revoked one by one. See [usage.md](./usage.md) for details.

## 9. Do I need to install a CLI / agent runtime separately?
No. The agent runtime (Pi / Claude Code / Codex) is downloaded automatically on first use — no separate CLI install. Runtime components are managed alongside plugins and model settings (**Settings → Plugins**). Keep the network available on first use; the engine stays unavailable until the download finishes.

## 10. Which models / engines can I use?
Configure any OpenAI-compatible / Responses API endpoint in **Settings → Model Configuration**, and assign different models per role (chat, AI commit messages, merge-conflict resolution). Switch between the built-in **Claude Code / Pi / Codex / OpenCode** engines per session. API keys are encrypted with Electron `safeStorage` (backed by the OS keychain).

## 11. Do I need an API key? Can I use a local model?
Yes. The app bundles **no** model credits or relay keys — you must supply the endpoint and key. Any endpoint that speaks the OpenAI protocol / Responses API works, so a locally hosted inference service (e.g. a compatible gateway in front of Ollama or vLLM) can be used too; speed and quality depend on your hardware and the chosen model.

## 12. Which UI languages are available?
12: Simplified Chinese, English, العربية (Arabic), Deutsch (German), Español (Spanish), Français (French), Bahasa Indonesia, 日本語 (Japanese), 한국어 (Korean), Português (Portuguese), Русский (Russian), Tiếng Việt (Vietnamese). Switch under **Settings → General → UI Language**; changes apply immediately.

## 13. How do I update?
Auto-update is built in (electron-updater): the app checks GitHub Releases shortly after launch and then roughly every 4 hours. **Downloads are opt-in** — in **Settings → About** click download, wait for the progress bar, then choose "restart and install". You can also download the new release from Releases and install over the old one; user data and settings are preserved.

## 14. How do I back up / migrate / fully uninstall?
- **Back up / migrate**: fully quit the app, then copy the user data directory (see Q7, including `chenbont-studio.db`) and `~/.chenbont/` to the same locations on the new machine.
- **Uninstall (Linux .deb)**: `sudo dpkg -r chenbont-studio`; for AppImage just delete the file; other platforms follow as they ship.
- **Clean removal**: after uninstalling, delete the user data directory and `~/.chenbont/` manually — otherwise a reinstall inherits the old settings and sessions.

## 15. Something crashed — how do I troubleshoot?
1. Confirm you are on the latest release;
2. Note the version in **Settings → About** and collect today's log from `logs/` in the user data directory;
3. If one engine or language server misbehaves, disable/reinstall that runtime or plugin and retry;
4. For phone remote issues, first check whether LAN direct connection works, then check your relay account and traffic allowance.

When reporting, include the version, OS, reproduction steps and the relevant log excerpt.

## 16. How do I report bugs or suggest features?
File an issue at https://github.com/chenbont/chenbont-studio/issues — please include the version number and reproduction steps. You can also use in-app **Project Feedback** to leave issues and suggestions on the project itself.

## 17. Where do I get the latest version?
Watch the **Releases** page of this repository, or visit the official website https://chenbont.com.

## 18. Enterprise licensing / business inquiries
Contact huangbh@chenbont.com for customized licensing plans.
