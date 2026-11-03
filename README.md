# Chenbont Studio（晨邦智研 · 智能开发工作台）｜ Proprietary Software · Releases & Downloads

> ⚠️ **重要声明：Chenbont Studio 桌面端为专有（闭源）软件，不提供源代码。**
> 你在本仓库看到的是软件说明文档与发行版下载入口，**不含任何源码**。
> 软件的使用受本仓库内 [LICENSE](./LICENSE)（最终用户许可协议）约束。
>
> ⚠️ **Important: The Chenbont Studio desktop app is proprietary (closed-source) software. Source code is not provided.**
> This repository contains only documentation and release download links — **no source code**.
> Use of the software is governed by the [LICENSE](./LICENSE) (End-User License Agreement) in this repository.

---

## 软件简介 ｜ Overview

**Chenbont Studio（晨邦智研）** 是基于 Pi Coding Agent SDK 构建的**桌面端 AI 编程 IDE（智能开发工作台）**，提供会话管理、文件 / Git / 终端、内置浏览器、数据库管理、GitHub 集成等全套 IDE 能力，并支持通过云端中继服务实现手机远程访问桌面开发环境。本软件基于开源项目 Mcode（[huangbh2020/mcode](https://github.com/huangbh2020/mcode) ，MIT）二次开发，上游版权与许可声明见 [THIRD-PARTY-NOTICES.md](./THIRD-PARTY-NOTICES.md)。

**Chenbont Studio** is a desktop AI coding IDE (smart development workbench) built on the Pi Coding Agent SDK. It provides session management, file / Git / terminal, in-app browser, database management, GitHub integration, and lets you remotely access your desktop dev environment from a phone via a cloud relay service. It is derived from the open-source project Mcode ([huangbh2020/mcode](https://github.com/huangbh2020/mcode), MIT) — see [THIRD-PARTY-NOTICES.md](./THIRD-PARTY-NOTICES.md) for upstream copyright and license notices.

- 当前版本 ｜ Current version：**0.1.56**（2025 年 11 月）
- 授权方式 ｜ License：专有软件 / 免费分发，源码不公开 ｜ Proprietary / free distribution, source not public
- 适用人群 ｜ Audience：开发者、需要 AI 辅助编程与远程访问的个人与团队 ｜ Developers and teams needing AI-assisted coding and remote access

> 与之配套的云端中继服务 **Studio Relay**（`studio-relay`，Go 单二进制）为开源项目，另见 https://gitcode.com/chenbont/studio-relay 。本仓库仅分发桌面端闭源客户端。
>
> The companion cloud relay service **Studio Relay** (`studio-relay`, single Go binary) is open source at https://gitcode.com/chenbont/studio-relay . This repository distributes only the closed-source desktop client.

---

## 功能特性 ｜ Features

### 🤖 AI 引擎 + 自配模型

- 基于 **Pi Coding Agent SDK** 构建，模型由你自行配置：在**设置 → 模型**中填写任意 OpenAI 协议 / Responses API 端点，成本自控。
- 支持 **Claude / Pi / Codex / OpenCode 多引擎**（`AgentProvider` 抽象层），按会话选择引擎，界面与历史不变。
- 按角色分配模型：普通对话、AI 提交信息、合并冲突解决可分别使用不同模型；API Key 经 Electron `safeStorage` 加密存储。

### 💬 实时对话与多会话

- 消息按 token **实时流式渲染**为结构化卡片（思考 / 工具调用 / 工具结果 / 图片）。
- **工具审批**：允许 / 始终允许 / 拒绝，按会话维护待审批队列；**计划模式**先调研后执行。
- 每轮文件快照 + 一键「撤销本轮」；附加文件、粘贴图片、斜杠命令、**语音输入**。
- 会话持久化 SQLite，支持续传与自动归档；多项目 / 分组 / 置顶 / 搜索。
- **工作树会话**：隔离 git worktree 并行会话，一键合并回主检出。

### 🧰 全套 IDE

- **Monaco 编辑器**（30+ 语言）、三态文件视图（编辑 / Diff / 预览）、宽面板布局。
- **多仓库 Git**：递归发现 monorepo 内多个仓库，暂存 / 分支 / 历史 / 操作日志；**AI 生成提交信息**、**AI 解决合并冲突**。
- **多标签终端**（xterm.js + node-pty）：切换项目不杀后台进程，自定义常用命令。
- **内置浏览器**：多标签、书签 / 历史 / 下载、设备模拟、**元素拾取**送入对话、agent 自动驱动、登录态跨重启保留。
- **语言服务器（LSP）**：TypeScript / Python / Go / Java 一键安装启用，定义 / 引用 / 悬停 / 实时诊断。
- **数据库管理**：内置 SQLite / MySQL / PostgreSQL 客户端，表结构浏览、SQL 执行、**AI 自然语言生成 SQL**（两阶段检索 + 执行验证闭环）。
- **GitHub 集成**：浏览 / 合并 PR、管理 Issue、从已推送分支创建 PR。

### ⏰ 自动化与定时任务

- 定义定时任务驱动 agent 定时工作，六种触发方式：**一次性 / 间隔 / 每天 / 每周 / 每月 / cron**，带「下次运行」预览。

### 🧩 插件、MCP 与技能

- 从市场（git 仓库 / 本地目录 / zip）安装 agent 插件，默认**禁用**并先做组件审查；插件可携带 skills、命令、子代理、MCP server、hooks。
- 管理 MCP 服务器（stdio / HTTP，远程 OAuth 登录）；内置 SKILL.md 编辑器管理技能。

### 📱 手机端远程控制

- **局域网**：桌面端生成二维码，手机扫码配对（设备令牌认证）。
- **远程访问**：官方中继零配置扫码即用；或自托管开源 **Studio Relay**（泛域名 + TLS）；或自备 VPS 走 **SSH 反向隧道**。
- 手机可看会话实时流、发消息、中断 / 撤销、审批工具、浏览文件与 diff、执行 Git 操作（含 AI 提交信息）。
- **桌面协作**：控制端通过中继拨号驱动被控端会话（`/api/pi-rpc` 白名单编排）。

### ⚙️ 丰富的设置

常规、外观（含**手绘主题**：纸面 / 牛皮纸）、快捷键、模型、技能、通知、Git、终端、浏览器、语言服务器、鼠标手势、语音输入、MCP、插件、运行时、用量统计、关于。

### 🔄 其他

- **按需运行时**：agent 运行时（Pi / Claude / Codex）不再打包进安装包，首次使用自动下载，安装包体积大幅减小；在**设置 → 运行时**管理。
- **自动更新**（electron-updater）：从 GitHub Releases 拉取 `latest*.yml` 自动升级。
- **团队反馈**：收集并分享会话反馈，讨论与工作紧密关联。
- **10+ 种界面语言**：中文、英文、阿拉伯语、德语、西班牙语、法语、印尼语、日语、韩语、葡萄牙语、俄语、越南语等。

---

## 下载 ｜ Download

请从 **GitHub Releases** 页面下载对应平台的安装包：

Please download the installer for your platform from the **GitHub Releases** page:

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

- 问题反馈 ｜ Issues：https://github.com/chenbont/chenbont-studio/issues
- 官方网站 ｜ Website：https://chenbont.com
- 商务合作 ｜ Business：huangbh@chenbont.com

---

© 2025 Chenbont Studio（huangbh）。保留所有权利 ｜ All rights reserved.
