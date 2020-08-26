---
title: "安装 PySpark"
date: 2020-04-22T16:03:21+08:00
tags: ["PySpark", "Spark"]
draft: false
---

## 安装 PySpark ##

### pip ###

```bash
pip install pyspark
```

### tarball ###

Spark tarball 中已包含 PySpark，可直接使用。也可在解包后使用 Python 脚本安装，以 spark-2.4.5-bin-hadoop2.7 为例：

```bash
tar -xzf spark-2.4.5-bin-hadoop2.7
python spark-2.4.5-bin-hadoop2.7/python setup.py install
```
