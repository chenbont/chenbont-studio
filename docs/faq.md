# FAQ

> Covers only distribution and usage questions — no source code or internal implementation details.

## 1. Is this open source?
No. The Chenbont Studio **desktop app** is proprietary (closed-source) software. This repository provides only documentation and release downloads — no source code. Use is governed by the [LICENSE](../LICENSE).

## 2. Download is slow / failing — what now?
- Check your network, or try again during a different time window;
- Some platforms throttle release bandwidth; retry later;
- Verify file integrity against the `checksums.txt` of each release.

## 3. Is the installer safe? Any antivirus false positives?
Our installers are built and checksum-verified. Some antivirus tools may flag them falsely — add the app to your allowlist. If you are still unsure, do not install.

## 4. Which systems are supported?
See "Supported Platforms" in [README](../README.md). Linux (.deb and AppImage) is available now; Windows / macOS builds are "Coming soon". Systems below the minimum requirements may not run.

## 5. Is the software free?
The software is obtained through this repository (the official channel) — beware of third-party resellers. Off-LAN remote connections go through the official Chenbont relay and require a cloud account: P2P direct traffic is not metered, while relayed traffic includes a monthly allowance and excess is charged at the published rate from your wallet balance. Top up in the remote-connect panel.

## 6. Can I resell or redistribute it?
**No.** Unauthorized redistribution, resale, reverse engineering, or embedding into other products is prohibited — see [LICENSE](../LICENSE).

## 7. Where is my data stored? Is anything uploaded?
Chenbont Studio runs locally; sessions and project data are stored on your machine by default. AI features connect to the model service you configure — see in-app docs and the model provider's terms for data flows. The author does not proactively collect your code. When using the official relay, the relay only forwards encrypted traffic and does not store plaintext.

## 8. How do I access from my phone?
Two options:
1. **LAN**: generate a QR code on the desktop app, scan with your phone;
2. **Official relay**: all off-LAN connections go through the official relay and require signing in to a cloud account in **Settings → Account**; connections prefer P2P direct transport, and relayed traffic includes a monthly allowance with excess charged at the published rate from your wallet balance. Self-hosted relays and SSH tunnels are not supported.
See [usage.md](./usage.md) for details.

## 9. Do I need to install a CLI / agent runtime separately?
No. The agent runtime (Pi / Claude / Codex) is downloaded automatically on first use and can be managed in **Settings → Runtime**.

## 10. Which models / engines can I use?
Configure any OpenAI-compatible / Responses API endpoint in **Settings → Models**, and switch between the built-in **Claude / Pi / Codex / OpenCode** engines per session. API keys are stored with OS-level encryption.

## 11. How do I report bugs or suggest features?
File an issue at https://github.com/chenbont/chenbont-studio/issues — please include the version number and reproduction steps.

## 12. Where do I get the latest version?
Watch the **Releases** page of this repository, or visit the official website https://chenbont.com.

## 13. Enterprise licensing / business inquiries
Contact huangbh@chenbont.com for customized licensing plans.
