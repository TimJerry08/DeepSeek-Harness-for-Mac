# DeepSeek Harness for macOS

> **真正的开箱即用**：下载，双击，直接进入。  
> 无需终端，无需安装 Node，无需打开浏览器标签页——只需一个原生 macOS App。

[![Platform](https://img.shields.io/badge/Platform-macOS-1E90FF?style=flat&logo=apple)](https://www.apple.com/macos/)
[![Apple Silicon](https://img.shields.io/badge/Apple%20Silicon-M1%2F2%2F3%2F4-333333?style=flat&logo=apple)](https://www.apple.com/mac/)
[![Version](https://img.shields.io/badge/Version-0.1.0-blue)](https://github.com/TimJerry08/DeepSeek-Harness-for-Mac/releases)
[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-000000)](https://github.com/TimJerry08/DeepSeek-Harness-for-Mac)

---

## 简介

**DeepSeek Harness for macOS** 是官方 [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) CLI 工具的原生 Swift + WKWebView 外壳。

它将命令行体验变成了一款**双击即可运行的桌面应用**——非常适合那些想使用 DeepSeek 强大的本地评估/沙盒环境，但不想碰终端的人。

---

## 功能特性

- **真正的开箱即用**——所有依赖都已内置：Node.js v24.19.0 LTS 和 `@deepseek-ai/dsh@0.1.0-rc.7` 全部打包在 App 内部。
- **原生 macOS 体验**——基于 Swift 和 WKWebView 构建（零 Electron/Tauri 开销）。在 Apple Silicon 上**3 秒内**启动。
- **极小的下载体积**——压缩后的 `.dmg` 安装包仅 **87 MB**（解压后约 393 MB）。
- **单进程生命周期管理**——`dsh web` 服务以子进程方式运行在独立的进程组中，退出 App 时会被完整终止。
- **菜单栏常驻**——关闭窗口后 App 仍在菜单栏运行，使用 App 封面图标。可一键重启、在浏览器中打开（用于调试）、复制服务地址。
- **原生诊断工具**——出错时可查看实时日志、一键复制诊断信息，或直接从 App 内打开日志文件。
- **干净的关于面板**——清晰显示内置运行环境版本和版权归属。

---

## 系统要求

- **Apple Silicon Mac**（M1、M2、M3 或 M4）——本版本**不**支持 Intel Mac。

---

## 安装方法

1. 从 [Releases](https://github.com/TimJerry08/DeepSeek-Harness-for-Mac/releases) 页面下载最新的 `.dmg` 文件。
2. 打开 `.dmg`，将 `DeepSeek Harness.app` 拖入 `Applications` 文件夹。
3. 双击 App 图标启动。

> **重要提示**：本应用尚未公证。首次打开时，macOS 可能会提示“无法验证开发者”。  
> **请按住 `Control` 键**，然后点击 App 图标，选择“打开”，再确认即可。此操作只需执行一次。

---

## 工作原理

- App 会在 `127.0.0.1` 上启动一个本地 HTTP 服务（默认端口 `3080`，若被占用则自动切换到其他端口）。
- 然后在原生 WKWebView 窗口中加载 DeepSeek Harness Web UI——**无需打开任何浏览器标签页**。
- 所有数据均保留在你的电脑上；App 不会发起任何外部网络请求（除非你配置了 DeepSeek API 调用）。

---

## 已知限制 (v0.1.0)

- **仅支持 Apple Silicon**——由于缺少测试硬件，暂不提供 Intel 版本。
- **尚未公证**——需要按照上述方法通过 Control + 点击来运行。
- **体积较大**——解压后约 393 MB，这是因为 Node.js 及所有依赖都已嵌入。我们计划在后续版本中进行优化。
- **无自动更新**——目前请手动查看 Releases 页面获取新版本。

---

## 开发 / 构建（面向进阶用户）

本外壳的源代码目前**暂不开源**。不过如果你好奇，本应用使用了以下技术构建：

- Swift（AppKit 和 WKWebView）
- Node.js（作为运行时捆绑）
- 官方 `@deepseek-ai/dsh` 包

如果你想自己构建类似的外壳，可以检查二进制结构——但我们不公开提供构建脚本。

---

## 致谢与许可

- **DeepSeek Harness**——由 DeepSeek AI 开发，基于 [MIT 许可证](https://github.com/deepseek-ai/deepseek-harness/blob/main/LICENSE) 发布。
- **Node.js**——版权归 Node.js 贡献者所有，基于 [MIT 许可证](https://github.com/nodejs/node/blob/main/LICENSE) 发布。

**本外壳（macOS App 壳层）** © 2026 Timothy-Wang。保留所有权利。  
本应用暂不开源；你被授予有限的许可证，允许将提供的二进制文件用于个人或商业目的，但未经明确许可，不得重新分发、反向工程或修改。

---

## 反馈与支持

- 如有 Bug 报告或功能建议，请 [提交 Issue](https://github.com/TimJerry08/DeepSeek-Harness-for-Mac/issues)。
- 如有一般性问题，可通过 [Twitter / 其他联系方式] 联系（可选）。

---

**由一位坚信好软件永远不需要终端的高中毕业生，用 ❤️ 制作。**

*立即下载，体验真正的开箱即用。*