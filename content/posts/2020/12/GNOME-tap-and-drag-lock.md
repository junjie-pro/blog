---
title: "GNOME: 拖拽锁定"
date: 2020-12-05T22:45:52+08:00
tags: ["GNOME"]
draft: false
---

GNOME 支持拖拽锁定，但默认情况下没有开启，且没有提供图形界面配置。下面是配置拖拽锁定的方法：

## 使用 ```gsettings``` 修改 dconf ##

```bash
gsettings set org.gnome.desktop.peripherals.touchpad tap-and-drag-lock true
```

### 如果你想恢复为默认设置，请运行 ###

```bash
gsettings reset org.gnome.desktop.peripherals.touchpad tap-and-drag-lock
```

## 使用 dconf Editor ##

如果你更喜欢图形化工具，你可以使用 dconf Editor 开启（或关闭）```/org/gnome/desktop/peripherals/touchpad/tap-and-drag-lock```。
