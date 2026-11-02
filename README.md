# Chenbont Studio（专有软件 · 发行与下载）｜ Proprietary Software · Releases & Downloads

> ⚠️ **重要声明：Chenbont Studio 桌面端为专有（闭源）软件，不提供源代码。**
> 你在本仓库看到的是软件说明文档与发行版下载入口，**不含任何源码**。
> 软件的使用受本仓库内 [LICENSE](./LICENSE)（最终用户许可协议）约束。
>
> ⚠️ **Important: The Chenbont Studio desktop app is proprietary (closed-source) software. Source code is not provided.**
> This repository contains only documentation and release download links — **no source code**.
> Use of the software is governed by the [LICENSE](./LICENSE) (End-User License Agreement) in this repository.

---

## 软件简介 ｜ Overview

**Chenbont Studio** 是基于 Pi Coding Agent SDK 构建的桌面端 AI 编程 IDE，提供会话管理、文件 / Git / 终端、浏览器预览等能力，并支持通过云端中继服务实现手机远程访问桌面开发环境。本软件基于开源项目 Mcode（[huangbh2020/mcode](https://github.com/huangbh2020/mcode) ，MIT）二次开发，上游版权与许可声明见 [THIRD-PARTY-NOTICES.md](./THIRD-PARTY-NOTICES.md)。

**Chenbont Studio** is a desktop AI coding IDE built on the Pi Coding Agent SDK. It provides session management, file / Git / terminal access, in-app browser preview, and lets you remotely access your desktop dev environment from a phone via a cloud relay service.

- 当前版本 ｜ Current version：**0.1.56**（2025 年 11 月）
- 授权方式 ｜ License：专有软件 / 免费分发，源码不公开 ｜ Proprietary / free distribution, source not public
- 适用人群 ｜ Audience：开发者、需要 AI 辅助编程与远程访问的个人与团队 ｜ Developers and teams needing AI-assisted coding and remote access

> 与之配套的云端中继服务 **Studio Relay**（`studio-relay`，Go 单二进制）为开源项目，另见 https://gitcode.com/chenbont/studio-relay 。本仓库仅分发桌面端闭源客户端。
>
> The companion cloud relay service **Studio Relay** (`studio-relay`, single Go binary) is open source at https://gitcode.com/chenbont/studio-relay . This repository distributes only the closed-source desktop client.

---

## 下载 ｜ Download

请从 **GitCode Releases** 页面下载对应平台的安装包：

Please download the installer for your platform from the **GitCode Releases** page:

| 平台 ｜ Platform | 文件 ｜ File | 说明 ｜ Notes |
| --- | --- | --- | --- |
| Linux (.deb) | `Chenbont-Studio-0.1.56-amd64.deb` | Debian/Ubuntu 安装包 |
| Linux (AppImage) | `Chenbont-Studio-0.1.56-x86_64.AppImage` | 免安装可执行包 |
| Windows | `Chenbont-Studio-0.1.56-win-x64.exe` | 敬请期待 ｜ Coming soon |
| macOS | `Chenbont-Studio-0.1.56-mac.dmg` | 敬请期待 ｜ Coming soon |

> 下载地址：在本仓库页面点击 **Releases**（发行版）标签，选择最新版本。
> Download: open the **Releases** tab on this repository page and pick the latest version.
> 校验文件完整性请参考各发行版的 `checksums.txt`。
> Verify integrity via the `checksums.txt` included with each release.

---

## 支持平台 ｜ Supported Platforms

| 平台 ｜ Platform | 最低版本要求 ｜ Minimum requirement |
| --- | --- | --- |
| Linux | glibc 2.31+ 的 x86_64 发行版（Debian 11 / Ubuntu 20.04+） |
| Windows | Windows 10 64 位及以上 ｜ Windows 10 x64 and later |
| macOS | macOS 11 及以上 ｜ macOS 11 and later |

---

## 安装与快速上手 ｜ Install & Quick Start

参见 [docs/使用说明.md](./docs/使用说明.md)（中文）｜ [docs/usage.md](./docs/usage.md) (English)。

---

## 许可证 ｜ License

本软件采用专有许可协议，详见 [LICENSE](./LICENSE)。

The software is licensed under a proprietary agreement — see [LICENSE](./LICENSE).

**核心约束（摘要）｜ Key terms (summary):**
- 你可以下载并安装使用本软件 ｜ You may download and use the software.
- **禁止**反编译、逆向工程、破解 ｜ No reverse engineering, decompiling, or cracking.
- **禁止**未经授权的再分发、二次销售或植入其他产品 ｜ No unauthorized redistribution, resale, or embedding.
- 软件按“现状”提供，作者不承担任何担保与责任 ｜ Provided “as is”, no warranty or liability.

---

## 常见问题 ｜ FAQ

参见 [docs/常见问题.md](./docs/常见问题.md)（中文）｜ [docs/faq.md](./docs/faq.md) (English)。

---

## 反馈与联系 ｜ Feedback & Contact

- 问题反馈 ｜ Issues：https://gitcode.com/chenbont/studio-relay/issues
- 官方网站 ｜ Website：https://chenbont.com
- 商务合作 ｜ Business：huangbh@chenbont.com

---

© 2025 Chenbont Studio（huangbh）。保留所有权利 ｜ All rights reserved.
