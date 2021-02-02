---
title: "使用指定的配置打开 GNOME 终端"
date: 2021-01-28T21:27:36+08:00
tags: ["Fedora", "GNOME"]
draft: false
---

我日常使用的系统是 Fedora Silverblue，它的根目录是只读的，但也可以使用 rpm-ostree 安装 rpm 包。不过我还是更喜欢保持宿主系统的“纯洁”，尽量使用 Podman 容器和 Flatpak 沙盒软件来完成日常操作。

Silverblue 默认安装了 toolbox，它能管理 Podman 容器，可以用 ```toolbox enter``` 来进入容器系统。因为 toolbox 创建的容器会使用宿主系统上对应用户的家目录，日常使用下来和宿主系统没什么区别。当然，这也是有代价的，启动容器的 bash 时明显比启动宿主系统上的慢很多，大概和 PowerShell 的启动速度差不多吧，不过这个问题不算很大，还可以接受。

但每次打开终端都需要敲命令很麻烦，所以我在 GNOME 终端创建了新的配置，自动运行 ```toolbox enter```。不过有时还是需要在宿主系统上执行命令，我并没有把 toolbox 设置为 GNOME 终端的默认配置，仍然保持了默认的 bash ，只在使用设定的快捷键启动终端时才会进入 toolbox 容器。

GNOME 终端会以 ```--profile=PROFILE_NAME``` 指定的配置启动，这就满足了我的需求。

## 我的配置方案 ##

### 启动 toolbox 容器 ###

* 快捷键：```Super``` + ```Z```
* 命令行：```gnome-terminal --profile=toolbox```

### 启动宿主系统 bash ###

* 快捷键：```Super``` + ```Shift``` + ```Z```
* 命令行：```gnome-terminal --profile=host```
