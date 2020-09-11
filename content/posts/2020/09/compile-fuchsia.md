---
title: "在 Fedora Linux 上编译 Fuchsia"
date: 2020-09-11T17:25:06+08:00
tags: ["Fuchsia"]
draft: false
---

## 要求 ##

* curl
* gcc（CGO）
* git（建议 2.24 或以上）
* python（2.7），且要能在 PATH 中找到 python
* unzip
* 大约 70 [GiB](https://zh.wikipedia.org/wiki/Gibibyte) 的磁盘空间，建议 100 GiB
* 时间，Intel® Core™ i3-6100 的编译时间约为 140 分钟。

## 获取源代码 ##

注意：fuchsia.dev 的所有样例均以 ```~/fuchsia``` 为根目录。你可能需要为 curl 和 git 设置代理。

```bash
cd ~
curl -s "https://fuchsia.googlesource.com/fuchsia/+/master/scripts/bootstrap?format=TEXT" | base64 --decode | bash
```

### 设置环境变量 ###

将 ```//.jiri_root/bin``` 添加到 ```PATH``` 中，此目录包含了 fx、jiri 等程序。

```bash
echo "export PATH=~/fuchsia/.jiri_root/bin:$PATH" >> ~/.bashrc
source .bashrc
```

## 设置编译配置 ##

```bash
cd ~/fuchsia
fx set workstation.x64
```

## 编译 ##

```bash
fx build
```

## 使用模拟器运行 Fuchsia ##

jiri 自动下载了 Fuchsia Emulator（FEMU，Fuchsia 模拟器），实际上为 Android 模拟器（aemu），路径为 ```//prebuilt/third_party/aemu```。

使用 ```fx emu``` 运行。

注意：FEMU 可能无法直接在 Podman 容器中运行，请使用物理机以避免不必要的麻烦。

## 参考文献 ##

* [Fuchsia](https://fuchsia.dev/)
