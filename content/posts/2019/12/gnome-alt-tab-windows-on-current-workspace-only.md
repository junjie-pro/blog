---
title: "GNOME：设置 Alt + Tab 只在当前工作区的窗口间切换"
date: 2019-12-21T17:42:16+08:00
tags: ["GNOME"]
draft: false
---

GNOME 的 ```Alt``` + ```Tab``` 默认在所有工作区的窗口间切换，当使用工作空间隔离任务时很不方便。因此，我选择将其设置为只在当前工作区中切换。

## 使用 ```gsettings``` 修改 dconf ##

```bash
gsettings set org.gnome.shell.app-switcher current-workspace-only true
```

### 如果你想恢复为在所有工作区间切换窗口，请运行 ###

```bash
gsettings reset org.gnome.shell.app-switcher current-workspace-only
```

## 使用 dconf Editor ##

如果你更喜欢图形化工具，你可以使用 dconf Editor 开启（或关闭）```/org/gnome/shell/app-switcher/current-workspace-only```。

## 参考文献 ##

[Gnome 3: How to Alt Tab windows on current workspace only (Example)](https://coderwall.com/p/m5mhoq/gnome-3-how-to-alt-tab-windows-on-current-workspace-only)
