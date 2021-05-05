---
title: "为 flatpak 应用设置代理"
date: 2021-05-05T18:29:27+08:00
tags: ["dconf", "gsettings", "flatpak", "linux"]
draft: false
---

有些应用程序（如 Chrome）没有使用环境变量来设置代理，而是读取 dconf 数据库存储的配置信息。因为 flatpak 应用程序运行在沙盒中，它们读取到的配置均为默认值。

因此需要使用 ```flatpak run --command=sh``` 进入应用运行的 flatpak 环境为 dconf 数据库添加正确的代理配置。

代理设置：

| 代理 | 主机 | 端口 |
| :----: | :----: | :----: |
| HTTP | localhost | 3128 |
| HTTPS | localhost | 3128 |
| Socks | localhost | 1080 |

命令（以 Chrome 为例）：

```sh
#进入容器
flatpak run --command=sh com.google.Chrome

#设置 HTTP 代理
gsettings set org.gnome.system.proxy.http host localhost
gsettings set org.gnome.system.proxy.http port 3128 

#设置 HTTPS 代理
gsettings set org.gnome.system.proxy.https host localhost
gsettings set org.gnome.system.proxy.https port 3128 

#设置 Socks 代理
gsettings set org.gnome.system.proxy.socks host localhost
gsettings set org.gnome.system.proxy.socks port 1080 
```
