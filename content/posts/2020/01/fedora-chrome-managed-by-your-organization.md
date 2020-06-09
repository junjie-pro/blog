---
title: "Fedora 安装 Chrome 后显示“您的浏览器由所属组织管理”"
date: 2020-01-22T11:20:13+08:00
tags: ["Browser", "Chrome", "Fedora"]
draft: false
---

在 Fedora 上通过 RPM 方式安装 Google Chrome 后，会发现 Chrome 显示“您的浏览器由所属组织管理”。这是因为 Fedora 预装了一个名为 fedora-chromium-config.noarch 的包，其功能是改变 Chrome 的 UA，向其中添加 Fedora 的信息。

卸载此包即可解决 Chrome 显示“您的浏览器由所属组织管理”的问题，同时也可以更有效地隐藏系统信息，不是吗？

### 卸载

以 root 权限运行：

```bash
# dnf remove fedora-chromium-config.noarch
```
