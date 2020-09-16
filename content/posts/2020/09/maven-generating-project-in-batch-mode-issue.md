---
title: "Maven \"Generating project in Batch mode\" 问题的解决方法"
date: 2020-09-13T09:05:40+08:00
tags: ["Maven"]
draft: false
---

这个问题是 Maven 获取远程 catalog 时网络速度过慢或无法访问造成的，可通过 ```-X``` 参数查看调试信息。

可以同时[为 Maven 设置 HTTP、HTTPS 代理](/posts/2020/09/set-proxy-for-maven)来解决此问题。

## 参考文献 ##

[Maven Archetype generate proxy issue, searching for remote catalog - Stack Overflow](https://stackoverflow.com/a/52721924/9397281)
