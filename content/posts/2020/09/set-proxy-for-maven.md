---
title: "为 Maven 设置代理"
date: 2020-09-13T09:05:16+08:00
tags: ["Maven"]
draft: false
---

修改 ```.m2/settings.xml``` 文件：

```xml
<settings>
  <proxies>
    <proxy>
      <id>http-proxy</id>
      <active>true</active>
      <protocol>http</protocol>
      <host>localhost</host>
      <port>3128</port>
    </proxy>
    <proxy>
      <id>https-proxy</id>
      <active>true</active>
      <protocol>https</protocol>
      <host>localhost</host>
      <port>3128</port>
      </proxy>
  </proxies>
</settings>

```
