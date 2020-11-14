---
title: "为 Windows 客户机安装 SPICE 客户端工具"
date: 2020-11-14T16:18:22+08:00
tags: ["KVM", "SPICE", "Windows"]
draft: false
---

使用 [KVM](https://zh.wikipedia.org/wiki/基于内核的虚拟机) 虚拟化 Windows 时性能极低，解决方法是安装 [SPICE 客户端工具](https://www.spice-space.org/download.html)，它包含 SPICE 客户机代理以及一些驱动程序等。

安装后不仅可以有效提高性能，还有和宿主机共享剪切板、自动调整客户机分辨率以及[自动释放不使用的内存](https://en.wikipedia.org/wiki/Memory_ballooning)等功能。
