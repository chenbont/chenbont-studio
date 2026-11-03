# FAQ

> Covers only distribution and usage questions — no source code or internal implementation details.

## 1. Is this open source?
No. The Chenbont Studio **desktop app** is proprietary (closed-source) software. This repository provides only documentation and release downloads — no source code. Use is governed by the [LICENSE](../LICENSE). The companion cloud relay service **Studio Relay** is open source (https://gitcode.com/chenbont/studio-relay).

## 2. Download is slow / failing — what now?
- Check your network, or try again during a different time window;
- Some platforms throttle release bandwidth; retry later;
- Verify file integrity against the `checksums.txt` of each release.

## 3. Is the installer safe? Any antivirus false positives?
Our installers are built and checksum-verified. Some antivirus tools may flag them falsely — add the app to your allowlist. If you are still unsure, do not install.

## 4. Which systems are supported?
See "Supported Platforms" in [README](../README.md). Linux (.deb and AppImage) is available now; Windows / macOS builds are "Coming soon". Systems below the minimum requirements may not run.

## 5. Is the software free?
It is distributed free of charge. This repository is the official download channel — beware of third-party resellers. Some advanced features (e.g. official relay Pro tier, enterprise licensing) may be charged separately; see official announcements.

## 6. Can I resell or redistribute it?
**No.** Unauthorized redistribution, resale, reverse engineering, or embedding into other products is prohibited — see [LICENSE](../LICENSE).

## 7. Where is my data stored? Is anything uploaded?
Chenbont Studio runs locally; sessions and project data are stored on your machine by default. AI features connect to the model service you configure — see in-app docs and the model provider's terms for data flows. The author does not proactively collect your code. When using the official relay, the relay only forwards encrypted traffic and does not store plaintext.

## 8. How do I access from my phone?
Three options:
1. **LAN**: generate a QR code on the desktop app, scan with your phone;
2. **Official relay**: zero-config scan-to-connect (free tier: 1 controller + 1 guest; Pro see [中继服务定价](./中继服务定价.md));
3. **Self-hosted**: deploy the open-source **Studio Relay** (wildcard DNS + TLS), or use an SSH reverse tunnel on your own VPS.
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
