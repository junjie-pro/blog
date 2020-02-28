---
title: "在 Linux console 中使用 HiDPI 字体"
date: 2020-02-28T20:57:47+08:00
draft: false
---

Linux 5.0 加入了一款 HiDPI 字体 —— Terminus console font，这款字体很适合在高分辨率的屏幕上使用。

### 在 Linux console 中的启用方式

#### 使用内核参数

在内核启动参数中加入 ```fbcon=font:TER16x32``` 即可启用此字体。

显然，如果内核较旧则无法通过此方式使用 Terminus 字体。

#### 通过包管理安装字体包并修改 ```/etc/vconsole.conf```

如果你是用的是 Fedora，可以用包管理（如 dnf）安装 ```terminus-fonts-console.noarch```，此包提供了 Terminus 字体文件（字体文件位于 ```/lib/kbd/consolefonts/```）。

你可以在 console 运行 ```setfont ter-font-name``` 临时地应用 Terminus 字体，重启后会恢复默认字体，或运行 ```setfont``` 立即恢复默认 console 字体。

可在 ```/etc/vconsole.conf``` 设置 "```FONT=ter-g28b.psf.gz```" 永久应用此字体，重启后生效。

### 参考文献

[Linux Kernel 5.0 (now rc1) will include Terminus console font as an option!](https://www.reddit.com/r/linux/comments/addp21/linux_kernel_50_now_rc1_will_include_terminus/)

[vconsole.conf — Configuration file for the virtual console](https://www.freedesktop.org/software/systemd/man/vconsole.conf.html)
