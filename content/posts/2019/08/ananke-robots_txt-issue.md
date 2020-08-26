---
title: "Hugo 博文 noindex 问题"
date: 2019-08-07T23:15:23+08:00
tags: ["Hugo"]
draft: false
---

我在 Google 上搜索我的博客时，发现只有主页被纳入了搜索结果，感觉有点奇怪。

在 Google Search Console 上发现我的博客有个问题，博文都有 ```noindex```、```nofollow``` 标记：```<META NAME="ROBOTS" CONTENT="NOINDEX, NOFOLLOW">```。

于是我在 Google 上搜索了这个问题，[发现可能是主题导致的](https://orianna-zzo.github.io/sci-tech/2018-01/blog%E5%85%BB%E6%88%90%E8%AE%B05-%E8%A6%81%E8%AE%A9github-pages%E8%A2%AB%E7%B4%A2%E5%BC%95%E5%88%B0/)。

我使用的主题是 ananke，在 ```themes/ananke/layouts/robots.txt``` 发现了下面的代码：

```text
User-agent: *
# robotstxt.org - if ENV production variable is false robots will be disallowed.
{{ if eq (getenv "HUGO_ENV") "production" | or (eq .Site.Params.env "production")  }}
  Disallow:
{{ else }}
  Disallow: /
{{ end }}
```

因此，只需要设置一内容为 ```production``` 的环境变量 ```HUGO_ENV``` 即可解决此问题：

```bash
echo 'export HUGO_ENV="production"' >> ~/.bashrc
source ~/.bashrc
```
