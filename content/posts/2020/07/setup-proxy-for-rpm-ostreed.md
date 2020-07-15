---
title: "为 rpm-ostreed 设置代理"
date: 2020-07-14T16:20:06+08:00
tags: ["rpm-ostree"]
draft: false
---

编辑 rpm-ostreed 服务配置文件：

```bash
systemctl edit rpm-ostreed.service
```

添加如下内容：

```text
[Service]
Environment="http_proxy=http://IP:Port"
```

重启 rpm-ostreed 服务：

```bash
systemctl restart rpm-ostreed.service
```

# 参考文献 #

[GitHub coreos/rpm-ostree/issues/208](https://github.com/coreos/rpm-ostree/issues/208#issuecomment-307369036)

