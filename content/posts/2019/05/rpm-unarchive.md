---
date: "2019-05-26T00:08:26+08:00"
title: "解包 RPM"
tags: ["rpm"]
draft: false
---

## 将 RPM 转为 tgz

```bash
rpm2archive rpm_filename.rpm

# 解压 tgz
tar -xzvf rpm_filename.rpm.tgz [-C output_path]
```

## 将 RPM 转为 cpio

```bash
rpm2cpio rpm_filename.rpm
```
