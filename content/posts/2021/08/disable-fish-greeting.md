---
title: "关闭fish的欢迎语"
date: 2021-08-18T17:09:30+08:00
tags: ["fish", "shell"]
draft: false
---

在```~/.config/fish/config.fish```中加入```set -U fish_greeting```：

```fish
if status is-interactive
    # Commands to run in interactive sessions can go here
    set -U fish_greeting
end
```

## 参考文献 ##

- [Frequently asked questions — fish-shell 3.3.1 documentation](https://fishshell.com/docs/current/faq.html#how-do-i-change-the-greeting-message)
