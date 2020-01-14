---
title: "修改语言优先级"
date: 2020-01-13T22:13:22+08:00
tags: ["Fontconfig"]
draft: false
---

当 Linux 发行版的系统语言设置为非中文时，中文汉字字体会被渲染为日文汉字字体，这个问题可以通过使用仅有简体/繁体中文汉字的字体修复（如 Fedora 的 google-noto-sans-sc-fonts.noarch），但还可以通过修改 Fontconfig 的配置文件来解决。

### 修改 Fontconfig 配置

#### 直接修改配置文件

向 ```~/.i18n``` 添加以下配置可将语言优先级修改为美国英语（en-US）、中国大陆简体中文（zh-CN），优先级从左向右依次递减：

```text
FC_LANG=en-US:zh-CN
```

#### 使用 GUI 工具修改配置文件

fonts-tweak-tool 是配置 Fontconfig 的 GUI 工具，在其 Language Ordering 页面可修改语言优先级。

### 探究原因

我认为这个问题可能是 Japanese（日文）、Simplified Chinese（简体中文）以及 Traditional Chinese（繁体中文）三者中，日文对应的英语单词的首字母 J 按字母表 A-Z 的顺序最靠前导致的。

注意，我并没有细究原因。如有错误，欢迎来函指正。

### 外部链接

[Fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/)

[fonts-tweak-tool 的源代码仓库](https://bitbucket.org/tagoh/fonts-tweak-tool/)
