---
title: "Pyspark Deploy Mode and Log Level"
date: 2020-04-22T15:25:46+08:00
tags: ["PySpark", "Spark"]
draft: false
---

## 启动模式 ##

### local ###

使用一个 Worker 线程本地化运行 Spark（默认）。多用于开发测试，不需要构建集群。

### standalone ###

连接到指定的 Spark 单机版集群（Spark standalone cluster）的 Master，不需要构建集群。

### yarn ###

以客户端或集群模式直接连接 yarn 集群。

### mesos ###

客户端直接连接 mesos 集群。

## 参数 ##

### local ###

* local：使用一个 Worker 线程本地运行（默认）
* local[n]：使用 n 个 Worker 线程本地运行
* local[*]：使用机器 CPU 核心数个 Worker 线程本地运行

### standalone ###

spark://host:port 连接到制定的 Spark 单机集群的 Master。必须使用 Master 所配置的端口，默认端口为 7077。

### yarn ###

默认以客户端模式连接到 yarn 集群，集群位置由环境变量 HADOOP\_CONF\_DIR 决定。

Spark 2.0 以前，yarn 分为 yarn-client 与 yarn-cluster。

Spark 2.0 之后，使用 --deploy-mode=client|cluster 参数设置连接模式。

### mesos ###

mesos://host:port 连接到指定的 Mesos 集群。host 为 Mesos Master。必须使用 Master 配置的端口，默认为5050。

## 日志设置 ##

### 日志级别 ###

ALL, DEBUG, ERROR, FATAL, INFO, OFF, TRACE, WARN

### 设置日志级别 ###

#### 修改 log4j.properties ####

默认为在控制台输出 INFO 及以上级别的日志。

```
log4j.rootCategory=INFO, console
```

#### 运行时使用 setLogLevel(log_level) 设置 ####

```python3
from pyspark imposr SparkContext

sc = SparkContext('local', 'first app')
sc.setLogLevel('WARN')
```
