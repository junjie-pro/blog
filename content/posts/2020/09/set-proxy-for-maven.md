---
title: "为 Maven 设置代理"
date: 2020-09-13T09:05:16+08:00
tags: ["Maven"]
draft: false
---

修改 ```.m2/settings.xml``` 文件：

```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 https://maven.apache.org/xsd/settings-1.0.0.xsd">
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
